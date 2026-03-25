# 故障排除指南

阅读前提示：本文档仅翻译原版游戏中自带的troubleshooting.pdf内容。

### The game crashes with a scripting error in line 60, room15.asc.

### 游戏因脚本错误在第60行、room15.asc处崩溃。

This error indicates that your system has not been able to initialize the game audio for some reason. To fix it, try the following:
此错误表明您的系统由于某种原因未能初始化游戏音频。要解决此问题，请尝试以下方法：

-First, try whitelisting the game folder in your antivirus software. Some programs like Avast or Windows Defender will sometimes interfere with the game startup and cause the audio to not initialize.
首先，尝试将游戏文件夹添加到杀毒软件的白名单中。某些程序（如 Avast 或 Windows Defender）有时会干扰游戏启动，导致音频无法初始化。

-If this doesn't work, launch the Configuration Tool, click on "Advanced" on the lower-right corner, and in the "Digital Sound" drop-down, change the audio device to "Default WaveOut Device", "Default DirectSound Device", or "DirectSound (Hardware mixer)".
如果上述方法无效，请启动配置工具(winsetup.exe)，点击右下角的 "Advanced"，在"Digital"下拉菜单中，将音频设备更改为"Default WaveOut Device"、 "Default DirectSound Device"或"DirectSound (Hardware mixer)"。

### Pressing the Esc key to pause/save/quit my game doesn’t work.

### Esc 键无法暂停/保存/退出我的游戏。

The Options menu is not accessible during cutscenes or dialogues. Wait until you regain control of your character, and try again.
在过场动画或对话期间，无法访问选项菜单。请等待至您重新获得角色控制权后再尝试。

### When I bring up the Steam Overlay, I can’t click on it because the cursor is still active in the game.

### 当我呼出 Steam 界面时，由于游戏中的光标仍然处于活动状态，我无法点击它。

This issue might appear if you’re using the Direct3D default graphics driver. To fix this, run the game from your Steam client, select “Launch Configuration Tool”, and select OpenGL in the “Driver” tab.
如果您使用的是 Direct3D 默认图形驱动，则可能出现此问题。要解决此问题，请从 Steam 客户端运行游戏，选择“启动Configuration Tool”，然后在“Driver”选项卡中选择 OpenGL。

### The game stutters or the cursor moves too slowly.

### 游戏卡顿或光标移动过慢。

Run the game from your Steam client and select “Launch Configuration Tool”. You can increase the mouse speed in the “Advanced” tab. If things are still running slowly for you, try changing the graphics driver to OpenGL. If the issues persist, disable Vertical Sync in the “Advanced” tab.
请从 Steam 客户端运行游戏并选择“启动Configuration Tool”。您可以在"Advanced"选项卡中提高鼠标速度。如果问题依旧，请尝试将图形驱动更改为 OpenGL。如果问题仍然存在，请在"Advanced"选项卡中禁用垂直同步。

### I‘m having issues running the game in fullscreen mode under Linux with multiple monitors.我在 Linux 系统下使用多显示器以全屏模式运行游戏时遇到问题。

Run the game in windowed mode using ./ioawn4t --windowed, and set the appropriate scaling for your screen resolution in the cfg file. e.g., game_scale_win=4.
请使用 ./ioawn4t --windowed 命令以窗口模式运行游戏，并在 cfg 文件中为您的屏幕分辨率设置合适的缩放比例，例如：game_scale_win=4。

### My changes to the Linux cfg file aren’t being applied.

### 对 Linux 下的 cfg 文件所做的修改未生效。

There can actually be up to three different cfg files under Linux:

Linux 系统下，实际上最多可能存在三个不同的 cfg 文件：

- The default acsetup.cfg file that will be used the first time the game is run. It’s located in the game’s own “data” folder once unzipped.默认的 acsetup.cfg 文件，在首次运行游戏时使用。解压后，它位于游戏自身的“data”文件夹中。

- $XDG_DATA_HOME/ags/GAMENAME/acsetup.cfg. If this file exists, any changes you wish to make to the game configuration must be made to this file.

  XDG_DATA_HOME/ags/GAMENAME/acsetup.cfg，如果此文件存在，您希望对游戏配置所做的任何更改都必须在此文件中进行。

- $XDG_DATA_HOME/ags/acsetup.cfg. This is a global cfg file that is applied to all AGS games, and overrides the previous one if it exists.

  XDG_DATA_HOME/ags/acsetup.cfg，这是一个全局 cfg 文件，适用于所有 AGS 游戏，如果存在，将覆盖前述文件。

Note: If $XDG_DATA_HOME is not defined, then "$HOME/.local/share" is used instead.
注意：如果未定义 $XDG_DATA_HOME，则使用 "$HOME/.local/share" 代替。

For more details and configuration options, see

欲知更多详情及配置选项，请参阅：

https://github.com/adventuregamestudio/ags/blob/master/OPTIONS.md