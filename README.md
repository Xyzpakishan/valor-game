## Installation For Heroku User

### Required Heroku Buildpack
* heroku/nodejs
* https://github.com/jonathanong/heroku-buildpack-ffmpeg-latest.git
* https://github.com/DuckyTeam/heroku-buildpack-imagemagick.git

### Steps To Setup Bot on Heroku
* Fork this github repository.
* Click on Deploy Button.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/DineshValor/valor)

* Signup/Sign In with your user id password.
* Set `App name`.
* Click on `Deploy app`.
* After finish, click on `Manage App`.
* Go to `Settings`. (If settings option not seen, then switch browser into destop mode) 
* Click on `Add Buildpack` and add all three. [mentioned above] (note:- add nodejs again too)
* Go to `Deploy`.
* Click on `GitHub (connect to gitHub)`. Connect you Github account with heroku, if not done yet before.
* Click on `Search` and connect `<username>/valor`
* `Click on `Deploy Branch`. (It's take around few minutes to finish, be patience.)
* After finish, go to `Resources`.
* Turn ON `worker: node .`
* Click on `More↑↓`, then click on `View longs`.
* Wait for QR code generate. (Only in pc or laptop compatible)
* Scan it via Whatsapp app.
* Hooray Bot ready, check whatsapp and try to use bot using command `??` `/menu`

─────────────────────────

## Installation For Termux User
### Requirement:
* Android 7 or above
* Internet
* 2 Device (one to scan qr code from whatsapp web)
* Little bit IQ

### Steps To Setup Bot Into Termux
* Download Termux. [`Download`](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_universal.apk)
* Download `node_modules`. [`Download`](https://drive.google.com/file/d/1Ydcjt3PnGiOr9vL66dFC11V0sEywJb32/view?usp=drivesdk)
* Fork repo or download `valor-bot`. [`Download`](https://github.com/DineshValor/valor/archive/refs/heads/v4.0.5-md.zip)
* Open termux.
* Type below given commands one by one ↓↓
(do not try to copy `$` along with command 😂)
```
$ termux-setup-storage
$ pkg update && pkg upgrade
$ pkg install git
$ pkg install nodejs-lts -y
$ pkg install ffmpeg -y
$ pkg install imagemagick -y
$ pkg install yarn
$ cd /storage/downloads
$ git clone https://github.com/DineshValor/valor
╭──────────────────
│[If Error in git clone]
│• download `valor-bot` from 3nd step.
│• extract `valor-bot.zip` using any file manager into `downloads` folder.
╰──────────────────
$ cd /storage/downloads/valor-bot
(Here replace valor-bot name with current download valor-bot folder name)
```
* Extract `node_modules.zip` using any file manager into `valor-bot` folder. For ex. (downloads/valor-bot/node_modules)
* Continue in termux after `$ cd /storage/downloads/valor-bot`
```
$ node .
╭──────────────────
│[If Error in node .]
│• check twice node_modules
│• contact me on whatsapp
╰──────────────────
```
* Wait for bot starting...
* Scan QR code from 2nd device. (Go to whatsapp > Linked Devices > Join `Multi Device Beta` > Click on `link device`)
```
╭──────────────────
│[If device vibrate but not connected]
│• open file manager, go to `downloads > valor-bot > session.data.json` & delete session.data.json file.
│• exit from termux.
╰──────────────────
$ cd /storage/downloads/valor-bot
$ node .
```
* Scan QR code, once connected, appear green in termux at first boot-up.

*Caution:- If failed again i. QR code, then repeat steps.

─────────────────────────

## How To Customise Message Display

### Message With Image-Location, Template-URL, Template-Call, Buttons
```
conn.sendHydrated(m.chat, 'text', 'footer', 'image.jpg', 'template-url', 'Template-Name', '0123456789', 'Template-CALL', [
      ['Donate', '/donasi'],
      ['Speed', '/ping'],
      ['Owner', '/owner']
], m, {asLocation: true})
```

### Remove Template Call Button
* Replace 'Template-Call' with 'null' both places to remove it.
```
conn.sendHydrated(m.chat, 'text', 'footer', 'image.jpg', 'template-url', 'Template-Name', null, null, [
      ['Donate', '/donasi'],
      ['Speed', '/ping'],
      ['Owner', '/owner']
    ], m, {asLocation: true})
```

### Remove Both Template URL & Call Button
* Replace 'Template-URL' & 'Template-Call' with 'null' each time both places to remove it.
```
conn.sendHydrated(m.chat, 'text', 'footer', 'image.jpg', null, null, null, null, [
      ['Donate', '/donasi'],
      ['Speed', '/ping'],
      ['Owner', '/owner']
    ], m, {asLocation: true})
```
### Add/Remove/Edit Buttons
* To remove button, delete `['button', '/button']` row.
* To add button, add `['button', '/button']` code line.
* To edit/rename button, edit/rename `button` name.
```
conn.sendHydrated(m.chat, 'text', 'footer', 'image.jpg', null, null, null, null, [
      ['Button¹', '/button¹'],
      ['Button²', '/button²'],
      ['Button³', '/button³]
    ], m, {asLocation: true})
```

### Add/Remove/Edit Image
* To remove image, replace 'image.jpg' with 'null'.
```
conn.sendHydrated(m.chat, 'text', 'footer', null, 'template-url', 'Template-Name', '0123456789', 'Template-CALL', [
      ['Donate', '/donasi'],
      ['Speed', '/ping'],
      ['Owner', '/owner']
], m, {asLocation: true})
```
* To change image, replace 'image.jpg' with custom 'image.jpg link'.
```
conn.sendHydrated(m.chat, 'text', 'footer', 'https://telegra.ph/file/fe5883c8011fd033e395c.jpg', 'template-url', 'Template-Name', '0123456789', 'Template-CALL', [
      ['Donate', '/donasi'],
      ['Speed', '/ping'],
      ['Owner', '/owner']
], m, {asLocation: true})
```

#### Note
* Use `conn.sendButton()` instead `conn.sendHydrated()` to clickable on `Read more` in the `footer` Menu Message.
```
conn.sendButton(m.chat, 'hi', text.trim(), 'https://telegra.ph/file/fe5883c8011fd033e395c.jpg', [
['menu', '/menu'],
['speed','/ping']
], m, { asLocation: true })
```
![Picsart_22-02-25_15-27-08-938__01](https://user-images.githubusercontent.com/98645523/155695355-33d20852-25f2-4e1b-88cf-36cad7ed9f1d.jpg)

