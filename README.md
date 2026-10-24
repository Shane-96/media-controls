# Media Controls

This fork continues development of Media Controls after the upstream repository was archived. Releases of this fork are published on [GitHub](https://github.com/Shane-96/media-controls/releases).

## What does this extension do?

Show controls and information of the currently playing media in the panel.

## Features

- Customize the extension the way you want it
- Basic media controls (play/pause/next/previous/loop/shuffle/seek)
- Mouse actions lets you run different actions via left/middle/right/scroll.
- Popup with album art and a slider to control the playback
- Scrolling animations
- Blacklist players

---

## How to install

#### Install this fork from GitHub Releases

1. Download `mediacontrols@cliffniff.github.com.shell-extension.zip` from the [latest release](https://github.com/Shane-96/media-controls/releases/latest). Use the attached extension ZIP, rather than GitHub's source code archives.
2. Open a terminal in the directory containing the downloaded file and run:

   ```sh
   gnome-extensions install --force mediacontrols@cliffniff.github.com.shell-extension.zip
   ```

3. Log out and back in, then enable the extension:

   ```sh
   gnome-extensions enable mediacontrols@cliffniff.github.com
   ```

The extension keeps its original UUID so existing settings are preserved. Installing this fork replaces the upstream extension with the same UUID. The [extensions.gnome.org listing](https://extensions.gnome.org/extension/4470/media-controls/) belongs to the upstream project and does not distribute this fork's releases.

---

## Reporting issues

- Make sure your issue isn't a duplicate
- Include the following information when creating the issue,
  - Extension version
  - Gnome version
  - Your distribution
  - A screenshot if it is possible

---

## Development

This project uses Node.js 24 and pnpm 10 for package management and script execution. Building also requires `gnome-extensions`, `glib-compile-resources`, gettext, and zip. On Ubuntu, install the build tools with:

```sh
sudo apt-get install gnome-shell libglib2.0-bin gettext zip
```

### Available Scripts

**Building:**

- `pnpm build` - Build the extension

The installable ZIP is written to `dist/builds/mediacontrols@cliffniff.github.com.shell-extension.zip`.

**Development:**

- `pnpm debug` - Run a nested gnome session for debugging
- `pnpm translations` - Update translation files

**Extension Management:**

- `pnpm run ext:install` - Install the extension
- `pnpm run ext:uninstall` - Uninstall the extension
- `pnpm run ext:enable` - Enable the extension
- `pnpm run ext:disable` - Disable the extension
- `pnpm run ext:prefs` - Open extension preferences

### Quick Start for Contributors

1. Clone the repository
2. Install dependencies: `pnpm install`
3. Build: `pnpm build`
4. Install: `pnpm run ext:install`
5. Log out and back in, then enable the extension: `pnpm run ext:enable`
6. Open preferences to test: `pnpm run ext:prefs`

For active development, use `pnpm debug` to test changes in a nested GNOME session.

### Publishing a release

The version in `src/metadata.json` (`version-name`) is the source of truth. To publish a release:

1. Update `version-name`, commit the changes, and push them to this repository.
2. Create and push a matching tag. For the current version:

   ```sh
   git tag -a v2.4.6 -m "Media Controls 2.4.6"
   git push origin v2.4.6
   ```

The [Release workflow](.github/workflows/release.yml) checks that the tag matches the extension version, builds the installable ZIP, and creates a GitHub Release with the ZIP attached and generated release notes. Tags with a hyphen, such as `v2.4.7-beta.1`, are published as prereleases and must also match `version-name`. The workflow uses GitHub's automatic `GITHUB_TOKEN`; no additional release secrets are required. Releases are published to this GitHub repository.

---

## Get involved

Any type of contribution is appreciated! If you have any suggestions for new features feel free to open a new issue.

If you are interested in translating, download the [po file](assets/locale/mediacontrols%40cliffniff.github.com.pot) and translate it. Then open a pull request with the translated file. You can use [Gtranslator](https://flathub.org/apps/org.gnome.Gtranslator) or [Poedit](https://flathub.org/apps/net.poedit.Poedit) to translate.

If you are interested in contributing code. There are no specific guidelines for contributing. Just make sure you follow the coding style of the project. To update the translation files run `pnpm run translations` in the extensions directory after your changes are done. This will update the files in the locale folder.

<a href="https://github.com/Shane-96/media-controls/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Shane-96/media-controls" />
</a>

Made with [contrib.rocks](https://contrib.rocks).

## Screenshots

#### Popup menu

[<img src="assets/images/popup.png" width="400">]()

#### General settings

[<img src="assets/images/prefs_general.png" width="400">]()

#### Panel settings

[<img src="assets/images/prefs_panel.png" width="400">]()

#### Position settings

[<img src="assets/images/prefs_positions.png" width="400">]()

#### Shortcut settings

[<img src="assets/images/prefs_shortcuts.png" width="400">]()

#### Other settings

[<img src="assets/images/prefs_other.png" width="400">]()
