# banana-cursor

A cursor was requested by [u/JMT37](https://www.reddit.com/user/JMT37/). It is the most unique cursor ever crafted in Linux history.

[![build](https://github.com/ful1e5/banana-cursor/actions/workflows/build.yml/badge.svg)](https://github.com/ful1e5/banana-cursor/actions/workflows/build.yml)

## Notes

-   All cursor's SVG files are found in [svg](./svg) directory or you can also find them on [Figma](https://www.figma.com/file/rL9ngfrDJbXqNW4pUESANY/banana-cursor?node-id=0%3A1).

<!-- If you're interested, you can learn more about "sponsor-spotlight" on
 https://dev.to/ful1e5/lets-give-recognition-to-those-supporting-our-work-on-github-sponsors-b00 -->

![shoutout-sponsors](https://sponsor-spotlight.vercel.app/sponsor?login=ful1e5)

-   **2024-07-21**: [04eb3aa](https://github.com/ful1e5/banana-cursor/commit/04eb3aa80d76c3e27d2e5870de3cb57b19b69a61) Partitioned cursor build configuration into multiple files according to platform:
    `build.toml` -> `configs/win_lg.build.toml`, `configs/win_rg.build.toml`, `configs/win_xl.build.toml`, `configs/x.build.toml`.

---

![Banana](https://github.com/user-attachments/assets/02ae34f7-f555-447a-aeab-35297d0711ac)
![Banana Green](https://github.com/user-attachments/assets/7ca834fd-369d-4c09-956d-dd7b15177c2a)
![Banana Blue](https://github.com/user-attachments/assets/4af7e734-c2d3-4cf6-9986-68b44f7e1ea2)
![Banana Red](https://github.com/user-attachments/assets/19316c10-1bca-424e-a85f-7472a2080af4)

## Cursor Sizes

### Xcursor Sizes:

<kbd>16</kbd>
<kbd>20</kbd>
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

| size | Regular (× ²⁄₃) | Large (× ⁴⁄₅) | Extra-Large (× 1) |
| ---: | --------------: | ------------: | ----------------: |
|   32 |     21.333 → 22 |     25.6 → 26 |                32 |
|   48 |              32 |     38.4 → 39 |                48 |
|   64 |     42.666 → 43 |     51.2 → 52 |                64 |
|   96 |              64 |     76.8 → 77 |                96 |
|  128 |     85.333 → 86 |   102.4 → 103 |               128 |

## Colors

### Banana

-   Base Color - `#FCD900` (Yellow)
-   Outline Color - `#6D3C1B` (Brown)

### Banana Green

-   Base Color - `#54F851` (Green)
-   Outline Color - `#0C2608` (Dark Green)

### Banana Blue

-   Base Color - `#64CDCD` (Blue)
-   Outline Color - `#0E2026` (Dark Blue)

### Banana Red

-   Base Color - `#E16C6C` (Red)
-   Outline Color - `#1B0707` (Dark Red)

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
   click `Delete`.
5. Click '**yes**' when prompted.

## Build From Source

### Prerequisites

-   Python version 3.7 or higher
-   [clickgen](https://github.com/ful1e5/clickgen)>=2.2.5 (`pip install clickgen`)
-   [yarn](https://github.com/yarnpkg/yarn)

### Quick start

1. Install [build prerequisites](#prerequisites) on your system
2. `git clone https://github.com/ful1e5/banana-cursor`
3. `cd banana-cursor`
4. `yarn install`
5. `yarn generate`
6. See [Installing Banana Cursor](#installing-banana-cursor).

### Getting Started

Once you have the [build prerequisites](#prerequisites) installed, You can personalize colors,
customize sizes, change target platforms, and more. This process involves using external tools,
as this repository only contains SVG files and configuration for these tools:

-   [cbmp](https://github.com/ful1e5/cbmp): Used for customizing colors and generating PNG files.
-   [ctgen](https://github.com/ful1e5/clickgen): Used for customizing sizes and building XCursor and Windows Cursors.

You can refer to the README of each tool for more information on their command-line options.

#### Crafting Your Banana Cursor

The process of creating custom cursor themes involves two main steps:

1. Rendering SVG files to PNG files.
2. Building cursor themes from PNG files.

#### Customize Colors

`cbmp` provides three options for changing colors:

1. `-bc`: Base color, which replaces the `#00FF00` color in the SVG.
2. `-oc`: Outlined color, which replaces the `#0000FF` color in the SVG.
3. `-wc` (optional): Watch Background color, which replaces the `#FF0000` color in the SVG.

```bash
npx cbmp [...] -bc "<hex>" -oc "<hex>" -wc "<hex>"
```

Alternatively, you can provide a JSON configuration file to render SVG files, which contains a sequence of `cbmp` commands:

```bash
npx cbmp render.json
```

#### Customize Sizes

##### Customize Windows Cursor size

To build Windows cursor with size `16`:

```bash
ctgen configs/x.build.toml -s 16 -p windows -d "bitmaps/Banana" -n "Banana" -c "The Banana XCursors with size 16"
```

You can also customize output directory with `-o` option:

```bash
ctgen configs/win_xl.build.toml -s 16 -p windows -d "bitmaps/Banana" -o "out" -n "Banana" -c "The Banana Windows Cursors with size 16"
```

##### Customize XCursor size

To build XCursor with size `16`:

```bash
ctgen configs/x.build.toml -s 16 -p x11 -d "bitmaps/Banana" -n "Banana" -c "The Banana XCursors with size 16"
```

You can also assign multiple sizes to `ctgen` for XCursors build:

```bash
ctgen configs/x.build.toml -s 16 18 24 32 -p x11 -d "bitmaps/Banana" -n "Banana" -c "The Banana XCursors with size 16"
```

#### Examples

Lets generate Banana Cursor with green and black colors:

```bash
npx cbmp -d "svg" -o "bitmaps/Banana-Hacker" -bc "#00FE00" -oc "#000000"
```

After rendering custom color you have to build cursor through `ctgen`:

```bash
ctgen configs/x.build.toml -d "bitmaps/Banana-Hacker" -n "Banana-Hacker" -c "Green and Black Banana XCursors."
```

Afterwards, Generated theme can be found in the `themes` directory.

###### Banana Gruvbox

```bash
npx cbmp -d "svg" -o "bitmaps/Banana-Gruvbox" -bc "#282828" -oc "#EBDBB2"

ctgen configs/x.build.toml -d "bitmaps/Banana-Gruvbox" -n "Banana-Gruvbox" -c "Groovy Banana XCursors."
ctgen configs/win_rg.build.toml -d "bitmaps/Banana-Gruvbox" -n "Banana-Gruvbox" -c "Groovy Banana Windows Regular Cursors."
ctgen configs/win_lg.build.toml -d "bitmaps/Banana-Gruvbox" -n "Banana-Gruvbox" -c "Groovy Banana Windows Large Cursors."
ctgen configs/win_xl.build.toml -d "bitmaps/Banana-Gruvbox" -n "Banana-Gruvbox" -c "Groovy Banana Windows Extra Large Cursors."
```

###### Banana Solarized Dark

```bash
npx cbmp -d "svg" -o "bitmaps/Banana-Solarized-Dark" -bc "#002b36" -oc "#839496"

ctgen configs/x.build.toml -d "bitmaps/Banana-Solarized-Dark" -n "Banana-Solarized-Dark" -c "Solarized Dark Banana XCursors."
ctgen configs/win_rg.build.toml -d "bitmaps/Banana-Solarized-Dark" -n "Banana-Solarized-Dark" -c "Solarized Dark Banana Windows Regular Cursors."
ctgen configs/win_lg.build.toml -d "bitmaps/Banana-Solarized-Dark" -n "Banana-Solarized-Dark" -c "Solarized Dark Banana Windows Large Cursors."
ctgen configs/win_xl.build.toml -d "bitmaps/Banana-Solarized-Dark" -n "Banana-Solarized-Dark" -c "Solarized Dark Banana Windows Extra Large Cursors."
```

###### Banana Solarized Light

```bash
npx cbmp -d "svg" -o "bitmaps/Banana-Solarized-Light" -bc "#839496" -oc "#002b36"

ctgen configs/x.build.toml -d "bitmaps/Banana-Solarized-Light" -n "Banana-Solarized-Light" -c "Solarized Light Banana XCursors."
ctgen configs/win_rg.build.toml -d "bitmaps/Banana-Solarized-Light" -n "Banana-Solarized-Light" -c "Solarized Light Banana Windows Regular Cursors."
ctgen configs/win_lg.build.toml -d "bitmaps/Banana-Solarized-Light" -n "Banana-Solarized-Light" -c "Solarized Light Banana Windows Large Cursors."
ctgen configs/win_xl.build.toml -d "bitmaps/Banana-Solarized-Light" -n "Banana-Solarized-Light" -c "Solarized Light Banana Windows Extra Large Cursors."
```

###### Banana Dracula

```bash
npx cbmp -d "svg" -o "bitmaps/Banana-Dracula" -bc "#282a36" -oc "#f8f8f2"

ctgen configs/x.build.toml -d "bitmaps/Banana-Dracula" -n "Banana-Dracula" -c "Dracula Banana XCursors."
ctgen configs/win_rg.build.toml -d "bitmaps/Banana-Dracula" -n "Banana-Dracula" -c "Dracula Banana Windows Regular Cursors."
ctgen configs/win_lg.build.toml -d "bitmaps/Banana-Dracula" -n "Banana-Dracula" -c "Dracula Banana Windows Large Cursors."
ctgen configs/win_xl.build.toml -d "bitmaps/Banana-Dracula" -n "Banana-Dracula" -c "Dracula Banana Windows Extra Large Cursors."
```

## Testing Cursor

There are several websites that allow you to test your cursor states by hovering over buttons. This can be very useful when developing or verifying the behavior of a cursor. The following websites cover many of the most commonly used cursors, although they may not include all available options.

-   [Cursor-Test](https://vibhorjaiswal.github.io/Cursor-Test/)
-   [Mozilla CSS Cursor](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor)

For a blueprint for creating XCursors, you may also want to refer to [Cursor-demo](https://wiki.tcl-lang.org/page/Cursor+demo).

# Bugs

Bugs should be reported [here](https://github.com/ful1e5/banana-cursor/issues) on the Github issues page.

## Getting Help

You can create a **issue**, I will help you.

## Contributing

Check [CONTRIBUTING.md](CONTRIBUTING.md), any suggestions for features and contributions to the continuing code masterelopment can be made via the issue tracker or code contributions via a `Fork` & `Pull requests`.
