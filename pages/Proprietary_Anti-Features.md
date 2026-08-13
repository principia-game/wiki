This page goes over the anti-features that were present in the proprietary version of Principia.

**Note:** Everything mentioned in this page is historical, describing things how they were in the last proprietary version of Principia (1.5.1), and have been removed from the open source version of the game.

## Windows activation system/DEMO mode
The Windows version of Principia had an activation system that would check if the user has purchased the game. By default when installing the game it would be in DEMO mode, which placed various limitations for what could be done in the game as well as a dialog reminding the user to purchase the game.

{{ image({
	"url": "images/proprietary_anti-features/windows_demo_dialog.webp",
	"alt": "Thank you for playing Principia. This is the demo version with limited functionality. Purchase the full version to get rid of this annoying message, and to get unlimited publishing and downloading access to the community website. Get the full version for a discounted price by referring your friends to buy it too. Read more on the store page."
}) }}

The Windows version of Principia was quietly made free in 2015 due to the administration of selling the game costing more than the revenue generated, giving every user who registered on the community site a full Windows license of the game. Once the official community site shut down in early 2018, the online activation system became non-functional and the game would always be in DEMO mode unless it had already communicated with the server before it shut down.

Before the open source release of Principia and after the official community site's shutdown, the Windows version of the game would be "cracked" by sharing the cookie file of someone who had logged into the community site. For example, one would copy the following lines into the `c` file (used by libcurl as its cookie jar) in the Principia user data folder:

```
#HttpOnly_.principiagame.com	TRUE	/	FALSE	1551164781	phpbb_ziao2_u	42
#HttpOnly_.principiagame.com	TRUE	/	FALSE	1551164781	phpbb_ziao2_k	blabla
#HttpOnly_.principiagame.com	TRUE	/	FALSE	1551164781	phpbb_ziao2_sid	blabla
#HttpOnly_.principiagame.com	TRUE	/	FALSE	0	z2lia7e	1
```

What is important for the activation is that `z2lia7e` is set to `1`, `phpbb_ziao2_u` is set to a user ID greater than 1, and the two other phpBB session cookies are present. If principiagame.com was unresponsive (rather than just throwing 502 errors), you might need to add `127.0.0.1 principiagame.com` to your hosts file to cause the connection to immediately fail and try the offline activation.

Later on principia-web would set these cookies in order to automatically activate the Windows version of Principia upon logging into the community site.

### Download tokens
While the Windows version of Principia was in DEMO mode, the user could play a limited amount of levels from the community site, consuming a download token for each level played. While purchasing the game would give unlimited access to the community site, users could also refer others to install the Windows version of Principia to get more download tokens.

The following message would be shown when the user had run out of download tokens:

> **You have run out of download tokens :(**
>
> What to do now? Buy Principia to support our development and get unlimited access.
> You can also get 10 more download tokens by referring one of your friends to install the Principia Demo. Read more by clicking the button below.

## X-Principia analytics
When logged into the community site, Principia will send some analytics data in the `X-Principia` HTTP header as part of its ping request to the community site to check for version updates and new user notifications.

- The current window width of the game
- The current window height of the game
- Number of version checks made (i.e. playtime session length)
- The ID of the community level currently played
- A state value, denoting with bits whether the user is in the sandbox, a procedural adventure level, a main puzzle level, on the main menu, or playing a community level.

This would be encrypted with a XOR cipher and encoded as Base64 when sent to the server.

## Android license verification
The Android version of Principia had a license verification system that would check if the user had purchased the game on Google Play. This would be used when attempting to register an account on the community site to check whether the game is pirated or not. If the game was pirated, the user would be unable to register an account on the community site.

## Android Facebook analytics
The Android version of Principia featured the Facebook SDK, which would send analytics data to Facebook when the user did certain actions in the game.

## Android LITE edition
The Android version of Principia had a free LITE edition with limited features and no ability to play levels from the community site.
