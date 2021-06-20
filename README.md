# SteamAutoAuth
A chrome web extension to ease logging into multiple steam accounts. Automatically inputs password and enters mobile code on steam login. Powered by [`steam-totp`](https://github.com/DoctorMcKay/node-steam-totp/).

As someone who has to constantly keep switching between many accounts in steam, it can take a lot of time. This extension is made with the hope that it can reduce that time significantly.

![SteamAutoAuth User Interface](https://github.com/mabdu11ah/chrome-steamautoauth/blob/master/assets/preview-0.2.0.png?raw=true)

## Usage
### Installing the Extension In Chrome
[Download](https://github.com/mabdu11ah/chrome-steamautoauth/archive/0.2.0.zip) or clone the repository, then go to `chrome://extensions`.

Enable the developer mode, then click `Load Unpacked`. Select the repository's directory and hit select.

The extension should now be loaded. 

### How to add an account
To add an account, click the extension's icon in the chrome bar.

**Enter the username (required) of the account as well as the password and/or shared secret.**

Now when you enter the username in the Steam Login Username Input, the password and/or the code will automatically be input, as well as all the Sign In/Submit buttons being clicked.

**Note: There is an intended delay before the script kicks in, this is to ensure the username isn't changed in the input box.**

If you want more details as to what exactly happens:

- **Username and Password**
	- When the username is detected in the username input, the password will automatically be entered into the password input.
	- The sign in button is automatically pressed after a delay assuming no new characters have been input into the username input.

- **Username and Shared Secret**
	- When the username is detected in the account name box, and the sign in button is pressed, the shared secret is used to generate a code which is inserted into the code input and automatically presses the submit button.

- **Username, Password and Shared Secret** 
	- When the username is detected in the username input, the password will automatically be entered into the password input.
	- The sign in button is automatically pressed after a delay assuming no new characters have been input into the username input.
	- Once the Steam Guard Code input is shown, the shared secret is used to generate a code which is inserted into the code input and automatically presses the submit button.

## Shared Secret

### What is a shared secret?
**TL;DR**: Essentially a code which generates your Steam Guard Code, depending on the time, so you can login. 

Shared Secret is a code generated by Steam when you get mobile authenticator. 
Using a series of steps involving the current time your steam guard code is generated.
Since it involves the current time, it changes every 30 seconds.
The steps do not require an internet connection and therefore, the code can be generated offline. 

You will need either a **rooted** Android phone, an iPhone or [Steam Desktop Authenticator](https://github.com/Jessecar96/SteamDesktopAuthenticator).

### How to get your shared secret

[Rooted Android](https://github.com/SteamTimeIdler/stidler/wiki/Getting-your-'shared_secret'-code-for-use-with-Auto-Restarter-on-Mobile-Authentication#getting-shared-secret-from-android-windows)

[iOS/iPhone](https://www.youtube.com/watch?v=23MTKlSPi7Y)

[Steam Desktop Authenticator](https://www.youtube.com/watch?v=JjdOJVSZ9Mo)

## Security
All account details are kept in `chrome.storage.local` (i.e. your local device). Nothing is sent to a server.
Credentials (password and/or shared secrets) are base64 encoded.

## Building Manually

Although the built files are included in this repository, if you would like to build the extension yourself, ensure you have node and npm installed and execute this command in the folder:

```
npm install && npm run build
```

## Help 

If you have any queries or need help, make an issue [here](https://github.com/mabdu11ah/chrome-steamautoauth/issues).
