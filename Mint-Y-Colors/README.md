# Mint-Y color variations
### A new approach to please everyone

There are 16.7 million color possibilities. It’s way too much. We want to offer 11 or 12. With the dark and darker variants, that's 33 or 36.

This new approach is to offer a slightly smaller range of colors, focusing on the most popular, but with more variations. There are some dull colors taken from the old Mint-Y, there are several that come from https://flatuicolors.com/, and there are a few that are more vivid.

The https://flatuicolors.com/ offers a color palette created by a group of designers. These colors have been copied more than 25 million times from more than 150 countries around the world. The colors whose name ends with a "-2" have been slightly modified: it is a color located between the light version and the dark version of the same color on the same palette.

The few ColorShine colors come from the Mint-Yz-theme created by SebastJava. It's a fork of the Mint-Y theme that has been downloaded a few thousand times from https://www.pling.com/p/1408266/ without having advertised. And that is without counting the downloads made directly on GitHub. This Mint-Yz theme received many highly positive comments.

______
### message-colors.svg use:

Copy-Paste those lines from the **svg file:**

    $link_color: #(LATESTCOLOR);
    $link_visited_color: #(LATESTCOLOR);
    //___
    $selection_mode_bg: $selected_bg_color;
    $selection_mode_fg: $selected_fg_color;
    $warning_color: #(LATESTCOLOR);
    $warning_fg_color: white;
    $error_color: #(LATESTCOLOR);
    $error_fg_color: white;
    $success_color: #(LATESTCOLOR);
    $destructive_color: #(LATESTCOLOR);
    $suggested_color: #(LATESTCOLOR);
    $question_color: #(LATESTCOLOR);
    //___
    $drop_target_color: #(LATESTCOLOR);

These lines replaces the corresponding ones in:

    ~/mint-themes/src/Mint-Y/gtk-3.0/sass/_colors.scss