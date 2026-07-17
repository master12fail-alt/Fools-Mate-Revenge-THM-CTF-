# Fools-Mate-Revenge-THM-CTF-
This will be the second Fools-mate room. I did the fools-mate room in one take https://github.com/master12fail-alt/Fools-Mate-THM-CTF-.git . I was exited to the part 2 which was this room called "Fools-Mate Revenge".

## Metadata
| Field | Value |
|----------|----------|
| Platform  | TryHackMe |
| Difficulty | Medium |
| Tools Used | Burp Suite |
| Date completed | 2026-07-17 |

## TL;DR

We found out this room can be cracked by using the payload in the setting of the Chess game that was in the website.Just send the 


### 1.Overview/Target Description


 ### 2.Initial Recon
 We directly went to Burp and start initial recon with proxy HTTP History. The highlighted yellow and red Request are the 2 important . We found out in /api/setting/ can be used to solve this room.

 <img width="1920" height="1080" alt="burp1" src="https://github.com/user-attachments/assets/36688269-9881-4891-ad98-a7e76cf4328c" />


### 3.Vulnerability Discovery
In the /api/move, when we checkmated with rook then the  .From the proxy tab, we can clearly see the there "reward gate closed: session.config.unlocked is not set". so we knew that this is sessin related vulnerability .

<img width="1920" height="1080" alt="setteing1" src="https://github.com/user-attachments/assets/56d3a1e4-9f46-410a-bbda-f0f48f690b46" />


### 4.Exploitation
After we knew the Vulnerability, we tried constructor prototype Payload. so we sent the payload with the /api/setting request in which server responded with OK .
<img width="1920" height="1080" alt="constructorproto" src="https://github.com/user-attachments/assets/29afce74-8559-459f-a5c5-00aa8eb53ae5" />

### 5.Root Cause Confirmation
### 6.Getting the Flag
As the payload was sent in Exploitation stage, we copied the Cookie ID of that request and pasted in the /api/move request the sent. We got the FLAG.

<img width="1920" height="1080" alt="flagfinal" src="https://github.com/user-attachments/assets/542fb049-1d75-4f54-857e-ad6d45bf7370" />


### 7.Lesson Learned
We learned about the Constructor Prototype payload. We learned how to use Cookie id to get the Flag.
## Appendix
Screenshots: screenshots/


