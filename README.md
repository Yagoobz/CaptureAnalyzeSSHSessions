<h2>Exercise 5: Capture and Analyze SSH Sessions</h2>

<h3>Objectives</h3>
- x
<br />
- x
<br />
- x
<br />
- x

<h3>Step 1: Update Wireshark Filter to Capture Traffic from a Different Host</h3>
To initiate the capture of all traffic between myself and the remote server I plan to SSH into, I input "host tty.sdf.org" into the Wireshark capture filter. To generate SSH traffic, I utilize Windows PowerShell, providing my login credentials. Additionally, I generate Telnet traffic by entering the same username and password. While examining Wireshark, I initially detected what seemed like a potential error. However, upon further reflection, I realized it was simply SSH exercising caution, a fundamental aspect of its security measures. When SSH attempts to log into a host it hasn't encountered previously, it displays a message as a precautionary measure.
<br />
<img src="https://github.com/Yagoobz/CaptureAnalyzeSSHSessions/assets/145611184/1ad469ab-0a5a-4d7d-9eb5-b47bc24b682b" height="30%" width="70%" alt="Disk Sanitization Steps"/>

<h3>Step 2: Check Conversations Under Wireshark Statistics</h3>
Since I've captured both Telnet and SSH traffic, I wondered if Wireshark could inform me about the number of conversations in the packet capture. Indeed, it can! By navigating to the "Statistics" tab, then selecting "Conversations," and specifically choosing "TCP" because both SSH and Telnet utilize TCP, we're able to observe the two conversations. This view provides details such as port numbers, IP addresses, packet counts, and more. 
<br />
<img src="https://github.com/Yagoobz/CaptureAnalyzeSSHSessions/assets/145611184/687d7fc4-3524-47bc-b19b-e7b127ec8af6" height="30%" width="70%" alt="Disk Sanitization Steps"/>

<h3>Step 3: Analyze SSH Conversation</h3>
Based on previous observations, I'm aware that the Telnet conversation is unencrypted, leaving all activity visible to anyone intercepting the traffic between me and the server. However, upon examining the SSH conversation and selecting "Follow Stream," it's evident that all data is encrypted. Anyone attempting to decipher this encrypted traffic intercepted along the way will likely face significant challenges.
<br />
<img src="https://github.com/Yagoobz/CaptureAnalyzeSSHSessions/assets/145611184/613509f2-4ad9-4583-a6a5-b92151f49a65" height="30%" width="70%" alt="Disk Sanitization Steps"/>

