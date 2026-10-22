SOC Lab 01 — Failed Login Investigation

Project type: Educational SOC investigation
Status: Simulated case study

1. Overview

This lab documents how a junior security analyst can investigate a simulated alert involving repeated failed login attempts.

Scenario: 35 failed login attempts against one account within 60 seconds.

Objective: Assess the alert, identify the evidence required, and recommend appropriate next steps.

2. Initial Assessment

A high number of failed logins in a short period may indicate a brute-force attempt. However, the alert alone does not confirm an attack.

Possible explanations include:

* Repeated incorrect passwords
* A misconfigured application or service
* A possible brute-force attempt

3. Investigation Procedure

1. Review authentication logs for the relevant time period.
2. Identify the affected account and target device.
3. Check timestamps and count the failed attempts.
4. Identify the source IP address, if recorded.
5. Look for successful logins after the failures.
6. Compare the activity with normal account behavior.

4. Linux Log Analysis

On Linux systems using systemd, authentication events may be available through the system journal.
Example command:
Bash 
sudo journalctl --since "1 hour ago" | grep -Ei "failed password|authentication failure"
On systems that use /var/ log/ auth.log,inspect matching entries with: 
bash 
sudo grep -Ei "failed password|authentication failure" /var/log/auth.log
Note: Log locations and messages vary by distribution. These commands are examples and should only be used on systems you are authorized to inspect.

5. Findings and Limitations

The simulated alert reports 35 failed login attempts within 60 seconds.

The source IP address, affected device details, and any subsequent successful logins must be verified in the relevant logs.

No conclusion about the attacker’s identity or whether an attack succeeded can be made from the alert alone.

6. Recommended Actions

* Preserve relevant authentication logs.
* Investigate the source IP and affected account.
* Check for successful logins and other suspicious activity.
* Follow the organization’s incident response procedures.
* Escalate the alert if evidence supports a suspected attack.

7. Conclusion

Repeated failed logins can indicate suspicious activity and require further investigation. A security analyst should validate the evidence before classifying the event as a confirmed attack.

Learning outcomes: Alert triage, Linux log analysis, evidence gathering, and incident documentation.

Disclaimer: This is an educational case study based on a simulated alert, not a real incident investigation.
