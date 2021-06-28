
### Automated color updates
This Mint-Yz fork lets you change or add colors easier and faster than with the official Mint-Y scripts. But I have a Pull Request going on to copy these features to the official Mint-Y, so eventually, maybe, the official Mint-Y will be easier too.

With this Mint-Yz fork here, building Mint-Y-Colors is now 100% automated. As of August 2020, the following directories have to be edited by hand on the official Mint-Y:

  * gtk-2.0/menubar-toolbar/  
  * gtk-3.0/thumbnails/  
  * cinnamon/thumbnails/  
  * xfwm4/ (3 colored assets)

So if you want to build your own themes, you will find it less difficult starting from here. But there are always unforeseen events, things to learn, things to fix. It is not so easy. Make sure you have the time and the will before you embark on this adventure. And be careful, always make backup copies. Be aware you must have some basic knowledge of the Linux system and terminal. There is no warranty, this is at your own risk.

### Required
If you want to build your own theme, you will need to install those packages:
 
  * Inkscape, preferably version 1.0 or higher (from PPA?)
  * optipng  
  * imagemagick
  * sassc
  * git

### Compatibility issues
There are a few `render-assets.sh` scripts scattered around the `src/Mint-Y` directory and its sub-directories. They contain some `--export-filename` or `--export-png` Inkscape commands. Check that you have the required command for your version of Inkscape, or just replace as required:
 
  * Inkscape version 1.0 or higher: `--export-filename`  
  * Inkscape version 0.x: `--export-png`

### Instructions
If you want to create your own theme, here is what to do.

1. Install the required software and packages listed above.
1. Git clone this repository, using your terminal: `git clone https://github.com/SebastJava/mint-yz-theme.git`. You may need to install the git package first.
1. Edit the colors in the `constants.py` file. You can add new colors if you want to. You don’t have to place them in any particular order. I placed my colors in ascending order of hue, but it could have been sorted alphabetically or otherwise. Take a look at this `constants.py` file:
   1. `colors1` is the base color
   1. `colors2` is for the dark variants
   1. `colors3` and `colors4` are just for those tiny `titlebutton-close-hover` and `titlebutton-close-active`, respectively.
   1. Example, add your new color in constants.py: <br>
`y_hex_colors1["MyNewColorName"] = "#40BF40"` <br>
`y_hex_colors2["MyNewColorName"] = "#36A336"` <br>
`y_hex_colors3["MyNewColorName"] = "#66CC66"` <br>
`y_hex_colors4["MyNewColorName"] = "#2D862D"` <br>
(`colors2` = 15% darker, `colors3` = 20% lighter, `colors4` = 30% darker)

   1. I recommend setting `colors2` 5% darker, unless this color is already dark. The `colors3` should be 20% lighter. And `colors4` should be 30% darker.
   1. OPTIONAL: I made a simple trick to quickly get those values and copy them into the `constants.py` file. Open the `Mint-Y-Colors/Mint-Y-Variations-NEW.svg` file into Inkscape. Check the different layers. There are layers named `colors2`, `colors3` and `colors4`. By making them visible only one layer at a time, i used a color picker to quickly "pick and paste" all the 11 colors for all those colors 1, 2, 3 and 4. But feel free to get those values any way you want.
1. Open your Terminal and change directory: `cd ~/mint-yz-theme`.
1. On the first time, you must run `./update-variations.py All` from your terminal, in the mint-yz-theme directory. Later, you can replace `All` with one specific color name like `Blue` for quick testing.
1. Next, run `./generate-themes.py` from your terminal, in the mint-yz-theme directory.
1. And finally, copy all the files from ~/mint-yz-theme/usr/share/themes/ into /usr/share/themes/ as root: `sudo cp -rf usr/share/themes/Mint-Yz-* /usr/share/themes/` from your terminal, in the mint-yz-theme directory.
1. Change your theme in the system preferences.

### Help
If you are having trouble, start by searching the web for answers. If you can’t find any good answer, you can create an [issue](https://github.com/SebastJava/mint-yz-theme/issues) here on my repository. But if you need an answer quickly, you’d be better off with the [Linux Mint Forums](https://forums.linuxmint.com/).
