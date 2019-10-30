# RGB Channel Shift Tool

This Processing sketch provides a GUI interface for datamoshing images by
manipulating RGB color channels.


<!-- vim-markdown-toc GFM -->

* [Overview](#overview)
* [Installation](#installation)
* [Features](#features)
    * [Swap Color Channels](#swap-color-channels)
    * [Shift Color Channels](#shift-color-channels)
    * [Recursive Iterations](#recursive-iterations)
    * [Randomization](#randomization)
    * [Experimental Shift Types](#experimental-shift-types)
* [Controls](#controls)
    * [Color Channels](#color-channels)
        * [Source Channel](#source-channel)
        * [Target Channel](#target-channel)
    * [Horizontal/Vertical Shift](#horizontalvertical-shift)
    * [Randomize Options](#randomize-options)
        * [Toggle Randomization Options](#toggle-randomization-options)
        * [Set Random Shift Threshold](#set-random-shift-threshold)
    * [Confirm Step](#confirm-step)
    * [Reset Step](#reset-step)
    * [Save Current Result](#save-current-result)
    * [Load a New Source Image](#load-a-new-source-image)
    * [Advanced Options](#advanced-options)
* [Experimental Shift Types](#experimental-shift-types-1)
    * [Linear](#linear)
    * [Scale](#scale)
    * [Skew](#skew)
    * [XY Multiply](#xy-multiply)

<!-- vim-markdown-toc -->

## Overview

The basic features of this tool allow you to shift color channels vertically and
horizontally, as well as swap color channels with each other:

![Basic Showcase](samples/basic-showcase.png)

It also includes experimental shift types that modify how pixels are shifted,
which can be combined for interesting effects:

![Advanced Showcase](samples/advanced-showcase.png)


## Installation

This sketch requires [Processing 3+](https://processing.org/download/) (tested
using Processing 3.5). It uses the [G4P GUI
library](http://www.lagers.org.uk/g4p/), which is included in this repo, so no
additional setup is required.


## Features

### Swap Color Channels

Swap the selected channel from the source image with the selected channel from
the target image.

### Shift Color Channels

Shift the selected source image channel horizontally and/or vertically on the
target image.

### Recursive Iterations

Use the target image as the source for subsequent iterations.

### Randomization

Target channel, source channel, horizontal shift, and vertical shift can all be
randomized. You can select/deselect which options to randomize, as well as set a
max threshold for vertical and horizontal shift amounts.

### Experimental Shift Types

By default, horizontal and vertical shifts translate the color channel along the
x and y axes, respectively. You can also select experimental shift types with
their own advanced options that modify how each pixel is shifted based on a
number of conditions. (Kind of hard to explain succinctly, but basically it's a
bunch of neat effects)

For explanations and examples of each type, see [Experimental Shift
Types](#experimental-shift-types-1).

## Controls

![GUI](screenshots/gui.png)

### Color Channels

#### Source Channel

Selects the color channel from the source image to be shifted.

#### Target Channel

Selects the color channel from the result image to swap the source channel with.
If you don't want to swap channels, set this to the same option as the source
channel.


### Horizontal/Vertical Shift

The horizontal and vertical shift sliders offset the selected source channel
along the X and Y axis, respectively. 

By default, both sliders use percentage values. If you want to set an exact
pixel distance to shift by, select the **Pixels** option to the right of the
slider.

You can also set the shift value manually using the text input to the left of
the sliders.


### Randomize Options

The **Randomize Options** panel is used to randomize the current step.

#### Toggle Randomization Options

By default, all options are randomized. You can uncheck the boxes of any options
you do not want to randomize.

#### Set Random Shift Threshold

The **Max Horizontal/Vertical Shift %** inputs can be used to put a limit on the
randomized shift values. For example, setting **Max Horizontal Shift %** to 10
will only result in random horizontal shift values of 10% of the image width or
less. 

**Note:** that neither of these inputs will have any effect if the corresponding
**Horizontal/Vertical Shift** checkbox is unchecked.


### Confirm Step

To commit the current channel shift step, click the **Confirm Step** button.
This will update the working image to match the preview and reset all
configurations so you can apply another step.

If the **Recursive** checkbox is checked upon clicking the confirm button, the
source image pixels will be updated to match the shifted image, so further
channel shifts/swaps will be applied based on the shifted image instead of the
original image. Otherwise, further channel shifts/swaps will be based on the
original channels.


### Reset Step

To revert the current step to the default, click the **Reset Step** button. Note
that this will not affect any previously confirmed steps.


### Save Current Result

To save the current result shown in the preview window, click the **Save
Result** button. This will bring up the system "Save As" dialog.


### Load a New Source Image

To load a source image, click the **Load Image** button and select the desired
image file. Note that this will clear the current result, so be sure to save it
before loading if you don't want to lose your work.

### Advanced Options

**TODO:** Advanced Options panel


## Experimental Shift Types

**TODO:** Explain options for each

### Linear

![Linear shift type](samples/linear.png)

### Scale

![Scale shift type](samples/scale.png)

### Skew

![Skew shift type](samples/skew.png)

### XY Multiply

![XY Multiply shift type](samples/xy-mult.png)


