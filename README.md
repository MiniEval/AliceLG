# Alice/LG (beta) - A Blender Add-on for Looking Glass Displays

**Author:** Christian Stolze

### Let Alice/LG take your Blender artworks through the Looking Glass! This short guide is to get you started.

## About the Add-on
This add-on was created for the use of Blender with the Looking Glass holographic displays. I am not associated with the Looking Glass Factory and devoloped this add-on privately in my freetime because I'm a fan of [Blender](https://www.blender.org/) as well as the amazing new holographic display technology created by the [Looking Glass Factory](https://lookingglassfactory.com/). 

If you like this add-on and want to do a private donation, thank you for your support! I will most-likely invest it into new hardware, since rendering with an Quad-Core Intel Core i7 increases my coffee consumption way too much ...

[![Donate](https://www.paypalobjects.com/en_US/DK/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=N2TKY97VJJL96)

## About the Repository
This repository is to provide a beta version of the add-on to a limited group of people for testing purposes only. I would like to find and fix the worst bugs before releasing it into the wild and would appreciate if you do not redistribute the provided version. The final source code will be published as a public repository on GitHub with the official release of this addon. 

Please keep in mind that this beta version of the add-on may contain errors that cause Blender to crash. If you find a bug or have any idea for a missing feature, please open an issue in this repository with a detailed description. Thank you for your help and have fun blendering your holograms! :)

## Main Features
- integration into the common Blender workflow
- an optional viewcone representing the Looking Glass volume in the scene
- lightfield viewport in the Looking Glass with:
   - automatic and manual refresh modes
   - a holographic mouse cursor
   - most of the features of a native Blender viewport
- render any camera view as single quilt image or animation
- support for multiple scenes and view layers
- camera & quilt settings are saved with your Blender file
- support for all available Looking Glass displays (including the new Looking Glass Portrait)

## System Requirements
- Windows, macOS, or Linux
- Blender 2.9x
- Holoplay Service App

## Installation


1. Install the Holoplay Service App on your PC or Mac (if not already done).

2. Download the [zip file](https://github.com/regcs/AliceLG-beta/releases/download/v1.0-beta.4/AliceLG-beta4.zip) of this addon.

3. Install _Alice/LG_ in Blender:
   - Open Blender
   - In the main menu, navigate to _Edit → Preferences → Add-ons → Install → Install Add-on_
   - Select the downloaded zip file and click "Install"
   - Enable the add-on by activating the check box on the left

## How to Use

### Add-on Controls

After the installation you find a _Looking Glass_ tab in each Blender viewport. Depending on your current selections, the tab shows up to four control panels & subpanels:

- **Looking Glass.** Contains the Looking Glass display selection, a view resolution selection, and a button to turn on/off the lightfield window. Furthermore, it has two subpanels:

   - **Camera Setup.** Select one of the cameras in the scene to setup a view for the Looking Glass and the quilt rendering. Once

   - **Quilt Setup & Rendering.** Controls for starting a quilt render.

- **Lightfield Window.** The lightfield / hologram is rendered to a separate window, which needs to be placed inside your Looking Glass display. In this category you find options to switch between two different modes for the lightfield Window: _Viewport_ and _Quilt Viewer_. It has two subpanels:

   - **Lightfield Cursor.** In _Viewport_ mode you have the option to display a lightfield mouse cursor in the lightfield window. Only works if the lightfield window is the active window.

   - **Shading & Overlay Settings.** If the lightfield window is in _Viewport_ mode, it basically acts like a native Blender viewport - except that it's a holographic viewport. The settings for this (lightfield) viewport are defined here.

### Lightfield Window & Viewport

The lightfield window is the place where the hologram is rendered. It can be opened via a click on the button: _Looking Glass → Lightfield Window_, if you have a Looking Glass connected and HoloPlay Service is running. After the window was opened, move it to your Looking Glass screen and click the _Looking Glass → Toggle Fullscreen Mode_ button, which appeared in the add-on controls after the lightfield window was opened. (_NOTE: On Windows this should happen automatically_) Only in fullscreen mode the hologram will be displayed correctly in your Looking Glass. The lightfield window can operate in two modes:

- **Viewport.** In viewport mode, it basically acts like a normal Blender viewport in the Looking Glass - except that it is holographic. You can choose between _Auto_ and _Manual_ refresh mode: In _Auto_ mode, the hologram is re-rendered everytime something in the scene changes, while in _Manual_ mode the hologram is only rendered if you click the refresh button. _NOTE: Due to the restrictions in the rendering pipeline Blender currently has for add-on developers, this mode can be quite slow. Hopefully, their will be a solution for that provided in future versions of Blender._

- **Quilt Viewer.** In the quilt viewer mode, you can load or select a rendered quilt image and display it as a hologram in the Looking Glass. So, this mode is basically here to enjoy the fruits of your work. Playing animations is not supported yet. _NOTE: To display the quilt correctly, the correct quilt preset must be selected under _Looking Glass → Resolution__

### Camera Setup & Quilt Rendering

You can render still scenes and animation frames as complete quilt images. You can render for your currently connected device or for any other Looking Glass:

**(1) Rendering for your currently connected device** 
- select your connected Looking Glass (if not aleady selected) and a quilt resolution under _Looking Glass → Resolution_
- select an existing camera in _Looking Glass → Camera Setup → Camera_ or create a new camera by clicking "+" in the same panel
- check the _Looking Glass → Quilt Setup & Rendering → Use Device Settings_ checkbox
- locate the camera to the specific view you would like to render
- adjust the render and post-processing settings in the usual Blender panels (_NOTE: Image dimensions are overwritten by the add-on based on your connected Looking Glass or your manual settings under _Looking Glass → Quilt Setup & Rendering__)
- click on _Looking Glass → Quilt Setup & Rendering → Render Quilt_ or _Looking Glass → Quilt Setup & Rendering → Render Animation Quilt_ in the add-on controls.

**(2) Rendering for other Looking Glasses** 
- select your connected Looking Glass (if not aleady selected) and a quilt resolution under _Looking Glass → Resolution_
- select an existing camera in _Looking Glass → Camera Setup → Camera_ or create a new camera by clicking "+" in the same panel
- uncheck the _Looking Glass → Quilt Setup & Rendering → Use Device Settings_ checkbox
- choose the Looking Glass you want to render for from the list _Looking Glass → Quilt Setup & Rendering → Device_
- choose the quilt preset/resolution you want to render for from the list _Looking Glass → Quilt Setup & Rendering → Quilt
- locate the camera to the specific view you would like to render
- adjust the render and post-processing settings in the usual Blender panels (_NOTE: Image dimensions are overwritten by the add-on based on your connected Looking Glass or your manual settings under _Looking Glass → Quilt Setup & Rendering__)
- click on _Looking Glass → Quilt Setup & Rendering → Render Quilt_ or (if you want to render animation frames) _Looking Glass → Quilt Setup & Rendering → Render Animation Quilt_ in the add-on controls.

The _Render Quilt_ option will render the different views separately. After the last view has been rendered, a quilt will be automatically assembled. For the _Render Animation Quilt_ option, the same will happen for each frame of the animation, which will result in one quilt per frame. After rendering, the created quilt image or animation frames have to be handled in the same way as normal renders. You can still render normal (non-holographic) images in Blender as you usually do. 

_NOTE: Option (2) can be used even if no Looking Glass is connected._

### Incomplete Render Jobs

The add-on attempts to detect Blender crashes during quilt rendering as well as quilt animation rendering and prompts you with an option to continue or to discard an incomplete render job the next time you open the crashed file. The successful detection of an incomplete render job and its continuation requires that:

- the filename of the .blend-file did not change
- the file was saved before starting the render job **OR** no significant changes happended to the setup (e.g., camera position, render settings, etc.)
- the (temporary) view files of the incomplete render job are still on disk and not corrupted

While the add-on tries to check some basic settings, the user is highly recommended to check if the current render settings fit to the settings used for the incomplete render job before clicking the "Continue" button.

If you decide to discard the incomplete render jobs, the add-on will try to delete the view files of the incomplete render job.

_NOTE: This feature is considered to be 'experimental'. It might not detect crashes under all circumstances and might not succeed to continue the rendering always. If you encounter a situation were this feature failed, please submit a detailed bug report._

## License

The Blender add-on part of this project is licensed under the [GNU GPL v3 License](LICENSE).

**The following statement may need revision and may not apply. See Issue #1**

The HoloPlay Core SDK libraries are property of the Looking Glass Factory and are licensed under the [HOLOPLAY CORE LICENSE AGREEMENT](HOLOPLAY-LICENSE). The HoloPlay Core SDK provides the fundamental software basis for the communication between the Looking Glass display hardware and any app created for it. It is, therefore, considered a system library. As a consequence, the linked libraries of this API are distributed in a compiled (non open-source) form with this free software in agreement with the system library exception defined by the GNU GPL v3 License.
