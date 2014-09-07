blender-sculpt-geometry-tools
=============================

A set of convenience tools for Blender's dynamic topology sculpting.

An additional "Geometry" panel will appear in the Sculpt tab of your Toolshelf. It'll have the following tools:

- Smooth
- Laplacian Smooth
- Decimate
- Displace
- Subdivide
- Subdivide Smooth
- Beautify

The last three are edit mode operators (no live preview). The rest are shortcuts for applying modifiers.

# Usage

Make sure you're in Sculpt mode. The buttons will be grayed out until then. You can use them either in plain sculpting or in Dynamic Topology mode.

When you click a tool, a popup window with all the modifier's settings will appear. Some of the settings (like Triangulate or vertex groups) are filled in by the addon and thus are not exposed. If you click "OK", the modifier will be applied. If you hit Escape or click outside of the popup, the modifier will be discarded and removed from the stack.

Subdivide (Smooth) and Beautify don't expose any options, they're just instantly applied to a non-masked area.

All the tools try to use masking when possible, i.e. will only affect non-masked areas. If you have Dynamic Topology enabled prior to using any of the tools, it'll be enabled again once the tool has done its work.

# Caveats

- The tools do not support Multiresolution sculpting.
- Undo is a little awkward: you'll need to undo several steps to get back where you started.
- Viewport cannot be navigated while operator popup is displayed.
- Not every setting supports masking (i.e. Decimate in modes other than Collapse).
- Decimate does not preserve the mask when applied. It will affect only the non-masked area, but after it's done, your mask will be gone.

# Installation

1) Change to your addons directory:
```
cd $HOME/.config/blender/<2.71+>/scripts/addons
```

2) Clone the repository:
```
git clone https://github.com/radcapricorn/blender-sculpt-geometry-tools.git sculpt_geometry_tools
```

3) Activate the addon in Blender's User Preferences.

Alternatively, if you're not using git, download zip file and use Blender's Install From File button.
