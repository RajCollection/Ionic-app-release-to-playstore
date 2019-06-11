# Ionic-app-release-to-playstore

## App release to google play store steps:

### App side:

1.	Run the command to remove console logs plugin from yout app

> ionic cordova plugin rm cordova-plugin-console

Or

> cordova plugin rm cordova-plugin-console

2.	Generate unsigned apk

> ionic cordova build --release android

or

> ionic build android –release

-------
3.	Go to app signing section in play store account, get app play_store_key
Replace this key in your manifest.json file of app

-----
4.	Generate signed apk, run command

> keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000

Enter all the fields, name, alias, organigation unit, organigation name, location, and password

it will generate one .keystore file, copy this file in to platform/android folder, rename it to .jks

Enter your app name, alias, password which you given while generating keystore 

Download release.signin.properties file from  https://github.com/docketrun/app-build

Place it in platform/android folder

--------
5.	Run release command again

ionic cordova build --release android

or

ionic build android –release

------------------------

Playstore side:

Note: all account setup should be ready 
1.	Go to app releases,
2.	Create app
3.	Give all details including icon, screenshots and banner image
4.	Pricing and distribution, fill details
5.	Content rating
6.	Store listing
7.	App relases, upload apk, fill deatils, click on review, next click on final step 
Click on Start rollout to production button
Done
