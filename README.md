# Creating Mint-Y-COLOR variations is now 100% automated

**You no longer need to manually re-edit all those `files/usr/share/themes/` directories and files. All these color variations had to be redone over and over again. Now, it all happens automatically in a matter of minutes.**

This is a group of 6 branches. The first 5 are pull requests. And this sixth one here, this `newmain`, is there for testing purposes, and it also contains this readme file.

* **cinthumb**: creates `src/Mint-Y/cinnamon/mint-y-thumbnail.png` and `mint-y-dark-thumbnail.png`.
* **menubar-toolbar**: creates `src/Mint-Y/gtk-2.0/menubar-toolbar/` (only the 4 colored ones)
* **thumbnails**: creates `src/Mint-Y/gtk-3.0/thumbnail.png` and `thumbnail-dark.png`.
* **variations**: contains modified `update-variations.py` and `generate-themes.py` to run and copy all those things.
* **xfwm4**: creates `src/Mint-Y/xfwm4/` and `xfwm4-dark/` (only the 3 colored ones)

...And **newmain** merges all these branches for testing purposes and contains this readme file here.


`src/Mint-Y/gtk-2.0/menubar-toolbar/` was originally automated, with the Arc theme. I just put it back as it was.

`src/Mint-Y/xfwm4/` was originally fully automated, with the Arc theme. But the images have been changed slightly since then. Being in doubt, I therefore resumed the original automation, but only for the 3 colored assets.
 
`src/Mint-Y/gtk-3.0/thumbnail.png` is now automatically created in a simple way: a small addition to `assets.svg` and a small addition to `render-assets.sh`.
 
`src/Mint-Y/cinnamon/mint-y-thumbnail.png`: I automated the creation of these thumbnails with a kind of ingenious photomontage and a new script similar to the other scripts. You have to see my additions to the `src/Mint-Y/cinnamon/` folder to understand. It may look quite complex, but this `mint-y-thumbnails-src/` directory is only there in case someone wants to re-edit the images.


These pull requests replaces my previous #280 PR. It is approximately the same thing, but those 5 new PRs should be much easier to compare, review, and test. Things are now divided into sections. And those new branches were created from a master branch that is exactly the same as yours. And up-to-date. Everything got re-edited... and tested! But of course, as usual, there is NO WARRANTY. You should check all this before merging.

After having merged this group of PRs, you could just delete `files/usr/share/themes/` and `colorize.py`. And you could also delete my old Mint-Y-Colors directory; that's just old stuff.


## How this works
In short, the whole operation of the source Mint-Y is described as follows. There are several scripts in the `src/` sub-directories to re-generate the assets and CSS files. All of these scripts are launched by `/src/Mint-Y/build-themes.py`. But, to create all the color variations, two other Python scripts are taking care of replacing the colors and re-running all these processes. `update-variations.py` takes care of regenerating the assets with the new colors. These assets are then stored in `src/Mint-Y/variations/`. And then, finally, `generate-themes.py` will take care of duplicating those themes, and then change the colors in the CSS and GTKRC files, and then copy the assets from `src/Mint-Y/variations/`. There it is, approximately, in short.


## How to build
YOU MUST RUN `./update-variations.py All` at first !!! Later, you could re-edit those colors one-by-one with some `./update-variations.py COLOR`.

* Merge all those 5 branches or just test this `newmain` branch here.
* You MUST run `./update-variations.py All` at first. Later, you could try some new colors updates one-by-one.
* Run `./generate-themes.py`.
* `cd ~/mint-yz-theme` and then `sudo cp -rf usr/share/themes/ /usr/share/themes/`.
* Refresh your Menu > Preferences > Themes.
