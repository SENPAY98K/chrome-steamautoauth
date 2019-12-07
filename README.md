# SteamAutoAuth
A chrome web extension to automatically generate and enter mobile code on steam login. 
Powered by [`steam-totp`](https://github.com/DoctorMcKay/node-steam-totp/).

**Note:** This will only work for users who use who have the You will need your **shared secret**!

# Shared Secret

## What is a shared secret?
**TL:DR**: Essentially a code which generates your Steam Guard Code, depending on the time, so you can login. 

Shared Secret is a code generated by Steam when you get mobile authenticator. 
Using a series of steps invloving the current time your steam guard code is generated.
Since it invovles the current time, it changes every 30 seconds.
The steps do not require an internet connection and therefore, the code can be generated offline. 

You will need either a **rooted** Android phone, an iPhone or [Steam Desktop Authenticator](https://github.com/Jessecar96/SteamDesktopAuthenticator).

## How to get your shared secret

[Rooted Android](https://github.com/SteamTimeIdler/stidler/wiki/Getting-your-'shared_secret'-code-for-use-with-Auto-Restarter-on-Mobile-Authentication#getting-shared-secret-from-android-windows)

[iOS/iPhone](https://www.youtube.com/watch?v=23MTKlSPi7Y)

[Steam Desktop Authenticator](https://www.youtube.com/watch?v=JjdOJVSZ9Mo)

# Setup

## How to install as an extension
Clone the repository, then go to `chrome://extensions`.

Enable the developer mode, then click Load Unpacked. Select the repository's directory and hit select.

The extension should now be loaded. 

## How to add an account
To add an account, click the extension's icon in the chrome bar.

Now enter your username and shared secret and hit enter.

**Note:** The details are kept in **plain text** in your `chrome.storage`. **Nothing is sent to a server.**

The extension works by checking if the username is in the `chrome.storage` and if it is it generates the code by using the shared secret which is attached to the username. 

# Help 

If you have any queries or need help, contact me [here](https://steamcommunity.com/id/vrtgn). 

# Donations

[Donate to me](https://steamcommunity.com/tradeoffer/new/?partner=306348802&token=fkRNEvP-).

[Donate to DrMcKay (Creator of `steam-totp`)](https://www.paypal.com/signin?forceLogin=false&returnUri=https%3A%2F%2Fwww.paypal.com%2Fdonate&state=%252F%253Ftoken%253DRphc0uE-ilTnGq4CWwFMFWj0eFvQPGGWv0XF6iu96h_z13NWWh4spZ7Rl_KAtpHuv0dK2G%2526fromUL%253Dtrue&intent=donate&ctxId=b997d1de82a642fd9a7f33a750dfac0a).



