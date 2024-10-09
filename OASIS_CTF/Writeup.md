# OASIS Capture The Flag Competition
- This is a writeup on some of the challenges that taught me the most
- Our team got **10th** position and overall this was a very fun experience and i got to learn about alot of new things

## I have been falling for 30 minutes!
### Description:
- It hits you! The IOI uses an encrypted communication service to control the virus's every move. Your mission is clear: sever the link between the IOI and the virus to isolate and defeat it. However, you linger too long in one place, and the IOI catches wind of your plan. Fortunately for them, they have a firewall jail just beneath the surface. The ground trembles and splits open, sending you plummeting into the abyss. You land with a resounding THUD, surrounded by towering firewalls. You see a computer in the middle of the cell, and feel like you can use it to your advantage. Can you break free from this digital prison? [firewall](https://firewall.oasis.cryptonite.live)

### Solution:
- When you first load up the site you see you can change the user by clicking the arrow buttons in the centre and we notice that affects the "userid=number" in the url. Since the parameters of the url are visible it is more prone to SQL injection attacks, so i tried changing the value of the parameter to something else to check that, I put in the value as "6" and behold the flag appeared.
- Flag:
> *OASIS{T00_m4ny_h0urs_4nd_wh3r3_d1d_1t_l34d}*

## All that for a drop of blood
### Description:
- As the terminal roars back to life, a single message blinks on the screen: "START GAME." You're no longer just a playerâ€”you're in the endgame now. The keyboard before you looks deceptively simple, but nothing you try gets past the loading screen. Something is clearly wrong. Can you uncover the hidden flaw and push beyond this stagnant start? [https://startgame.oasis.cryptonite.live/]
