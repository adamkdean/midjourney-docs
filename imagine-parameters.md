---
description: An illustrated Guide to /imagine parameters
---

# Imagine Parameters Illustrated

### Basic Structure

Parameters options that change how the images generate. A full `/imagine` command might contain several things, like an image URL, image weights, algorithm versions, and other switches.\
\
`/imagine` parameters should follow the below order:

![/imagine prompt: https://example/tulip.jpg  a field of tulips in the style of Mary Blair --no farms --iw .5 --ar 3:2"](.gitbook/assets/ImagineStructure.jpg)

"Switches" in this context means controls passed to the bot using a "--" parameter. For instance, the command `/imagine hi there --w 448` has a text prompt, and a parameter for the width, using the "--w" instruction.

### Sizes

#### **Width and Height**

`--w` Width of image. Works better as multiple of 64 (or 128 for `--hd`)

`--h` Height of image. Works better as multiple of 64 (or 128 for `--hd`)

`--w` and `--h` values above 512 are unstable and may cause errors.

![/imagine: promptvibrant california poppies](.gitbook/assets/MJ\_Imagine.png)

&#x20;

![/imagine:promptvibrant california poppies --w 448](.gitbook/assets/MJ--w.png)



`--aspect` or `--ar` Sets a desired aspect ratio, instead of manually setting height and width with `--h` and `--w`.

Try `--ar 9:16` for example, to get a 9:16 aspect ratio (\~256x448).

![promptvibrant california poppies --ar 9:16](.gitbook/assets/mj--ar.png)

Also see [Understanding Image Sizes](resource-links/understanding-image-size.md).

#### Size Shortcuts

These "shortcuts" are command that do the same as the forms following the ":" in the list below. For instance, if you type:

**/imagine:** `prompt`**`vibrant california poppies`**`--wallpaper`

It would be the same as typing the longer form:

**/imagine:** `prompt`**`vibrant california poppies`**`--w 1920 --h 1024 --hd`

Shortcut equivalences:

`--wallpaper`: `--w 1920 --h 1024 --hd`

`--sl`: `--w 320 --h 256`

`--ml`: `--w 448 --h 320`

`--ll`: `--w 768 --h 512 --hd`

`--sp`: `--w 256 --h 320`

`--mp`: `--w 320 --h 448`

`--lp`: `--w 512 --h 768 --hd`

###

### Algorithm Modifiers

#### Version 1

`--version 1` or `--v 1` uses the original Midjourney algorithm (more abstract, sometimes better for macro or textures). `--v 1` corresponds to the <img src=".gitbook/assets/MJ_v1_btn.png" alt="" data-size="line">button in `/settings.`

![](<.gitbook/assets/image (10).png>) prompt: **`vibrant california poppies` --version 1**

#### Version **2**

`--version 2` or `--v 2` uses the original Midjourney algorithm in use before July 25th, 2022.\
`--v 2` corresponds to the <img src=".gitbook/assets/MJ_v2_btn.png" alt="" data-size="line">button in `/settings.`

![](.gitbook/assets/mj--v2.png) prompt: **`vibrant california poppies` --v 2**

#### Version **3**

`--version 3` or `--v 3` uses the current default Midjourney algorithm.\
`--v 3` corresponds to the <img src=".gitbook/assets/MJ_v3_btn.png" alt="" data-size="line"> button in `/settings.`

\`\`![](.gitbook/assets/mj--v3.png) prompt: **`vibrant california poppies --v 3`**

#### High Definition

`--hd` Uses a different algorithm that’s potentially better for larger images, but with less consistent compositions.

![prompt: vibrant california poppies --hd](.gitbook/assets/mj--hd.png)

### Prompt Modifiers

#### --No

`--no` Negative prompting (e.g., `--no plants` would try to remove plants). This is like giving it a weight of -0.5.

![](<.gitbook/assets/mj--no (1).png>) prompt: **`vibrant california poppies --no grass`**

### Detail Modifiers

#### --Stop

`--stop` Stop the generation at an earlier percentage. Must be between 10-100.

![](<.gitbook/assets/image (1).png>) prompt: **`vibrant california poppies --stop 50`**

#### --Uplight

`--uplight` Use "lighter" upscaler for upscales. Light results are closer to the original image with less detail added during upscale. `--uplight` corresponds to the <img src=".gitbook/assets/MJ_uplight_btn.png" alt="" data-size="line"> button in `/settings`.

Regular upscale <img src=".gitbook/assets/MJ_regUpscale_btn.png" alt="" data-size="line"> (left) vs Light Upscale <img src=".gitbook/assets/MJ_uplight_btn.png" alt="" data-size="line"> (right)

![Regular upscale](.gitbook/assets/mj\_upscale.png) ![Light upscale](.gitbook/assets/Mj\_uplight.png)



### Seeds

A seed number generate the random starting noise used in the begining of image generation. Using the same number across multiple prompts will use the same starting noise.

#### --Seed

`--seed` Sets the random seed (an integer), which can sometimes help keep things more steady / reproducible between generations.

For instance: the same prompt run twice, with no seed specified:

![prompt: an abstract field of flowers](.gitbook/assets/MJ\_Imagine.png) ![prompt: an abstract field of flowers](.gitbook/assets/mj\_seed.png)

Versus specifying the seed and running it twice:

![prompt:vibrant california poppies--seed 0987](.gitbook/assets/MJ\_Imagine.png) ![prompt:vibrant california poppies--seed 0987](.gitbook/assets/mj\_seedtwice.png)

``

#### --Sameseed

`--sameseed <number>` Sets the same seed across all images of the resulting grid, resulting in minimal changes within the initial grid. The `sameseed` can be any positive integer.

![prompt:vibrant california poppies--sameseed 0987](.gitbook/assets/mj\_sameseed.png)

### --Stylize

`--stylize <number>`, or `--s <number>` The stylize argument sets how strong of a 'stylization' your images have, the higher you set it, the more opinionated it will be. Default number is 2500.

See the [User Manual](user-manual.md#stylize-values) for more detailed information.

The default is 2500, but you can set it lower too. For instance, `--s 1250` is good for when you want it to be 'less strict' but still 'pretty' (this is probably recommended for skilled users). `--s 1250` corresponds to the <img src=".gitbook/assets/MJ_v1_StyleLow.png" alt="" data-size="line"> button in `/settings.`

![using --s 1250. --s 1250 corresponds to the  button in /settings](.gitbook/assets/mj--s1250.png)

``

![The default, --s 2500 (which doesn't need to be specified in your prompt)
\--s 2500 corresponds to the  button in /settings.](.gitbook/assets/MJ--s2500.png)

![--s 5000 corresponds to the  button in /settings.](.gitbook/assets/mj--5000.png)

![--s 20000 If you want it to 'take over' and start drifting from your text, but not go crazy.
\--s 20000 corresponds to the  button in /settings.](.gitbook/assets/mj--s20000.png)

``

### --Quality

`--quality <number>` , or `--q <number>` Sets how much rendering quality time you want to spend. Default number is 1. Higher values take more time and cost more. See the [User Manual](user-manual.md#quality-values) for more detailed information.

Specifying a quality of .5 will reduce your cost and image quality:

![prompt:vibrant california poppies --q .5 (2x faster/cheaper) --q .5 corresponds to the  button in /settings.](.gitbook/assets/mj--q05.png)

`--q 1`  is the **default value**, you do not need to specify it.\


![prompt: vibrant california poppies--q 1 corresponds to the  button in /settings.](.gitbook/assets/MJ\_Imagine.png)

`--q 2` will give you more detailed results, but is 2x slower / more expensive:

![prompt:vibrant california poppies --q 2
\--q 2 corresponds to the  button in /settings.](.gitbook/assets/mj--q2.png)



### `Progress Videos`

`--video` Saves a progress video. Video will be sent to you in DM by the bot (private message) after you react to the result with the ✉️ emoji.

![prompt:vibrant california poppies --video](.gitbook/assets/mj--video.png)

### Image Prompting with URL

`--iw` Sets image prompt weight proportional to the text weight. Use a decimal value (default 0.25).

Add one or more image URLs to your prompt and it will use those images as visual inspiration. You can mix words with images or just have images alone. See [Image Prompt Questions](FAQs.md#image-prompt-questions) for more info.

**Note**: This is _not_ the same as building on top of (or "initializing" from) an input image. Midjourney does not currently offer the ability to use an "init" image as seen in some other tools, due to concerns about community public content.

`--iw` — Adjusts the weight of the image URLs vs the text. 0.25 is the default weight. As you increase it to 1, you increase the strength of the image. Experiment and see what you like. Also [see FAQ here](FAQs.md#image-prompt-questions) and [Manual section here.](user-manual.md#image-prompting-with-url)

**Note**: There is currently no way to apply different weights to different image prompts. This will be addressed in the future.

Example image prompt:

![](<.gitbook/assets/image (13).png>) Linked Image with the URL "https://dots.jpg"

Image prompt use with no `--iw` parameter, `--iw .5` `--iw 1` `--iw 2` and `--iw 5`

![Results of different image weights](.gitbook/assets/mj--iw.png)

**From left to right:**

* `prompt`` `**`https://dots.jpg vibrant california poppies`** (default image weight is .25)
* `prompt`` `**`https://dots.jpg vibrant california poppies --iw .5`**
* `prompt`` `**`https://dots.jpg vibrant california poppies --iw 1`**
* `prompt`` `**`https://dots.jpg vibrant california poppies --iw 2`**
* `prompt`` `**`https://dots.jpg vibrant california poppies --iw 5`**

### Settings

You can use the `/settings` command to set parameters you want to use as your defaults.\
Each row is a toggle button, meaning turning one on will turn the others off.

![](.gitbook/assets/settings.png)
