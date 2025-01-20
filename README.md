<h1>LOG Analysis with SPLUNK</h1>

 <h2>Scenario</h2>
 
You have recently joined the Security Operations team at a medium-sized
organization. As part of your first assignment, you are tasked with analyzing OpenSSH log files
to help identify any potential security threats. The organization has recently experienced a few
suspicious incidents, and management is keen on understanding if there are any patterns or
anomalies in the SSH login attempts.

 <h2>Objectives</h2>
 
Your goal is to use Splunk Cloud to thoroughly analyze the provided OpenSSH log file and
create a comprehensive report covering all aspects of your work. You will also need to set up a
dashboard and an alert in Splunk Cloud to help monitor similar activities in the future.
Additionally, you will manage user accounts in Splunk Cloud as part of the assignment.

 <h2>Tasks</h2>
 
1. User Management:
- Add New Users: Create a new user in Splunk Cloud for each group member.
Ensure the following configurations:

■ Time Zone: Set the time zone to WAT (West Africa Time).

■ Default App: Set the default app to "launcher (home).

■ Password Policy: Configure each user to change their password on the
first login.

■ Role Assignment: Assign an appropriate role to each new user based on
their responsibilities.


 <h2>Analysis</h2>
- Upload the Log File: Load the provided OpenSSH log file into Splunk Cloud.

- Analyze the Data: Conduct a detailed analysis of the log file. Look for anomalies
such as unusual IP addresses, multiple failed login attempts, or any other
indicators of potential security issues.


<h2>Dashboard and Alert Creation</h2>

- Create a Dashboard: Use the search query "Received disconnect from
112.95.230.3: 11: Bye Bye [preauth]" to create a dashboard in Splunk Cloud.
Ensure the dashboard visualizes relevant data from the OpenSSH logs
effectively.
- Configure an Alert: Set up an alert based on the provided search query. The
alert should:
■ Run daily at 8am.

■ Expire after 24 hours.

■ Trigger when the number of results is greater than 2.

■ Be received via email in plain text format.

■ Include all group members as recipients: Ensure that all members of
the team are included as recipients of the alert email.

■ Restrict Email Domain: Configure Splunk to allow alert emails to be sent
only to a particular domain.


 <h2>Field Extraction</h2>
- Create Field Extraction: Configure a field extraction for the IP address
‘183.62.140.253’ in Splunk Cloud. Name the extraction ‘src_ip’.

 <h2>Reporting</h2>
- Prepare and submit a well-organized report that includes your Splunk Cloud
dashboard and alert configurations along with a comprehensive summary of all
tasks completed.

 <h2>Link to Log</h2>
[OpenSSH Log(https://drive.google.com/file/d/1mkemQ-rYBqVNpU5psdA5fTfVzrNCH23G/view?usp=drivesdk)]

 <h2>Project Walkthrough</h2>

Login to Splunk:
<img src="https://i.imgur.com/z23MLp6.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/HsTWKt5.jpeg"/>
<br />
<br />

Create User for everyone in the team/group:
<img src="https://i.imgur.com/kVpQu65.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/d5F9EUi.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/sSQaJ4g.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/0B7BgfT.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/1h6ESP6.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/KIGi1mz.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/aUPMYwQ.jpeg"/>
<br />
<br />

Select time to (WAT) and assign roles to the uesers created, then configure each user to change their password when signed in:
<img src="https://i.imgur.com/C5xDMFp.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/quwPfRH.jpeg"/>
<br />
<br />

All Users Created:
<img src="https://i.imgur.com/Gdaz13z.jpeg"/>
<br />
<br />


 <h2>LOG Analysis</h2>

Next, upload and analyze the logs:

<img src="https://i.imgur.com/2FgzPyD.jpeg"/>
<br />
<br />

Scroll down and select Upload
<img src="https://i.imgur.com/PbCS92b.jpeg"/>
<br />
<br />

Click "Select File"
<img src="https://i.imgur.com/yvnRBNa.jpeg"/>
<br />
<br />

Select "Next" and set Source Type as "Default"
<img src="https://i.imgur.com/XuOTivT.jpeg"/>
<br />
<br />

Click "Next" leave "Input Settings as "Default" then Review and Submit.
<img src="https://i.imgur.com/Rmx1RM0.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/Nyzedco.jpeg"/>

Select "Start Searching to begin analyzing the logs
<br />
<br />
<img src="https://i.imgur.com/hTA1xU0.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/hIaOgX4.jpeg"/>
<br />
<br />

Create Dashboard:
<img src="https://i.imgur.com/ZcNKRTj.jpeg"/>
<br />
<br />

Dashboard Created:
<img src="https://i.imgur.com/sY7kmfk.jpeg"/>
<br />
<br />


Create Alerts:
<img src="https://i.imgur.com/kuvcbSr.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/4eCQe2e.jpeg"/>
<br />
<br />
<img src="https://i.imgur.com/eG8iuCJ.jpeg"/>
<br />
<br />

Alert Created:
<img src="https://i.imgur.com/ernHoq4.jpeg"/>
<br />
<br />


Dashboard:
<img src="https://i.imgur.com/wsOVAlr.jpeg"/>
<br />
<br />


 <h2>Findings</h2>

After analyzing the log file, i discovered the log contains multiple failed logins and authentication failures to a remote system. The attacker was trying to connect with a root privilege over an SSH session and most of the SSH request and Authentication came from an IP that was consistent:


Failed login request from: 103.99.0.122

Authentication request from: 183.62.140.253


The attacker also tried to login using a username “user” that wasn’t recorgnized by the system. The timestamp of the log also signified a brute-force attack that was done
with an automated tool


 <h2>Conclusion</h2>

In conclusion, after a thorough analysis of the log file, I concluded that the log originated from an attempted brute-force attack on a remote system via an SSH session.



 <h2>Recomendtions</h2>
1. Use Strong Passwords

2. Limit Login Attempts
   
3. Monitor IP Addresses

4. Use Multi-Factor/Two-Factor Authentication (MFA/2FA)

5. Disable Root SSH Logins

6. Use Web Application Firewalls (WAF)
    
