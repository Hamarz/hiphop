#HipHop [![Dependency Status](https://david-dm.org/hiphopapp/hiphop.svg?theme=shields.io)](https://david-dm.org/hiphopapp/hiphop)

![screenshot](http://gethiphop.net/images/github_screenshot.png)

## How does it work?

When searching, the app will use iTunes and Last.fm to display song results (with cover, title, artist). It will then try to find the best match for this song on Youtube and stream the **highest quality audio stream**.

No torrents, completely decentralized.

## Roadmap

- **Angular.js refactor (*In progress*)**
- Android & iOS apps (with Cordova)
- Easy proxy setup (Youtube is blocked at work for many users)
- Media keys support on desktop (https://github.com/rogerwang/node-webkit/issues/200)
- Internationalization (everyone will be able to help on translations)
- Auto-update
- Sync Playlists & History between all your devices (tough one as we can't use any backend)
- Offline mode for both desktop & mobile apps
- Kick-ass homescreen (with Top tracks in your country, by genres, etc.)

And we should keep focusing on:

- Keeping the app simple
- Improving performance (especially search and playback)
- Fixing bugs
- Providing a clean & attractive design
- Staying decentralized and impossible to take down

What's NOT a priority and why:
- Adding more metadata services: HipHop already provide a huge library (iTunes and Last.fm, combined) that satisfies 99.99% of the users
- Playing local files (most of them are available for streaming anyway)
- Working on anything that would require HipHop to have a backend or some sort of centralized system that could be easily be taken down
- Too advanced features (ex: showing the kbps for the song)

## HipHop on the Web

Here is a list of some of the articles talking about us:
https://github.com/hiphopapp/hiphop/wiki/HipHop-on-the-Web

# Contribute

Join us on IRC at `#hiphopapp` on freenode ([web access](http://webchat.freenode.net/?channels=hiphopapp)).

# Build

### Requirements
    
You will need Grunt:

	$ npm install -g grunt-cli

And Compass to build the stylesheets:

	$ gem install compass

You will also need to install all the node dependencies:

	$ npm install

### Running HipHop

You can easily launch HipHop with:

	$ grunt run

_Note that `grunt build` has to be done at least once before this._

# Known problems

### Error about missing libudev.so.0

Search for libudev.so.0 on your distribution. Most of the time it can be easily fixed by creating a symbolic link from libudev.so to libudev.so.0

See: https://github.com/rogerwang/node-webkit/wiki/The-solution-of-lacking-libudev.so.0
