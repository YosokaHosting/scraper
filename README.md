<h1 align="center">YosokaHosting <img src="https://user-images.githubusercontent.com/1303154/88677602-1635ba80-d120-11ea-84d8-d263ba5fc3c0.gif" width="40px" alt=""><br></h1>
<p align="center">
<img src="https://i.ibb.co/g9qGSTm/Screenshot-20230308-211801-1.jpg" />
</p>

<p align="center">

- 🐻 I'm YosokaHosting / RidhoRomadhon
- 😼 I'm Progamer / newbiee
- 👻 Year 19

-🐻 I'm No Girl 🐻-
</p>

------

## ```FOLLOW ALL SOSIALMEDIA ME```
<p align="center">
<a href="#"><img title="Rest-Api" src="https://img.shields.io/badge/Rest Api Free-green?colorA=%23ff0000&colorB=%23017e40&style=for-the-badge"></a>
</p>
<p align="center">
<a href="https://youtube.com/@YosokaHosting"><img src="https://img.shields.io/badge/YouTube YosokaNesia-ff0000?style=for-the-badge&logo=youtube&logoColor=ff000000&link=https://youtube.com/ZeroYT7" /><br>
<a href="https://instagram.com/@yt_YosokaHostinga"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"/> 
<a href="https://wa.me/6285891734201"><img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" />
</p>

## ```DONASI```

- [`SAWERIA`](https://saweria.co/yosoka)l

# scraper

Install package
```sh
npm i @YosokaHosting/scraper
```
Install latest version from github (not recommended)
```sh
npm i github:YosokaHosting/scraper
```

## What's updated?
- Using [zod](https://www.npmjs.com/package/zod) to validate data input and output. (not finished yet)
- Some bug fixes.
- Breaking changes. see [this](#from-v200-to-v300)
- Added `didyoumean` to search for similar words.
- Added `snapsave`
- Added `zippyshare`
- Added `sfilemobi`

## Example use
```js
// ESM 
import * as scraper from '@YosokaHosting/scraper'
// CJS
const scraper = require('@YosokaHosting/scraper')
```
### Instagram Downloader
```js
// Instagram Downloader
import { 
    instagramdl, 
    instagramdlv2, 
    instagramStory,
    instagramStoryv2
} from '@YosokaHosting/scraper'
const url = 'https://www.instagram.com/reel/CXK49yFLtJ_/?utm_source=ig_web_copy_link'
instagramdl(url).then(console.log).catch(console.error)
instagramdlv2(url).then(console.log).catch(console.error)
// use both to handle error
instagramdl(url).catch(_ => instagramdlv2(url)).then(console.log)
// Use async/await or top level await
console.log(await instagramdl(url).catch(console.error))
console.log(await instagramdlv2(url).catch(console.error))
// Instagram Story downloader
const username = 'freefirebgid'
const story = await instagramStory(username).catch(async _ => await instagramStoryv2(username))
console.log(story)
```
- `instagramdl` use website https://snapinsta.app, 
- `instagramdlv2` use website https://downloadgram.org
- `instagramdlv3` use website https://downvideo.quora-wiki.com
- `instagramdlv4` use website https://instadownloader.co
- `instagramStory` use website https://storydownloader.app
- `instagramStoryv2` use website https://www.instadp.com [**not working**]


### Youtube Downloader
```js
// Youtube downloader
import { 
    youtubedl,
    youtubedlv2 
} from '@YosokaHosting/scraper'
const url = 'https://youtu.be/iik25wqIuFo'
youtubedl(url).catch(_ => youtubedlv2(url)).then(({ video }) => {
    video['240p'].download().then(console.log).catch(console.error)
})
// Use async/await 
const yt = await youtubedl(url).catch(async () => await  youtubedlv2(url))
const dl_url = await yt.video['240p'].download()
console.log(dl_url)
```
- `youtubedl` use website https://www.y2mate.com
- `youtubedlv2` use website https://yt5s.com
- `youtubedlv3` use website https://onlinevideoconverter.pro
- `youtubeSearch` use website https://www.youtube.com


### Tiktok downloader
```js
// Tiktok downloader
import { 
    tiktokdl,
    tiktokdlv2 
} from '@YosokaHosting/scraper'
// Tiktok downloader v1
const url = 'https://www.tiktok.com/@tiktok/video/6844446901010982300'
tiktokdl(url).then(console.log).catch(console.error)
// tiktokdl v2
tiktokdlv2(url).then(console.log).catch(console.error)
// async / await 
console.log(await tiktokdl(url).catch(console.error))
console.log(await tiktokdlv2(url).catch(console.error))
```
- `tiktokdl` use website https://snaptik.app
- `tiktokdlv2` use website https://api.tikmate.app
- `tiktokdlv3` use website 'https://ssstik.io
- `tiktokfyp` use website https://t.tiktok.com [**Not Working**]

### All in One Downloader
```js
import {
    aiovideodl,
    savefrom,
    snapsave
} from '@YosokaHosting/scraper'
// Facebook video downloader
console.log(await aiovideodl('https://fb.watch/9WktuN9j-z/'))
// Twitter video downloader
console.log(await aiovideodl('https://twitter.com/jen_degen/status/1458167531869458440?s=20'))

// Tiktok downloader
console.log(await savefrom('https://www.tiktok.com/@omagadsus/video/7025456384175017243?is_from_webapp=1&sender_device=pc&web_id6982004129280116226'))
// Instagram downloader
console.log(await savefrom('https://www.instagram.com/reel/CXK49yFLtJ_/?utm_source=ig_web_copy_link'))

// Instagram downloader
console.log(await snapsave('https://www.instagram.com/reel/CXK49yFLtJ_/?utm_source=ig_web_copy_link'))
// Facebook video downloader
console.log(await snapsave('https://fb.watch/9WktuN9j-z/'))
```
- `aiovideodl` use website https://aiovideodl.ml [**Not Working**]
- `savefrom` use website https://id.savefrom.net
- `snapsave` use website https://snapsave.app

### Aksara Jawa
```js
// Aksara jawa
import { 
    latinToAksara,
    aksaraToLatin
} from '@YosokaHosting/scraper'
// Latin to aksara jawa
console.log(latinToAksara('hallo rek'))
// Aksara jawa to latin
console.log(aksaraToLatin('ꦲꦭ꧀ꦭꦺꦴ​ꦫꦺꦏ꧀', { HVokal: false })) // Hvokal: false mean ꦲ will return 'ha' not vokal
```
Source: https://bennylin.github.io/transliterasijawa/


### Primbons
```js
// Primbons
import { 
    getZodiac,
    nomorhoki
} from '@YosokaHosting/scraper'
// Get zodiac
console.log(getZodiac(1, 1))
// Get nomor hoki
console.log(await nomorhoki(6213353))
```
- `artimimpi` use website https://www.primbon.com
- `artiname` use website https://www.primbon.com
- `nomorhoki` use website https://www.primbon.com
- `getZodiac` source: https://github.com/Nurutomo/wabot-aq/blob/master/plugins/zodiac.js


### Images
```js
// Images
import {
    googleImage,
    pinterest,
    wallpaper,
    stickerTelegram,
} from '@YosokaHosting/scraper'
const keyword = 'minecraft'
// Google image
console.log(await googleImage(keyword))
// Pinterest image
console.log(await pinterest(keyword))
// Wallpaper
console.log(await wallpaper(keyword))
// Sticker telegram
console.log(await stickerTelegram(keyword))
```
- `googleImage` use website https://www.google.com
- `pinterest` use website https://www.pinterest.com
- `stickerTelegram` use website https://combot.org
- `stickerLine` use website https://store.line.me
- `wallpaper` use website https://www.shutterstock.com
- `wallpaperv2` use website https://wall.alphacoders.com
- `wallpaperv3` use website https://www.hdwallpapers.in


### Religions
```js
// Religions
import {
    asmaulhusna, asmaulhusnajson,
    alquran,
    jadwalsholat, listJadwalSholat
} from '@YosokaHosting/scraper'
// Asmaul Husna
console.log(await asmaulhusna())
// Asmaul Husna Json
console.log(asmaulhusnajson) // the json will empty if you never use `asmaulhusna()`
// alquran 
console.log(await alquran())
// Jadwal Sholat
console.log(await jadwalsholat('semarang'))
```
- `alquran` source: https://raw.githubusercontent.com/rzkytmgr/quran-api/master/data/quran.json
- `asmaulhusna` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/religions/asmaulhusna.ts
- `jadwalsholat` use website https://www.jadwalsholat.org


### Games
```js
// Games
import {
    tebakgambar, tebakgambarjson,
    asahotak, asahotakjson
} from '@YosokaHosting/scraper'
// Tebak gambar
console.log(await tebakgambar())
// Tebak gambar json
console.log(tebakgambarjson) // the json will empty if you never use `tebakgambar()`
// Asahotak
console.log(await asahotak())
// Asahotak json
console.log(asahotakjson) // the json will empty if you never use `asahotak()`
```
- `asahotak` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/asahotak.ts
- `caklontong` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/caklontong.ts
- `family100` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/family100.ts
- `siapakahaku` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/siapakahaku.ts
- `susunkata` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/susunkata.ts
- `tebakbendera` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebakbendera.ts
- `tebakgambar` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebakgambar.ts
- `tebakkabupaten` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebakkabupaten.ts
- `tebakkata` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebakkata.ts
- `tebakkimia` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebakkimia.ts
- `tebaklirik` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebaklirik.ts
- `tebaktebakan` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tebaktebakan.ts
- `tekateki` source: https://raw.githubusercontent.com/YosokaHosting/scraper/master/src/games/tekateki.ts


### News
```js
// News
import {
    cnbindonesia,
    antaranews,
    kompas
} from '@YosokaHosting/scraper'
// Cnbindonesia
console.log(await cnbindonesia())
// Antaranews
console.log(await antaranews())
// Kompas
console.log(await kompas())
```
- `antaranews` use website https://www.antaranews.com
- `cnbindonesia` use website https://www.cnbcindonesia.com
- `kompas` use website https://www.kompas.com
- `liputan6` use website https://www.liputan6.com
- `merdeka` use website https://www.merdeka.com
- `suaracom` use website https://www.suara.com

### Encryption
```js
// Encryption
import {
    toBase64,
    fromBase64ToString,
    randomUUID,
    randomBytes,
    createHash
} from '@YosokaHosting/scraper'
// To base64
const base64 = toBase64('Hello World!!')
console.log(base64)
// From base64 to string
console.log(fromBase64ToString(base64)) // 'Hello World!!'
// Random UUID
console.log(randomUUID())
// Random Bytes
console.log(randomBytes(16))
// Hash
console.log(createHash('sha256', 'Hello World!!'))
```
- `randomUUID` source: https://github.com/uuidjs/uuid/blob/main/src/v4.js and https://github.com/nodejs/node/blob/master/lib/internal/crypto/random.js
- `randomBytes` use `crypto` module
- `createHash` use `crypto` module

### Bioskop
```js
// Bioskop
import {
    bioskopNow,
    bioskop
} from '@YosokaHosting/scraper'
// Bioskop 
console.log(await bioskop())
// Bioskop Now
console.log(await bioskopNow())
```
- `bioskop` use website https://jadwalnonton.com
- `bioskopNow` use website https://jadwalnonton.com

### Downloader 
```js
import {
    mediafiredl,
    sfilemobi,
    sfilemobiSearch,
    zippyshare
} from '@YosokaHosting/scraper'
// Mediafire
console.log(await mediafiredl('https://www.mediafire.com/file/gpeiucmm1xo6ln0/hello_world.mp4/file'))
// Sfilemobi
console.log(await sfilemobi('https://sfile.mobi/oGm8kAIQCs7'))
// Sfilemobi Search
console.log(await sfilemobiSearch('minecraft'))
// Zippyshare
console.log(await zippyshare('https://www53.zippyshare.com/v/Gajlfjd4/file.html'))
```
- `mediafiredl` use website https://www.mediafire.com
- `sfilemobi` use website https://www.sfilemobi.com
- `sfilemobiSearch` use website https://www.sfilemobi.com
- `zippyshare` use website https://www.zippyshare.com

### Chord 
```js
import {
    chord
} from '@YosokaHosting/scraper'
// Chord
console.log(await chord('Until i found you'))
```
- `chord` use website https://www.gitagram.com

## Breaking Changes
### - from v1.2.1 to v3.1.1
- `savefrom` now output array of object instead of object
- `asmaulhusna` optionally can take `index` parameter to get the asmaulhusna of that index (default is random 1-99)
### - from v3.0.0 to v4.0.0
- `youtubeSearch` videoCount is not on the channel anymore (deleted)
