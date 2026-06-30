SSH-Brute-Force-Mitigation-Lab

Objective:

Demonstrate the vulnerability of an SSH service to brute force attacks and implement a proactive defense solution using Fail2Ban in a Linux environment.

1. Vulnerability Phase (Baseline)

I checked the server's vulnerability by performing a brute force attack with Hydra.

Result: The attack was successful, confirming that the system was exposed.

2. Defense Implementation (Fail2Ban)
I set up Fail2Ban on the target machine to automatically block IPs that exceed the failed attempts threshold. The /etc/fail2ban/jail.local file was configured with the following parameters:

[sshd]

enabled = true

maxretry = 3

bantime = 3600

3. Mitigation Verification

After activating Fail2Ban, I ran the attack again to check the blocking.
Result (Attack blocked): The attack is stopped by the firewall with a "Connection refused" error.

Ban Confirmation: I checked the ban status on the target machine using the su command.
