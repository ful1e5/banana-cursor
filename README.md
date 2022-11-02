# banana-cursor

The banana cursor.

[![build](https://github.com/ful1e5/banana-cursor/actions/workflows/build.yml/badge.svg)](https://github.com/ful1e5/banana-cursor/actions/workflows/build.yml)

## Banana Cursor needs your Input

Until 2021 my cursors projects were well funded by [pling.com](https://www.pling.com) but since the
[pling-factor](https://www.pling.com/terms/payout) on the website has decreased and monthly payments
are <500$, It is now dependent on community funding and sponsorships. If you want to help me to maintain
Banana Cursor and my other open source projects actively, consider sponsoring my work on [GitHub Sponsor](https://github.com/sponsors/ful1e5)
or DM me on [Twitter](https://twitter.com/ful1e5) if your company would like to support my projects,
I will gladly look into it and post your avatar in the project's README.

I appreciate all the wonderful people who patronize and sponsoring my work.

## Sponsors

<!-- Add your name or avatar here with the Pull Request in case I missed it. -->

N/A

---

![Banana](https://imgur.com/pCoon2Q.png)

> **Note**
> All cursor's `.svg` files are found in [svg](./svg) directory or you can also find them on
> [Figma](https://www.figma.com/file/rL9ngfrDJbXqNW4pUESANY/banana-cursor?node-id=0%3A1).

#### Cursor Sizes

<kbd>22</kbd>
<kbd>24</kbd>
<kbd>28</kbd>
<kbd>32</kbd>
<kbd>40</kbd>
<kbd>48</kbd>
<kbd>56</kbd>
<kbd>64</kbd>
<kbd>72</kbd>
<kbd>80</kbd>
<kbd>88</kbd>
<kbd>96</kbd>

## Cursor Sizes

### Xcursor Sizes:

<kbd>22</kbd>
<kbd>24</kbd>
<kbd>28</kbd>
<kbd>32</kbd>
<kbd>40</kbd>
<kbd>48</kbd>
<kbd>56</kbd>
<kbd>64</kbd>
<kbd>72</kbd>
<kbd>80</kbd>
<kbd>88</kbd>
<kbd>96</kbd>

### Windows Cursor Size:

- <kbd>16x16</kbd> - Small
- <kbd>24x24</kbd> - Regular
- <kbd>32x32</kbd> - Large
- <kbd>48x48</kbd> - Extra Large

## How to get it

### Easiest Way

You can download latest `stable` & `development` releases from
[Release Page](https://github.com/ful1e5/banana-cursor/releases).

## Installing Banana Cursor

#### Linux/X11

**Installation:**

```bash
tar -xvf Banana.tar.gz                   # extract `Banana.tar.gz`
mv Banana ~/.icons/                      # Install to local users
sudo mv Banana /usr/share/icons/         # Install to all users
```

**Uninstallation:**

```bash
rm ~/.icons/Banana                       # Remove from local users
sudo rm /usr/share/icons/Banana          # Remove from all users
```

#### Windows

**Installation:**

1. Unzip `.zip` file
2. Open unziped directory in Explorer, and **right click** on `install.inf`.
3. Click 'Install' from the context menu, and authorize the modifications to your system.
4. Open Control Panel > Personalization and Appearance > Change mouse pointers,
   and select **Banana Cursors**.
5. Click '**Apply**'.

**Uninstallation:**

Run the `uninstall.bat` script packed with the `.zip` archive

**OR** follow these steps:

1. Go to **Registry Editor** by typing the same in the _start search box_.
2. Expand `HKEY_CURRENT_USER` folder and expand `Control Panel` folder.
3. Go to `Cursors` folder and click on `Schemes` folder - all the available custom cursors that are
   installed will be listed here.
4. **Right Click** on the name of cursor file you want to uninstall; for eg.: _Banana Cursors_ and

## Build From Source

#### Notes

- Banana build configuration and cursor hotspot settings are bundled in the `build.toml` file.
- Check out the scripts section in [package.json](./package.json) to see how we build the cursor theme,
  excluding the render scripts. They are useful for converting `.svg` files to `.png` files.
- yarn is optional, For building XCursors and Windows cursors from `.png` files or resizing them
  you don't need that. If you want to develop/modify Banana's colors, and bitmaps, or generate a png
  file from a svg, Then you can use yarn because bitmapper is written in TypeScript.

### Build prerequisites

- Python version 3.7 or higher
- [clickgen](https://github.com/ful1e5/clickgen)>=2.1.2 (`pip install clickgen`)
- [yarn](https://github.com/yarnpkg/yarn)

### Quick start

1. Install [build prerequisites](#build-prerequisites) on your system
2. `https://github.com/ful1e5/banana-cursor`
3. `cd banana-cursor && yarn build`
4. See [Installing Banana Cursor](#installing-banana-cursor).
   click `Delete`.
5. Click '**yes**' when prompted.

### Building

> **Note**
> Bitmaps are already generated in the `bitmaps` directory and **managed by the maintainer**
> (do not edit them directly).

First make sure you installed the [build prerequisites](#build-prerequisites).
Now that you have the dependencies, you can try build individual themes from bitmaps and
customize sizes, target platform, and etc. with the `ctgen` CLI (packed with `clickgen`).

#### `yarn build` aberration

Here are the default commands we used to build the Banana-cursor and packed them into `yarn build`:

```bash
ctgen build.toml
```

Afterwards, the themes can be found in the `themes` directory.

#### Customize Sizes

> **Note**
> You can change the cursor size up to 200 because pngs are rendered with 200x200.
> If the cursor is resized by more than rendered png size, the final cursor will be blurred.

##### Customize Windows Cursor size

To build Windows cursor with size `16`:

> **Warning**
> Windows cursor supports only one size, if multiple sizes are given with `-s` the first size will
> be considered in build.

```bash
ctgen build.toml -s 16 -p windows -c 'Banana cursors with size 16'
```

You can also customize output directory with `-o` option:

```bash
ctgen build.toml -s 16 -p windows -o 'out' -c 'Banana cursors with size 16'
```

##### Customize XCursor size

To build XCursor with size `16`:

```bash
ctgen build.toml -s 16 -p x11 -c 'Banana cursors with size 16'
```

You can also assign multiple sizes to `ctgen` for XCursors build:

```bash
ctgen build.toml -s 16 24 32 -p x11 -c 'Banana cursors with size 16'
```

# Bugs

Bugs should be reported [here](https://github.com/ful1e5/banana-cursor/issues) on the Github issues page.

# Getting Help

You can create a **issue**, I will help you.
