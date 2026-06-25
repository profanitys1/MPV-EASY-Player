MPV-EASY Player
https://./img/mpv-logo-128.png 🌐 Language of this page: English | 中文
MPV-EASY Player: An easy to use, modern video player based on MPV
All the content on this page is described in English.

If you don't know English, it doesn't matter. You can download it from the release page and try to use it. The interface of MPV-EASY Player supports display in Chinese, English and additional languages described below.

https://./img/mpv-easy-player-gui-mode-github.jpg

Help Translate MPV-EASY Player Language Files
If you like this player and have the ability to translate it into a language you are familiar with:

language : Chinese and English language files have been provided under this path. You can download them for reference and use these two language files plus Qt Linguist to translate into other languages.

Chinese language files: cn-mpveasygui.ts and cn-mpveasysettings.ts

English language files: en-mpveasygui.ts and en-mpveasysettings.ts

After the translation, you only need to send the new language file to issues.

Of course you can also correct the translation in the English language file.

Many thanks.

Additional Languages Already Supported:
Italian language files (it-mpveasygui.ts and it-mpveasysettings.ts): Thanks to bovirus for the Italian translation and corrections to the English translation.

Japanese language files (ja-mpveasygui.ts and ja-mpveasysettings.ts): Thanks to coolvitto for providing the Japanese translation.

Quick Summary (If You Don't Want to Read the Detailed Content Below)
The folder [MPV-EASY Player\data\portable-data] corresponds to mpv’s:

%appdata%\mpv configuration folder (i.e., C:\Users\<username>\AppData\Roaming\mpv)

Or the mpv\portable_config configuration folder

Place mpv script files in [MPV-EASY Player\data\portable-data\scripts] (the subfolder structure is the same as in mpv)

To manually modify mpv settings normally found in %appdata%\mpv\mpv.conf or mpv\portable_config\mpv.conf:

In MPV-EASY Player these settings have been moved to [mpv-easy player\data\mpv-easy-data\rjno1.conf]. Modify this file instead.

The input.conf file used to customize shortcut keys:

In MPV-EASY Player this file is located at [MPV-EASY Player\data\mpv-easy-data\input.conf]

Various Scripts Usable by mpv
Please refer to this summary page: https://github.com/mpv-player/mpv/wiki/User-Scripts

Basically, MPV-EASY Player is built by thoroughly reading and understanding mpv’s manual.pdf, then assembling and combining mpv, mpv configuration, lua scripts (including those shared by others on GitHub), and js scripts.

Although MPV-EASY Player requires installation, it is essentially a 100% portable application. So-called "installation" is just extraction; after reinstalling the OS, you can run it immediately without reinstalling, at most needing to re-associate file formats.

Of course, as a kind of front-end, a lot of other things have been done, some clever hacks even – after all, some features cannot be perfectly integrated just with mpv and scripts (mainly due to the author’s limited coding ability). But with continuous development, MPV-EASY Player now has its own complete GUI front-end and has become a full-fledged player. Therefore, its default appearance now looks like the image below.

https://./img/mpv-easy-player-6-github.jpg

Although MPV-EASY Player has a more beautiful GUI, it does not abandon mpv’s native GUI. In fact, you can switch freely among 4 different operation modes and 2 different GUI interfaces at any time, and also experience the latest mpv at any time (just place the downloaded latest mpv into the [MPV-EASY Player folder\mpv] path). Lua and js scripts supported by mpv can also be directly placed into MPV-EASY Player. This retains mpv’s characteristics as much as possible, achieving maximum compatibility.

https://github.com/422658476/MPV-EASY-Player/blob/master/img/mpv-easy-player-2.jpg

The Entire Player Includes Much Open-Source Code and Even More Closed-Source Code
Limited by energy and ability, this is not a cross-platform player; it only runs on Windows, and some behaviors may even violate various agreements.

However, apart from the four exe files, all other files of MPV-EASY Player are already here on GitHub. These files are certainly very useful for you to use the original mpv; with minor modifications and placing them into mpv, you can gain many improvements, whether you use mpv on Windows, Mac, or Linux (they all support or mostly support these).

Don’t ask why it works on Windows, Mac, Linux: it’s because I have all three operating systems and have used various front-ends for mpv. After all, I’m very familiar with operating in the graphical interface of each OS (skilled at clicking the mouse). If you haven’t used some of these operating systems, let it go – curiosity will waste a lot of your time and energy, and might even be exhausting. (Especially the third one: branches, dependencies, various package managers, compilation, input methods, graphics drivers, front-ends, compatibility problems caused by different graphical environments are the most troublesome.)

Maybe you ask why not use various mpv-based graphical front-ends. After fully understanding this player from the manual, you’ll find that only native mpv can make it the most powerful, interesting, and full of possibilities, because you need to add various parameters and scripts. Using native mpv also has other extra benefits, such as keeping up with the latest version and experiencing new features, and of course, the fastest bug fixes.

Most front-ends more or less lack support for parameters and scripts. The most common problem is losing the OSC (since it’s no longer needed) – you don’t know if lua scripts are supported, which file to add parameters to, where to place them. In the end, you find the original version is more convenient. 2018-7-28: I seem to be slapping my own face. :(

Of course, nothing is absolute. The above may become outdated, wrong as time passes, things develop, thoughts change, and technology advances. So you may even ignore all the above.

Why Did I Write the Above? And Put It at the Very Beginning?
To waste as much of your precious time as possible.

How to Obtain mpv’s manual.pdf (Documentation)
https://mpv.io/manual/ – On this page you can view the HTML version of the manual, or download the PDF version. The mpv package you download also contains this manual.pdf.

Reading the documentation is, of course, the top priority. You can learn which files go in which path to take effect, what parameters activate what features, and find answers to ten thousand "why" questions about mpv. However, the document is in English; use translation software when reading.

Benefits of the portable-data and mpv-easy-data Folders
Note: You don’t need to look at folders like icons, img, tutorial; the useful ones for you are only portable-data and mpv-easy-data.

Since I have uploaded all files in these two folders, your burden of reading the manual.pdf is greatly reduced (writing MPV-EASY Player is also to lighten everyone’s load – after all, many painful processes and wasted time can be borne by one person). You can even just open some files in these two folders, copy and paste their contents to get the result you want. Therefore, all the following text is an explanation of how to migrate most functions of MPV-EASY Player to mpv, so you can understand the differences between the two in operation and functionality.

This way, no matter what platform you use mpv on, even if MPV-EASY Player has bugs, stops updating, or becomes incompatible with the latest mpv, you can rely on yourself to obtain a more powerful, more convenient, even your own mpv player. It can also help you discover bugs in MPV-EASY Player faster and add new features.

Similarities and Differences in Folder Structure Between MPV-EASY Player and mpv
Since MPV-EASY Player originates from mpv, their folder structures are actually very similar. Therefore, migrating settings and files from the former to the latter is very simple.

Why doesn’t MPV-EASY Player use the same folder structure as mpv?

Because mpv’s lua scripts do not support being stored in paths containing Chinese characters (theoretically paths with wide characters or double-byte characters) (mpv 0.33.0 2020-11-22 resolved this issue). So partial separation was done. MPV-EASY Player, through pre-launch processing, enables mpv to call lua scripts when stored in paths containing Chinese. So when using mpv, you must also pay attention to the problem of lua scripts and Chinese paths; it’s best to use an all-English path.

Maybe the file storage paths, structures, and calling methods mentioned below have many differences from what you previously thought, maybe even redundant. But all this effort is for supporting Chinese paths and for storing as few files as possible on the C drive under pure English paths, so that most data is kept off the C drive, preventing configuration file loss and software loss, and also minimizing the number of small files that need to be copied to the C drive, saving time and enabling faster startup.

How to Adapt MPV-EASY Player’s Two Folders for mpv on Windows Click to Jump Below
On Windows, mpv supports reading configuration from essentially two paths. You only need to choose one.

Using text explanations may still cause confusion in understanding. No problem – you can first download a pre-packaged example from the release: “Homepage Tutorial Example Usage: mpv-0.28.2-i686-20180324 (based on method 1, used under pure English path)”. Use it while reading the text below.

Method 1 (Only works fully under pure English paths, i.e., MPV-EASY operation mode: Native 2 | mode 2):
https://./img/mpv-conf-dir-1.jpg

Steps:

Download the program.
From https://mpv.srsfckn.biz/ or https://sourceforge.net/projects/mpv-player-windows/files/ download the mpv program package, extract it locally, for example to the mpv player folder, so you can see mpv.exe inside that folder.

Create fixed folders and files.
Open the folder containing mpv.exe (in the example, open the mpv player folder). Based on the path of mpv.exe, create the following subfolders and files. These file/folder names and paths are immutable.

mpv.exe's folder\portable_config
mpv.exe's folder\portable_config\XXXXXXX (Choose one of the two below based on the following info)

mpv.exe's folder\portable_config\lua-settings (if using mpv version before 2018-3-30)
mpv.exe's folder\portable_config\script-opts (if using mpv version after 2018-3-30)
mpv.exe's folder\portable_config\scripts
mpv.exe's folder\portable_config\mpv.conf

If unclear, refer to the image above. The purpose of folders and files can be found in the manual.pdf.

mpv will by default read various configurations from the portable_config subfolder. So all subsequent files will be placed inside the portable_config folder for modification.

Import files into the portable_config folder.
From this page download the portable-data and mpv-easy-data folders at the top.

Put everything inside the portable-data folder into [mpv.exe folder\portable_config].
Place the mpv-easy-data folder itself (along with the folder) directly into [mpv.exe folder\portable_config].

After importing, the structure should match the image. You can manually verify.

Modify mpv.conf to let mpv read normally.

The purpose of modifying mpv.conf:
a. Direct mpv to read configuration files from the following paths:

mpv.exe folder\portable_config\mpv-easy-data\input.conf
mpv.exe folder\portable_config\mpv-easy-data\rjno1.conf
b. Let mpv save history files to:
mpv.exe folder\portable_config\mpv-easy-data\watch_later

Open mpv.conf under [mpv.exe folder\portable_config], check if each line begins with #. If not, add # (lines starting with # are treated as comments by mpv, having no effect).

After checking, add the following 5 lines to mpv.conf:

text
input-conf=portable_config\mpv-easy-data\input.conf
include=portable_config\mpv-easy-data\rjno1.conf
watch-later-directory=portable_config\mpv-easy-data\watch_later
profile="ini-rjno1"
write-filename-in-watch-later-config
Because relative paths are used, no matter where the mpv player folder is moved to (under any pure English path), the configuration will work without any further changes.

Method 2 (Supports Chinese paths, but some files must be copied to C drive, i.e., MPV-EASY operation mode: Compatible | mode 0):
https://./img/mpv-conf-dir-2.jpg

Note: The second arrow in the image above is wrong. It should point from the left scripts folder to the right scripts folder.

The second method evolves from the first. Once you have the first, you can easily turn it into the second with a little manipulation.

The second method mainly uses the fact that mpv’s configuration folder on the C drive is itself a pure English path to solve the problem of lua scripts not supporting Chinese paths.

Rename the portable_config folder from the first method, e.g., to data. You will get:

mpv.exe folder\data
mpv.exe folder\data\XXXXXXX (choose one according to above)

mpv.exe folder\data\lua-settings
mpv.exe folder\data\script-opts
mpv.exe folder\data\scripts
mpv.exe folder\data\mpv.conf
mpv.exe folder\data\mpv-easy-data

The data folder can be moved and renamed to any path. If you want easy migration with mpv or are not familiar with mpv, it’s still recommended to keep it in the folder containing mpv.exe.

The mpv-easy-data folder can also be moved to any path, but for convenience keep it under [mpv.exe\data].

Open mpv.conf under [mpv.exe folder\data], check that each line begins with #. If not, add #.

Modify the purpose of mpv.conf: direct mpv to read config files from:

data\input.conf
data\mpv-easy-data\rjno1.conf
data\mpv-easy-data\watch_later

After checking, change the previous 5 lines to:

text
input-conf=data\input.conf
include=data\mpv-easy-data\rjno1.conf
watch-later-directory=data\mpv-easy-data\watch_later
profile="ini-rjno1"
write-filename-in-watch-later-config
Since relative paths are used, after moving the mpv player folder (see next step), no changes to mpv.conf are needed.

Move the folder containing mpv.exe and the data folder to the path you want to store them (supports Chinese paths), e.g.:

D:\mpv player player\mpv.exe
D:\mpv player player\data

Copy (or cut, but recommend copy) the lua-settings, scripts folders and mpv.conf file from the data folder to:

C:\Users\<username>\AppData\Roaming\mpv
(If the mpv folder doesn’t exist, create it.)
For mpv versions after 2018-3-30, replace lua-settings with script-opts.

Whenever you modify data inside the data folder, redo step 4 before running mpv.exe for changes to take effect. After reinstalling the OS and losing data under C:\Users\<username>\AppData\Roaming\mpv, just redo step 4.

MPV Usage (Including Parameter Changes, Lua Scripts, JS Scripts, Custom Shortcuts)
Once you know how to flexibly use mpv on Windows through the steps above, you can begin various customizations. Of course, customization depends on your understanding of the manual.pdf. The more familiar you are, the more powerful it becomes. If you don’t care about the manual, that’s fine too, because the settings already added in the portable-data and mpv-easy-data folders are sufficiently powerful.

Note: If the default parameters do not make mpv work properly, it means mpv has changed some parameters during version upgrades. You need to compare the manual.pdf of old and new versions, or check the changelog to find differences.

Various Scripts for mpv
Please refer to this summary page: https://github.com/mpv-player/mpv/wiki/User-Scripts

If your mpv needs some basic default parameters, you can directly copy the parameters from rjno1.conf and then modify them.

Main Files and Folders for Customizing mpv
mpv-easy-data\input.conf – mainly used for customizing shortcut keys. The file already contains sufficient examples and a few modified shortcuts.
mpv-easy-data\rjno1.conf – mainly for adjusting mpv’s settings parameters. These settings were originally placed in mpv.conf and have now been moved to rjno1.conf, so mpv.conf does not need changes and it is not recommended to change it. Note the relationship: profile="ini-rjno1" in mpv.conf and [ini-rjno1] in rjno1.conf. The name ini-rjno1 can be changed but must be consistent.

rjno1.conf Usage Notes
Note: There is a parameter in rjno1.conf: osc=xxx (xxx is yes or no). This parameter controls the display/hiding of the OSC (playback control interface).
So when using rjno1.conf, you must ensure that osc=yes and not osc=no, so that mpv displays the OSC interface.
If you don’t understand, you can delete the line osc=xxx from rjno1.conf, then mpv will definitely display OSC.
Why does MPV-EASY Player add the somewhat risky osc=xxx parameter? Because MPV-EASY Player uses an external OSC by default. When osc=xxx is absent or osc=yes, after Windows boots or in some cases, MPV-EASY Player might display mpv’s built-in OSC instead of the external one. Adding osc=no effectively solves this incorrect phenomenon.

portable-data\scripts folder – lua scripts, js scripts obtained from the internet, or your own scripts must be placed here for mpv to read them.
portable-data\XXXXXXX (choose based on mpv version: lua-settings or script-opts) – in this folder, create .conf files with names matching scripts to change settings provided by scripts; specific usage depends on the script author’s explanation.
portable-data\lua-settings\osc.conf – this file can adjust all OSC settings provided by mpv. (For later versions, use script-opts instead of lua-settings.)
portable-data\lua-settings\stats.conf – this file can adjust various parameters of the detailed video info interface; already adjusted to semi-transparent.

Enhancements Provided by Scripts in the portable-data/scripts Folder
Most script files in portable-data can be found on GitHub, some have been slightly modified. Some require you to check the script’s shortcut keys, comments, or the script’s download page for usage. A small number are original scripts for MPV-EASY Player. You can also improve and fix bugs based on the comments in the scripts.

https://./img/mpv-easy-player-osd-bar-lua.jpg

osd-bar.lua – Original by MPV-EASY Player. Combined with parameters starting with osd in rjno1.conf, it can beautifully keep the progress bar always visible (still auto-hides in fullscreen).
playlistnoplayback.lua – Original by MPV-EASY Player. If you enable recording playback history and progress, when playing a playlist, this lua script solves the problem of automatically jumping to the previous playback progress when playing the next file – i.e., each file in the playlist always starts from the beginning. Limitations are noted in the comments.
local-language.lua – Original by MPV-EASY Player. This script enables MPV-EASY Player and mpv to display text in your most familiar language, i.e., localization. It can also separate more localization features from input.conf. For example, after adjusting volume, the OSD shows “Volume: 100%” instead of “volume:100%”, without needing to write show-text in the shortcut config file. It works regardless of command or shortcut used. However, this lua script is not added to MPV-EASY Player’s default scripts because it has some interference and negative effects. But in mpv it should be a very useful script; at least many commonly used command displays can be changed to your preferred language. By default it converts English to Simplified Chinese.
default-input.lua – Original by MPV-EASY Player. Adds modified default shortcut keys via lua and modifies some shortcut functions. Using this lua allows adding default shortcuts without modifying input.conf, and enables good multi-language support for show-text in commands.
use-cpu.lua – Original by MPV-EASY Player. If video width > 3000 or height > 2000, automatically switches back to CPU decoding. Default values can be adjusted. Not included in default scripts.
other.lua or other.js – Original by MPV-EASY Player. Automatically saves the volume so the next playback uses the last adjusted volume. However, to work normally in mpv it needs modification. Known issues and limitations are in the script’s comments.
+change-gpu-api.lua – Original by MPV-EASY Player. Switches vo to gpu and sets gpu-api to opengl.

https://./img/mpv-easy-player-osc-lua.jpg

osc.lua – Modified from the official original. If you understand lua, you can achieve full customization of OSC appearance.
Note: If you want to use mpv’s original OSC interface, delete osc.lua or rename it to a non-lua extension, and ensure rjno1.conf does not contain osc=no.

How to display on mpv’s OSC:

Volume:100% HWDec:d3d11va StayOnTop:no Track:(1) Subtitle:no Resolution:1920x1080 Channels…

Add the following line in osc.conf:

text
title=Volume:${volume}% HWDec:${hwdec-current} StayOnTop:${ontop} Track:${audio} Subtitle:${sub} Resolution:${width}x${height} Channels:${audio-params/hr-channels} FPS:${container-fps}
Refer to mpv’s documentation for more fields, but don’t add too many or they’ll overflow the OSC’s right edge. In MPV-EASY Player, please don’t add this; use the settings interface to adjust.

######################## Interlude ########################

https://./img/mpv-easy-player-4.png

https://./img/mpv-easy-player-4-1.png

The OSC Styles Above Can Exist Not Only in MPV-EASY Player but Also in Your mpv’s OSC
The operation steps are very simple:

From mpv-easy-data/osc-style download all osc-XXX.lua files. These lua files are original creations of MPV-EASY Player (modified from the official osc.lua). Each represents one or more styles.

For Example: osc-mpc-be-blue-box-bar-or-knob-20-60.lua
Why is the filename so long? Because its naming convention is [fileName-osc style-progress bar style-osc transparency range-osc transparency range.lua]. In this case, it means:

osc style = box
progress bar style = bar or knob
osc transparency range = between 20 and 60

Only within this range will it have the best display effect.

How to Make the Example osc-mpc-be-blue-box-bar-or-knob-20-60.lua Take Effect?
Rename osc-mpc-be-blue-box-bar-or-knob-20-60.lua to osc.lua.

Copy the renamed osc.lua to the portable-data\scripts folder, overwriting the existing osc.lua.

Open portable-data\lua-settings\osc.conf and modify as follows (use script-opts for later mpv versions):

text
layout=box
seekbarstyle=bar
boxalpha=45
The parameters layout, seekbarstyle, boxalpha correspond to the OSC style, progress bar style, and transparency range. After modifying osc.conf, restart mpv to see the style change.

If you want to create your own OSC appearance style, see: Tutorial: How to Create OSC Appearance Styles for MPV-EASY Player/MPV Player

######################## Interlude End ########################

autoload.lua – Automatically loads as a playlist.
ontop-playback.lua – Stays on top during playback.
open-file-dialog.lua – Displays an open file dialog, requires pressing the script’s shortcut.
pause-when-minimize.lua – Auto-pauses when minimized.
playlistmanager.lua – Advanced playlist, slightly modified for appearance and multi-language support. Requires pressing the modified shortcut in the script. For all features and usage, check its homepage.

Using Anime4K
Download the latest Anime4K: https://github.com/bloc97/Anime4K/releases

Click the “Installation Instructions for GLSL/MPV (vX.XX)” link on the release page and follow instructions.

Step 1: Put all *.glsl files from Anime4K_vX.X.zip into:
[MPV-EASY Player\data\portable-data\shaders] (create this folder yourself).

Step 2: Open [MPV-EASY Player\data\mpv-easy-data\input.conf].
Open https://github.com/bloc97/Anime4K/blob/master/md/GLSL_Instructions_Windows.md and, according to your GPU performance, fill in the different groups of shortcuts given on the page:

text
CTRL+1 no-osd ******
CTRL+2 no-osd ******
CTRL+3 no-osd ******
...
CTRL+0 no-osd change-list glsl-shaders clr ""
Step 3: Open Task Manager, enable GPU usage monitoring.
Run an anime video with MPV-EASY Player, press CTRL+1 to CTRL+6 to enable Anime4K with different settings. Compare mpv’s GPU usage; if it significantly increases compared to not using it, it’s working. Alternatively, visually compare image quality.
Press CTRL+0 to disable Anime4K.

Step 4: If you don’t want to press shortcuts every time or remember them, use MPV-EASY Player’s “Custom Menu” feature. Clicking the menu item can enable the specified function.

Image Quality and Performance
MPV-EASY Player enables hardware decoding by default, i.e., vo=gpu-next or vo=gpu. Both values can be tuned via the profile option.

When profile contains high-quality (default): best image quality, highest GPU usage (e.g., 24%).
Change high-quality to fast: worst quality, lowest GPU usage (e.g., 4%).
If you want a balance, delete high-quality or fast from the profile, reverting to mpv defaults, which balance quality and performance, GPU usage e.g., 14%.

You can also directly adjust [Video] - [Quality/Performance Preference] in the settings interface for the same effect.

How to Play Online Video Links
Create a txt file, open it with a text editor, copy one or more online video links into the file, one per line.

Save and change the file extension from .txt to .m3u, so it’s recognized as a playlist file.

Double-click the playlist file to start playing. Open the “Advanced Playlist” to jump between all video links.

Example: Watching TV stations (IPTV):
Open https://github.com/iptv-org/iptv/tree/master/streams , find cn.m3u (Mainland China TV stations), copy its content (all online addresses), save to txt, change extension to m3u, double-click to watch.

Advanced Playlist Customization
Using the mouse wheel to operate the playlist (e.g., select previous, next, play selected)

Color Gradient Progress Bar Examples
Although MPV-EASY Player’s settings interface has color picker, palette, and dozens of selectable colors, if you still don’t know which two colors produce a beautiful gradient progress bar, refer to the following examples.

https://./img/slider-demo-20220918.png

Preview Other Parts of the Video via Fast-Forward, Dragging Progress Bar, Then Return to Current Play Position
Using Shortcut Keys:
Mark position: Ctrl+Shift+BACKSPACE
Return to marked position: Shift+BACKSPACE

How to use: Press Mark position, mpv remembers the current playback time. Then you can freely drag, click the progress bar, or fast-forward/rewind to preview any part of the video. Finally press Return to marked position to go back and continue playing.

Using Custom Menu:

Menu Item Name	Shortcut
Mark Position	ctrl+shift+bs
Return to Mark	shift+bs
MPV-EASY Player’s Video Image Not Sharp Enough?
By default, when mpv uses profile=high-quality or default settings, the image appears smoother. For sharper image quality, change high-quality to fast in the profile.

If that’s not enough, you can:

Query available filters for downscaling image size source: Press ` to open command console, enter: set dscale help
Query current downscale filter: Press `, enter: show-text ${dscale} (result shows where volume is displayed)
Query available upscale filters source: ` -> set scale help
Query current upscale filter: ` -> show-text ${scale}

Adjustments and notes 1: See source
Note 2: When the setting Output Driver is direct3d, these filters may not work (check mpv manual).

Available scripts:

+change-dscale.lua – changes the filter used for downscaling.
+change-scale.lua – changes the filter used for scaling.

Sharpen Video Using Custom Menu
Menu Item Name	Shortcut
Sharpen = 2 (sharpen = 2)	s e t space s h a r p e n space 2
After pressing Enter it takes effect. You can manually delete the number 2 and enter another value then Enter.

Note: Sharpening may only work when output driver is gpu (vo=gpu).

Escaping Characters like " \ in Custom Menu
If you want to output special characters like " \ in commands sent via custom menu, you need to escape them: just like space is written as space, " must be written as \\", \ must be written as \\\\ to work correctly.

Giving Settings Values Not Available in the Settings Interface
For example, the settings interface’s Output Driver only includes gpu and direct3d. It corresponds to vo=xxx in [mpv-easy player\data\mpv-easy-data\rjno1.conf].

To set vo=gpu-next, which is not available in the interface, do this:

Note: If using mpv 0.36.0 or older, replace high-quality below with the old writing gpu-hq.

Open [mpv-easy player\data\mpv-easy-data\rjno1.conf] with a text editor.
Find profile=high-quality and change it, for example:

text
profile="high-quality,ini-custom"
Then in the same file, after:

text
[ini-rjno1-playlist]
no-resume-playback=
add (source):

text
[ini-custom]
vo=gpu-next
The line vo=gpu-next in [ini-custom] will override any existing vo=xxx under [ini-rjno1]. You can add more custom settings under [ini-custom], noting they will override same settings from [ini-rjno1].

Example:

text
[ini-custom]
vo=gpu-next
gpu-context=d3d11
d3d11-output-csp=pq
vf="format:dolbyvision=yes"
d3d11-output-format=rgb10_a2
blend-subtitles=no
Explanation (source):

Meaning	Dolby Vision Compatibility
vo=gpu-next	Use latest libplacebo renderer
gpu-context=d3d11	Real-time render engine
d3d11-output-csp=pq	Required for HDR playback on older Win10 API
vf="format:dolbyvision=yes"	Dolby Vision filter
d3d11-output-format=rgb10_a2	rgb10_a2 rgba16f rgba32f
blend-subtitles=no	Essential for external subtitles on HDR video
Background Color of Semi-Transparent Control on Video Turns Gray (Abnormal)
https://./img/color-error-20240410.png

Before fixing this via mpv settings, try updating your graphics driver first – it often solves it permanently.

Three solutions, choose one:

a. When output driver is gpu (vo=gpu), add to [ini-rjno1] in rjno1.conf:

text
d3d11-flip=no
This prevents semi-transparent from turning gray with no performance issue.

b. Change output driver to direct3D (vo=direct3D). But note: under direct3D, scale/dscale filters won’t work. Advantage: GPU usage may drop to 1/3 (e.g., 50% → 18%).

c. When output driver is gpu, add:

text
gpu-api=opengl
This increases CPU usage (e.g., 3% → 10%), GPU usage same as gpu-api=auto (d3d11) (e.g., 50%), but video may stutter.

Interface Text Too Small on High-Resolution (HiDPI) Monitors? (source)
Try logging off or restarting the system once.

Shortcut Keys
How to Write Each Key in mpv’s input.conf to Be Correctly Recognized
The most correct way is to refer to the lines after static const struct key_name key_names[] = { in mpv’s source code file:
https://github.com/mpv-player/mpv/blob/master/input/keycodes.c

For example, space should be written as SPACE, numpad 5 as KP5.

Why Doesn’t MPV-EASY Player’s Settings Interface Provide Custom Shortcut Key Functionality?
If you have used mpv (i.e., MPV-EASY Player’s “MPV Native GUI”), you’ll notice its OSC has no volume slider. To change volume, by default you can only hold the non-numpad 9 and 0. Therefore, in MPV-EASY Player, mouse wheel scrolling is forcibly bound to volume adjustment for convenience.

input.conf can customize all shortcuts, but in mpv, added lua and js scripts can also add their own shortcuts to enable their features. This scatters shortcuts across multiple files, and script shortcuts are often mixed among code, making extraction difficult. This makes obtaining shortcuts and detecting duplicates very hard.

Even more unfortunately, MPV-EASY Player uses a front-end/back-end separation similar to smplayer (believe me, this method is often more suitable than libmpv because it’s simpler for ordinary users to upgrade the mpv core, and script support is easier; you can also run and use mpv independently). When you press a shortcut, the OSD text can only be provided by show-text in input.conf. Supporting multiple languages means input.conf must also handle some language functions. For example, scrolling shows “音量：100%” in Chinese and “volume:100%” in English. If shortcuts were customizable, you’d also need to modify the corresponding show-text text—another challenge.

What’s fortunate? As a player, mpv’s daily use rarely requires custom shortcuts. The preset and modified shortcuts in MPV-EASY Player are sufficient and convenient. If you want to customize some, trust me, manually editing input.conf and script shortcuts is wiser and simpler.

Also, MPV-EASY Player doesn’t “reinvent the wheel” for shortcuts (i.e., nesting shortcuts). You can directly transfer your memory of mpv shortcuts to MPV-EASY Player. If you want to escape memorizing many shortcuts, use the “Custom Menu” feature. It can store and send a single shortcut or a group of shortcuts saved in input.conf or scripts; clicking a menu item can achieve the same result as pressing one or multiple shortcuts.

Note: mpv’s volume adjustment is non-linear. When volume=130, volume is 200% of normal. So when volume-max=200, the maximum adjustable volume is several times normal.

https://./img/mpv-easy-player-auto-input.png

How to Adapt MPV-EASY Player’s Two Folders for mpv (Mac and Linux)
Since MPV-EASY Player doesn’t have Mac and Linux versions, the tutorial above plus the following can let you create an MPV-EASY Player for Mac / MPV-EASY Player for Linux yourself. Although operation functions are simplified, the appearance and functionality during normal use are mostly the same.

Smart you may have realized: you can adjust MPV-EASY Player’s functions on Windows, then transfer these adjusted files to Mac or Linux, saving the trouble of manually modifying config files and consulting the manual. However, some cautions apply.

Because MPV-EASY Player enables hardware decoding by default, the parameter values for hardware decoding on Mac and Linux may differ from Windows. If you migrate without changing this parameter, playback may fail—most commonly, double-clicking to play causes mpv to flash and exit.
If you encounter this, check the parameter vo. It’s in:

mpv-easy-data\rjno1.conf

Also ensure hwdec=auto in rjno1.conf (so hwdec doesn’t cause failure). Since vo and hwdec are critical and influence each other, when playback fails, the root is often related to these two.

When hwdec=auto, in that file, check the mpv manual to see if the value after vo= is supported on your system. If incompatible, manually change it to a compatible value.

If you don’t want to figure this out and just want mpv to work on Mac/Linux, very simple: when adjusting MPV-EASY Player’s functions on Windows, switch hardware decoding to software decoding in the settings interface, then transfer those files. Software decoding is compatible across all systems.

If you’ve already mastered the two methods described in “How to Adapt MPV-EASY Player’s Two Folders for mpv (Windows)”, migrating settings to Mac and Linux is easy.

Place the contents of portable-data and mpv-easy-data folders into the following paths according to their structure, then modify mpv.conf similarly to the tutorial above.

Linux
Linux (~ represents the home partition. .config is a hidden folder; enable “show hidden files” in file manager. The mpv folder may need to be created):

text
~/.config/mpv/XXXXXXX   (choose based on version: lua-settings or script-opts)
~/.config/mpv/scripts
~/.config/mpv/mpv.conf
~/.config/mpv/mpv-easy-data
Mac
Mac (~ represents your home directory. .config is hidden; from home folder press Command+Shift+G and enter .config to go there. The mpv folder may need to be created):

https://./img/mpv-easy-player-mac.jpg
https://./img/mpv-easy-player-in-mac-os-x.png

Home directory = Finder -> Mac -> Mac system partition -> Users folder -> your username folder
No home? no no no. For most Mac users, home is on the system partition. If you have partitioned and used Settings -> Users & Groups -> right-click current user -> Advanced Options -> Home directory, you can mount home to a non-system location, similar to Linux. Benefits: personal data and settings completely separated from system; clean OS reinstall.

text
~/.config/mpv/XXXXXXX   (choose lua-settings or script-opts)
~/.config/mpv/scripts
~/.config/mpv/mpv.conf
~/.config/mpv/mpv-easy-data
Some Defects of mpv for Mac (present at version 0.28.2)

mpv for Mac has a display defect in OSC styles: changing the progress bar style via seekbarstyle parameter still shows an unchanged or different style than documented. If you encounter this, open:

~/.config/mpv/lua-settings/osc.conf (or script-opts for later versions)

Comment out the seekbarstyle line with #, i.e.:

seekbarstyle=*** -> #seekbarstyle=***

If OSC problems persist, also comment out layout line:

layout=*** -> #layout=***

If after adding osc.lua with layout=box the OSC doesn’t change, try modifying your added osc.lua at:

~/.config/mpv/scripts/osc.lua

Swap the code: change layouts["bottombar"] to layouts["box"] and layouts["box"] to layouts["bottombar"]. Because mpv for Mac may ignore layout=*** and forcibly use layout=bottombar. Since the modified style only works when layout=box, swapping moves the modified style code from box to bottombar.
