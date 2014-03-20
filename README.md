#HipHop

## Dependencies

You will need nodejs and grunt:

    $ npm install -g grunt-cli

And ruby with compass to build the stylesheets. Read [this](http://thesassway.com/beginner/getting-started-with-sass-and-compass) for more information.

## Running and debugging

Run at least once to install dependencies and generate JS and CSS files.

    $ npm install
    $ grunt

Run node-webkit from the build/cache directory (--debug always on). Note that grunt build has to be done at least once before this.

    $ grunt run

## Build

Build with:

    $ grunt build

By default it will build for your current platform however you can control that
by specifying a comma separated list of platforms in the `platforms` option to
grunt:

    $ grunt build --platforms=linux32,linux64,mac,win

You can also build for all platforms with:

    $ grunt build --platforms=all

## Release

1. Delete `/build/` folder

2. Update `version` in `/package.json`

3. Update `AppVersion` in `/dist/windows/windows-installer.iss`

4. `$ grunt build --platforms=mac` or just `$ grunt build` if you're on a Mac (the generated `HipHop.app` will be available in `/build/releases/HipHop/mac/`)

5. Compress `/build/releases/HipHop/mac/HipHop.app` to `HipHop-x.x.x.zip`. You have your Mac release!

6. Download latest Windows version of [rogerwang/node-webkit#downloads](https://github.com/rogerwang/node-webkit#downloads) and put all files in `/node-webkit/win/*`

7. Open and Build `/dist/windows/windows-installer.iss` in a Windows environment (requires [Inno Setup](http://www.jrsoftware.org/isdl.php#stable) installed), this will generate `/dist/windows/Install HipHop x.x.x.exe`. You have your Windows installer!

8. Upload both files to `http://download.gethiphop.net/releases/x.x.x/[mac|win]/`

9. Update `/misc/update.json` accordingly and upload to `http://gethiphop.net/update.json` (*ONLY* when both releases are available for download)