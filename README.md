# ShadowsocksX-NG

Current version is 1.3

[![Build Status](https://travis-ci.org/qiuyuzhou/ShadowsocksX-NG.svg?branch=develop)](https://travis-ci.org/qiuyuzhou/ShadowsocksX-NG)

Next Generation of [ShadowsocksX](https://github.com/shadowsocks/shadowsocks-iOS)

## Why?

It's hard to maintain the original implement. There are too many unused code in it.
It also embed ss-local source. It's crazy to maintain depandences of ss-local.
So it's hard to update ss-local version.

Now I just copy the ss-local from home brew. Run ss-local executable as a Launch Agent in background.
Serve PAC file via local HTTP server. So there are only some source code related to GUI left.
Then I rewrite the GUI code in Swift.

## Requirements

### Running

- macOS 10.11+

### Building

- Xcode 8.0+
- CocoaPods 1.0.1+

## Features

- Use ss-local from shadowsocks-libev 2.4.6
- Update PAC by downloading GFW List from GitHub
- Show QR code for current server profile
- Scan QR code from screen
- Auto launch at login
- User rules for PAC
- Support OTA updates
- An advanced preferences panel to configure:
  - Local SOCKS5 listen address
  - Local SOCKS5 listen port
  - Local SOCKS5 timeout
  - Enable UDP relay
  - GFW List URL
- Manual specify network service profiles for proxy configuration
- Reorder Shadowsocks profiles by drag & drop in the servers preferences panel

## Different from original ShadowsocksX

Run ss-local as a background service through launchd, not in the app process.
So after you quit the app, ss-local may still be running.

Add a manual mode which won't configure the system proxy settings.
Then you can configure your apps to use the SOCKS5 proxy manually.

## Contributing

Contributions must be available on a separately named branch based on the latest version of the main branch `develop`.

Ref: [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/)

## TODO

- [ ] Embed the HTTP proxy server [Privoxy](http://www.privoxy.org/)

## License

Released under the terms of GPLv3.
