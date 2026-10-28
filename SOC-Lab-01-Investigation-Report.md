SOC Lab 01 – Investigation of Failed Login Attempts

1. Objective

Investigate suspicious failed login attempts and identify potential indicators of a brute-force attack.

2. Scenario

A security alert was triggered after 35 failed login attempts occurred within 60 seconds on a user account.

3. Investigation Steps

* Reviewed the authentication logs.
* Identified repeated failed login attempts.
* Checked timestamps and login activity.
* Investigated the source IP address when available.
* Assessed whether the activity could indicate a brute-force attack.

4. Linux Commands Used

Search for failed SSH login attempts:

grep "Failed password" /var/log/auth.log

Count failed login attempts:

grep -c "Failed password" /var/log/auth.log

Display the latest authentication events:

tail -n 20 /var/log/auth.log

Note: The log file location may vary depending on the Linux distribution.

5. Findings

The alert reported 35 failed login attempts within 60 seconds. This activity may indicate a brute-force attack.

Further investigation is required to identify the source IP address, determine whether the attempts targeted one or multiple accounts, and check for successful logins.

6. Recommended Actions

* Investigate the source IP address.
* Check for successful authentication after the failed attempts.
* Review other suspicious authentication events.
* Apply account lockout policies or rate limiting where appropriate.
* Escalate the incident if malicious activity is confirmed.

7. Conclusion

This lab demonstrates how to investigate suspicious authentication activity using Linux logs and basic command-line tools.

Skills demonstrated: Log Analysis, Linux, SSH Authentication, Incident Investigation, Brute-Force Detection, SOC Fundamentals.
