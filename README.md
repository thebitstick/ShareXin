## Submit more languages using this [form](https://goo.gl/forms/rNx4yAB9KM2fDXDG3)

# ShareXin  

[![GitHub Stars](https://img.shields.io/github/stars/thebitstick/ShareXin.svg?)](https://github.com/thebitstick/ShareXin)
[![Crates.io](https://img.shields.io/crates/v/sharexin.svg)](https://crates.io/crates/sharexin)

## Requirements
* Linux or FreeBSD
* rustc 1.30.0^
* *scrot* (only need if `gnome-screenshot` not installed)
* *feh* (only need if `spectacle` is not installed or using GNOME Wayland)

## Features
* Takes screenshots
* Uploads to Twitter, Mastodon, and Imgur
* Saves screenshots to your Pictures
* Notifications
* GTK Dialog for entering a message with a tweet or toot
* Designed with **Wayland** in mind

### Desktop support
- GNOME desktop
- KDE Plasma desktop
- Budgie desktop
- Cinnamon desktop
- Unity desktop
- Any X11 DE

### Tested on
- Ubuntu 18.10
- Debian 9.5.0
- Fedora 29
- Arch Linux
- GhostBSD (FreeBSD distro)

## `--help`

## Language support
* English
* Français (French) by [@Eleoryth](https://twitter.com/Eleoryth)
* Español (Spanish)
* Esperanto
* 简体中文 (Simplified Chinese)
* 繁體中文 (Traditional Chinese)
* 日本語 (Japanese)
* 한국어 (Korean)
* Deutsch (German) by [@qwertxzy](https://twitter.com/qwertxzy)
* Polski (Polish) by [@Michcioperz](https://twitter.com/Michcioperz)
* Português (Portuguese) by [@pillgp](https://twitter.com/pillgp)

## Compiling

#### Ubuntu 18.04 dependencies
* libgtk-3-dev
* libcairo2-dev
* libpango1.0-dev
* libgdk-pixbuf2.0-dev
* libatk1.0-dev
* libssl-dev
* libcurl4-openssl-dev
* libclang-dev
* build-essential

#### Debian 9.5.0 dependencies
* libgtk-3-dev
* libcairo2-dev
* libpango1.0-dev
* libgdk-pixbuf2.0-dev
* libatk1.0-dev
* libssl-dev
* libcurl4-openssl-dev
* libclang-dev
* build-essential

#### Arch Linux dependencies
* curl
* gtk3
* gdk-pixbuf2
* cairo
* glib2
* openssl
* dbus
* xcb-util
* base-devel
* clang

#### Fedora 29 dependencies
* gtk3-devel
* cairo-devel
* pango-devel
* gdk-pixbuf2-devel
* atk-devel
* openssl-devel
* libcurl-devel
* clang-devel

#### FreeBSD 11 dependencies
* openssl-devel
* gmake
* gcc
* dbus-glib
* devel/dbus
* gtk3
* devel/glib20 (via ports)
* cairo
* pango
* gdk-pixbuf2
* atk
* openssl
* curl

### Compiling
1. `git clone https://github.com/ShareXin/ShareXin/`
2. `cargo install`

**OR**
1. `cargo install sharexin`

## Changelog
#### [0.6.8] - 2018-10-27
- Moved anything in `cmd.rs` to `main.rs` (main only called cmd anyways)
- Reorganized things to accomodate for Flatpaks
- Added Flatpak!!!

#### [0.6.7] - 2018-10-21
- Colors for character count on message popup match colors on Twitter Web
- Character count on message popup turns yellow when approaching limit with 20 characters left, just like on Twitter Web
- Didn't know `unreachable!("")` was a thing, replaced some instances of `panic!()` with it
- Removed useless `error::fatal()` message
- Disabling *"Ok"* button when no text is entered or when too much text is over service limit
- Removed "File saved" notification, not really needed
- Updated dependencies
- Debian is actually compatible **(had to regress from 3_22_30 of gtk-rs to 3_18)**
- Better comments
- `--upgrade` removed due to issues with openssl
- Character count only changes when keys are pressed in the TEXT Box, not the entire window
- Made `error.rs` actually readable
- Notifications for a sent image or status tweet/toot or Imgur post only last 2 seconds

#### [0.6.6] - 2018-10-31
- More testing done
- Removed some strange and unneccesary lines
- Removed lots of duplicate code
- Replaced many if else statements with match statements
- AppImage script provided
- General bug fixes
- Split screenshotting functionality off to [screenshot-rs](https://github.com/ShareXin/screenshot-rs)
- Removed swaywm support (even back when I used it, my implementation was trash, if any this is a service to sway users)
- Removed RefCell in `dialog.rs`
- Updated Twitter character limit (not full proof for non-Latin characters)
- Heavy rewrite of functions with clearer variables
- Old Twitter API restored for functionality, will be replaced by native API in a later update

#### [0.6.5] - 2018-09-26
- Work will continue on the project!
- Updated GNOME deps to 3_22_30 from 3_10
- Removed macOS support (how many people even used it?)
- Removed tray icon support (unneeded and unusable, GNOME doesn't even support it anymore)
- Updated various dependencies
- Removed ShareXin as a library
- Readded ShareXin to crates.io
- Added Subfolder under ShareXin in Pictures for sorting by years-month
- Rewrote method of determining screenshot selection software
  - Used to rely on hard-coded desktop variables to match with specific software
  - Now simply checks which software is installed, in a prefered order
- `t` and `toot` are still required for use with Twitter and Mastodon, but this WILL be addressed in 0.6.6
  - Native rust Twitter and Mastodon APIs will be added, with hopefully the same functionality.

#### [0.6.4] - 2018-03-30
- Wow this project keeps going
- Added Portuguese translation

#### [0.6.3] - 2017-10-19
- Added support for Ubuntu 17.10 Gnome Desktop (congrats on upgrading to the future)

#### [0.6.2] - 2017-09-01
- System tray support (not for Mac)
- New slogan, guaranteed to work on Linux, FreeBSD, and macOS only
- Makefile and PKGBUILD
- Better command line parsing with clap-rs
- ShareXin library? I guess?

#### [0.6.1] - 2017-08-26
- XDG Directory for Pictures folder (switched my system to French, directories changed)

#### [0.6.0] - 2017-08-25
- macOS tested, Imgur works, `t` and `toot` should work if you have them
- Updated "upgrade" and error messages
- Figured out libcurl issue on some older systems
- Bug fixes

#### [0.5.9] - 2017-08-20
- ImageMagick integrated
- `killall vim` finally removed (kinda)!

#### [0.5.8] - 2017-08-20
- Imgur link now copied to clipboard _(should work on Wayland?)_
- Better desktop recognition
- Bug fixes

#### [0.5.7] - 2017-08-19
- Less repetitive code
- Area screenshots (except for KDE and Mac) use two separate files,
the frozen fullscreen and the part of it you select
- Fixed bug where Error 29 would always print (kind of a bug)

#### [0.5.6] - 2017-08-19
- Removes temporary file after sending it
- Budgie Desktop support
- Ubuntu Unity Desktop support
- Theoretical Mac support

#### [0.5.5] - 2017-08-18
- Added Polish translation
- Character count acts like ShareX, counts down from 140 or 500 (depending on destination)
- "File Saved" notification now includes image saved

#### [0.5.4] - 2017-08-17
- Just a Cargo fix, ignore

#### [0.5.3] - 2017-08-15
- Now packaging `t` (should work)
- Added `auth` option for Twitter and Mastodon

#### [0.5.2] - 2017-08-15
- GTk fixes
- Notification for error messages
- Bug fixes
- Now using AppImage for releases

#### [0.5.1] - 2017-08-14
- No more wildcards in getting modules
- Separated `language.rs`
- Now using scrot rather than maim
- `.kill()` exists for `Command`, no longer using killall feh
- Added Fatal error messages
- Cinnamon desktop support

#### [0.5.0] - 2017-08-13
- Rewrite of Language message system, now using templates, extremely easy to add more languages
- Bug fixes

#### [0.4.9] - 2017-08-12
- Lots of optimizations
- Actual bug fixes
- Better error messages
- `format!` is a thing
- `gnome-screenshot` has native shadow effects for windows
- Really dumb [seg](https://github.com/thebitstick/ShareXin/blob/db4b202d30eecb160b2e4db4fbd4f03f918ba4da/src/language.rs#L25) [fault](https://github.com/thebitstick/ShareXin/blob/db4b202d30eecb160b2e4db4fbd4f03f918ba4da/src/error.rs#L38)
- Less code, actually
- Less comments, cause "comments are bad"

#### [0.4.8] - 2017-08-11
- Stderr used for errors
- Returns for String methods rather than variables
- Completely remade the help function, universal syntax
- Bug fixes

#### [0.4.7] - 2017-08-09
- Character count now shows when you've hit the limit and when you've passed
the limit
- Rather than crashing, if notify-rust is unable to show you a notification,
it'll display an error message and exit nicely
- Added French error messages
- Bug fixes

#### [0.4.6] - 2017-08-09
- Error messages now translated
- When uploading an image to Twitter, the character limit is reduced to 117, just like on ShareX
- Less panicking
- Less repetitiveness
- t and toot now show notification if command fails to run (API troubles or no internet), rather than just showing you the "Sent" notification
- Bug fixes
- **Known issue**: In order to get t working correctly without a terminal, it must `killall vim`, so consider it a feature-bug

#### [0.4.5] - 2017-08-07
- BSD support, tested on FreeBSD with Xfce
- Rather than panicking, ShareXin exits with an error message
- Cleaner command line parsing
- Error messages now multi-lingual, that is if the error doesn't include $LANG
- Bug fixes

#### [0.4.4] - 2017-08-04
- Untested Mac notifications
- Shadows only added to Window screenshots
- Mac screenshot support coming soon
- Bug fixes? Cleaner code? Maybe

#### [0.4.3] - 2017-08-03
- Bug fixes
- Cleaner code

#### [0.4.1] - 2017-08-02
- Partial Wayland support for Gnome, Plasma, and Sway
- Gnome-Screenshot used on Gnome
- Spectacle used on Plasma/KDE
- Swaygrab used on Sway (i3-clone)

#### [0.4.0] - 2017-08-01
- Cursor hidden in all screenshots
- Removed double shadow
- Bug fixes

#### [0.3.9] - 2017-07-31
- Bug fixes

#### [0.3.8] - 2017-07-30
- Better struct management
- Imgur support! Opens image in browser
- Changed date variable (had to change it manually everytime

#### [0.3.7] - 2017-07-29
- Custom error handles
- Added experimental `open` Image Option, lets you select an image (animated or not) or possibly a video and send to a destination
- Update checker implemented properly
- Fixed service variables, now using structs
- Readying code for more destinations
- `auth` option not working at this current moment in time due to immature twitter apis available for Rust
- `imgur` option hints at what will be the next Destination

#### [0.3.6] - 2017-07-28
- Character count now turns red when over the limit
- You can't send a toot or tweet if it's over the limit
- Double the ImageMagick shadow
- No longer using Pipers crate
- Changed those weird "mort" and "morti" variables
- Commented most of the code, cleaned up

#### [0.3.5] - 2017-07-27
- Added button to check your image
- Added upgrade checker
- Added character count
- Beautified code
- New command line args

#### [0.3.4] - 2017-07-26
- Window screenshot adds shadow
- Separated main.rs function gui()

#### [0.3.3] - 2017-07-26
- New UI thanks to Glade
- Notifications now have language support
- Pressing Control+Return sends your message
- Native Buttons, language changes!

#### [0.3.2] - 2017-07-25
- Cleaned help messages, used GNU coreutil messages for some items

#### [0.3.1] - 2017-07-25
- Separated main.rs into {main, help, file, send}.rs, less scrolling

#### [0.3.0] - 2017-07-25
- Die Deutsche Sprache!
- Falsche Kompilierungsdatum

#### [0.2.9] - 2017-07-25
- Multaj Lingovj! Added French, Spanish, Esperanto, and Japanese translations for --help!

#### [0.2.8] - 2017-07-25
- Maim replacing Gnome-screenshot
- Shadow added to area screenshots using ImageMagick
- Notification adds back tweet text

#### [0.2.7] - 2017-07-24
- Notifications via libnotify (bye bye dbus)
- Username gotten by $USER var, rather than an entire library (thanks std!)

#### [0.2.6] - 2017-07-23
- Forgot to update the version # for 0.2.5 from 0.2.4 and Crates wouldn't allow a reupload so....

#### [0.2.5] - 2017-07-23
- Better word wrap
- Better temp dir
- Notification actually shows image now

#### [0.2.4] - 2017-07-21
- Added version info
- Made --help prettier

#### [0.2.3] - 2017-07-21
- Send button now says Toot or Tweet depending on where you're going
- TextView no longer accepts tabs

#### [0.2.2] - 2017-07-21
- TextView now word wraps
- Ability to simply just tweet without an image
- Mort

#### [0.2.1] - 2017-07-20
- Centered window (why isn't .set_position() IN THE DOCS)

#### [0.2.0] - 2017-07-20
- Uh, if you're haven problems with t not loadin', check your $PATH

#### [0.1.0] - 2017-07-19
- Bug fixes and improvements

#### [0.0.0] - 2017-07-19
##### Added
- First commit
