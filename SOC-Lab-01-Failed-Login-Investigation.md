SOC Lab 01 — Failed Login Investigation

1. Overview

This is a learning exercise based on a simulated security alert.

Scenario: 35 failed login attempts were detected against one account within 60 seconds.

Objective: Understand the alert, identify the evidence needed for investigation, and recommend appropriate next steps.

2. Initial Assessment

A high number of failed login attempts in a short period may indicate a brute-force attempt. However, this alert alone does not confirm an attack.

Possible explanations include:

* Incorrect passwords entered repeatedly.
* A misconfigured application or service.
* A possible brute-force attack.

3. Investigation Steps

1. Review authentication logs for the relevant time period.
2. Identify the affected account and target device.
3. Check timestamps and the number of failed attempts.
4. Identify the source IP address, if recorded.
5. Look for successful logins following the failures.
6. Compare the activity with normal account behavior.

4. Linux Commands

On a Linux system using systemd, authentication events may be available through the journal:

sudo journalctl --since "1 hour ago" | grep -Ei "failed password|authentication failure"

On systems that use /var/log/auth.log, you can inspect matching entries with:

sudo grep -Ei "failed password|authentication failure" /var/log/auth.log

Note: Log locations and messages vary by Linux distribution. These commands should be used only on systems you are authorized to inspect.

5. Findings and Limitations

The simulated alert reports 35 failed login attempts within 60 seconds.

The source IP address, affected device details, and any subsequent successful logins must be verified in the relevant logs. No conclusion about the attacker’s identity or the success of an attack can be made from the alert alone.

6. Recommended Actions

* Preserve relevant authentication logs.
* Investigate the source IP and affected account.
* Check for successful logins and other suspicious activity.
* Follow the organization’s incident response procedures.
* Escalate the alert if evidence supports a suspected attack.

7. Conclusion

Repeated failed logins can indicate suspicious activity and require further investigation. A security analyst should validate the evidence before classifying the event as a confirmed attack.

Project type: Educational SOC investigation
Status: Initial case documentation
