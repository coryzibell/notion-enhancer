# <img src="./mods/core/icons/mac+linux.png" height="20px"></img> notion-enhancer

notion.so is a pretty awesome tool already, but there's always room for improvements.
it might just be a preference, it might be something crucial to your setup,
it might be something users have been asking for for a long time,
or it might even be something you haven't realised you need yet
\- there's something that would make your user experience a lot better.

this package is a mod-loader for the desktop app, with custom colour theming and extra feature enhancements.

want to contribute? check out the [contribution guidelines](CONTRIBUTING.md) and the [documentation](DOCUMENTATION.md).

for support, join the [discord server](https://discord.gg/sFWPXtA).

### supported desktop clients

- the [official windows/mac releases](https://notion.so/desktop).
- the arch linux AUR [notion-app](https://aur.archlinux.org/packages/notion-app/) package.
- the linux [notion-app](https://github.com/jaredallard/notion-app) installer.

(it can also be run from the wsl to apply enhancements to the windows app.)

**using a not-yet-supported operating system or notion installation?** ask for
[platform support](https://github.com/dragonwocky/notion-enhancer/issues/new?labels=enhancement&template=platform-support.md).

mobile clients are not supported and due to system limitations/restrictions cannot be.

a chrome extension may be coming soon for web client support.

## installation

> coming from <= v0.7.0? things are a bit different - have a read of [the update guide](UPDATING.md)
> before following these instructions.

during installation/removal, make sure no notion processes are running! (check your task manager.)

**win10, macOS**

1. [install node.js](https://nodejs.org/en/download/) (_a computer restart may be required here._)
2. execute `npm i -g notion-enhancer` in the terminal/command prompt as a root/admin user.

**debian/ubuntu, chromeOS, WSL (to modify the win10 app)**

execute the following lines in the terminal:

```
bash curl -sL https://deb.nodesource.com setup_current.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm i -g notion-enhancer
```

**arch linux, manjaro**

install the [aur package](https://aur.archlinux.org/packages/notion-enhancer)
with your aur helper (e.g. `yay -S notion-enhancer`).

### command-line interface

the enhancements should be automatically applied on installation
and automatically removed on uninstallation.

on some platforms this may throw errors if done without
elevated/admin permissions, though, so if it hasn't automatically
installed you will still need to use these commands.

```
Usage:
  $ notion-enhancer <command> [options]

Commands:
  apply   : add enhancements to the notion app
  remove  : return notion to its pre-enhanced/pre-modded state
  check   : check the current state of the notion app

For more info, run any command with the `--help` flag:
  $ notion-enhancer apply --help
  $ notion-enhancer remove --help
  $ notion-enhancer check --help

Options:
  -y, --yes      : skip prompts (may overwrite data)
  -d, --dev      : show detailed error messages (not recommended)
  -h, --help     : display usage information
  -v, --version  : display version number
```

**is this against notion's terms of service? can i get in trouble for using it?**

definitely not! i contacted their support team to check, and the response was awesome:

"Thanks for taking the time to share this with us. Userscripts and userstyles are definitely
cool ideas and would be helpful for many users! ... I'll also share this with the rest of the
team to take to heart for future improvements."

## features

once applied, modules can be configured via the graphical menu, which is opened from
the tray/menubar icon or with `ALT+E`.

![](https://user-images.githubusercontent.com/16874139/91446210-84ee6b00-e8ba-11ea-9f40-187a150e4a82.png)

currently all modules come pre-installed for technical reasons, security assurance, and ease-of-use.
these include:

### notion-enhancer core

**tags:** #core

**description:** the cli, modloader, menu, & tray.

**author**: [dragonwocky](https://github.com/dragonwocky/)

| option                       | type                                                                                          | default                    |
| ---------------------------- | --------------------------------------------------------------------------------------------- | -------------------------- |
| hide app on open             | toggle                                                                                        | no                         |
| auto-maximise windows        | toggle                                                                                        | no                         |
| close window to the tray     | toggle                                                                                        | yes                        |
| integrated titlebar          | toggle                                                                                        | yes                        |
| height of frameless dragarea | number input                                                                                  | `15`                       |
| integrated scrollbars        | toggle                                                                                        | yes                        |
| window display hotkey        | [accelerator](https://github.com/electron/electron/blob/master/docs/api/accelerator.md) input | `CommandOrControl+Shift+A` |

![](https://user-images.githubusercontent.com/16874139/90519171-094e3900-e1ab-11ea-8c5d-529ca15c6d95.png)

### custom inserts

**tags:** #extension

**description:** link files for small client-side tweaks.

**author**: [dragonwocky](https://github.com/dragonwocky/)

| option                | type | default |
| --------------------- | ---- | ------- |
| css insert            | file | none    |
| client-side js insert | file | none    |

### bracketed links

**tags:** #extension

**description:** render links surrounded with \[\[brackets]] instead of underlined.

**author**: [arecsu](https://github.com/arecsu/)

### dark+

**tags:** #theme #dark

**description:** a vivid-colour near-black theme.

**author:** [dragonwocky](https://github.com/dragonwocky/)

| option         | type  | default            |
| -------------- | ----- | ------------------ |
| primary colour | color | `rgb(177, 24, 24)` |

![](https://user-images.githubusercontent.com/16874139/90520312-85954c00-e1ac-11ea-8c45-3894c13b9b71.png)

### emoji sets

**tags:** #extension

**description:** pick from a variety of emoji styles to use.

**author:** [dragonwocky](https://github.com/dragonwocky/)

![](https://user-images.githubusercontent.com/16874139/90520622-f0df1e00-e1ac-11ea-8791-12922a037234.png)

### focus mode

**tags:** #extension

**description:** hide the titlebar/menubar if the sidebar is closed (will be shown on hover).

**author:** [arecsu](https://github.com/arecsu/)

![](https://user-images.githubusercontent.com/16874139/90521792-49fb8180-e1ae-11ea-8764-cb4309cec464.png)

### gameish

**tags:** #theme #dark

**description:** a purple, "gamer-styled" theme with a blocky-font.

**author:** [LVL100ShrekCultist](https://reddit.com/user/LVL100ShrekCultist/)

![](https://user-images.githubusercontent.com/16874139/90522144-b6768080-e1ae-11ea-8150-527c1f70f0e7.png)

### hide help button

**tags:** #extension

**description:** hide the help button if you don't need it

**author**: [coryzibell](https://github.com/coryzibell/)

### neutral

**tags:** #theme #dark

**description:** smoother colours and fonts, designed to be more pleasing to the eye.

**author:** [arecsu](https://github.com/arecsu/)

![](https://user-images.githubusercontent.com/16874139/90522373-f9d0ef00-e1ae-11ea-9dba-b29431609210.png)

### night shift

**tags:** #extension #theme

**description:** sync dark/light theme with the system (overrides normal theme setting).

**author:** [dragonwocky](https://github.com/dragonwocky/)

### pastel dark

**tags:** #theme #dark

**description:** a true dark theme with a hint of pastel.

**author:** [zenith_illinois](https://reddit.com/user/zenith_illinois/)

![](https://user-images.githubusercontent.com/16874139/90522660-5502e180-e1af-11ea-8885-073ad20d65b3.png)

### property layout

**tags:** #extension

**description:** auto-collapse page properties that usually push down page content.

**author:** [alexander-kazakov](https://github.com/alexander-kazakov/)

### right-to-left

**tags:** #extension

**description:** enables auto rtl/ltr text direction detection.

**author:** [obahareth](https://github.com/obahareth/)

![](https://user-images.githubusercontent.com/16874139/90522872-95faf600-e1af-11ea-807c-11ac1591217e.png)

### weekly view

**tags:** #extension

**description:** calendar views named "weekly" will show only the 7 days of this week.

**author:** [adihd](https://github.com/adihd/)

![](https://user-images.githubusercontent.com/16874139/90523679-86c87800-e1b0-11ea-8cc0-25f6825c6d49.png)

## contributors

[@TarasokUA](https://github.com/TarasokUA/) wrote the first versions of this in python, in early 2020.
a couple months after I ([@dragonwocky](https://github.com/dragonwocky/)) picked the project up, at first extending
upon the original base and later moving to the javascript module system.

since then, various community members have helped out heaps - some listed as
[contributors](https://github.com/dragonwocky/notion-enhancer/graphs/contributors) here on github,
but many helping with code, feedback and testing on discord and in emails.

individual modules have their original authors attributed.
