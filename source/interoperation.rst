Interaction with Third-Party Software
==================================================

PSD-related
------------------

ImageTrans can intereact with Photoshop using scripts.

Note: If you are on a Windows system and have a full version of Photoshop installed, ImageTrans provides exe scripting tools that automatically open PS. In other cases, you need to open the PS yourself and click File->Script->Browse to run the scripts.

Photoshop Script Repository: `<https://github.com/xulihang/ImageTrans_PhotoshopScripts>`_

PSD to JPG
+++++++++++++

The software does not support PSD files directly. You need to convert PSDs to JPGs first.

Open the conversion tool via Tools->PSD to JPG. It will call Photoshop to do the bulk conversion.

Non-Windows systems have to use the provided JSX script: pdf2jpg.jsx. Select the directory that needs to be converted.

Read Text Areas from PSDs
++++++++++++++++++++++++++++++++++

If you are working on a PSD file, you can read the coordinates, size, and text of text layers in the PSD file, display it in ImageTrans, and automatically replace the text with translation without generating an overlay layer. Click the Edit->Read text layers from PSD files, if present.

Non-Windows systems have to use the provided JSX script: readTextLayers.jsx. Select the folder to export, and then click Project->Import text areas exported with PS scripts to import.

Read Font Name
+++++++++++++++

The font name is in a PS-specific format, which can be obtained using readFont.jsx. The script reads the font information of the first text box.

Generating PSD
+++++++++++++++

After the translation is completed, you can generate a PSD file for further adjustment in PS. Click File-Generate editable PSD files to bring up the generating options dialog box.

Here's a description of the options:

* PSD exists - directly process the original PSD file. PSD files have to be put together with the JPG files. If it is not checked, new PSD files will be generated based on the JPG files.
* Replace with translation - Otherwise the source text will be used.
* Add overlay mask - Add overlays to cover the source text. If the text area corresponds to a text layer in the PSD, no overlay will be added.
* Use Precision Mode - The overlay in imprecision mode is a rectangular box. In precision mode, the software will accurately remove text.
* Flip image horizontally - for Chinese Comics Translated into Japanese Comics
* Use point text - All text boxes will use point text.
* Export only - Export data files only. Do not run Photoshop.

.. image:: /images/generating_options.jpg

Please patiently wait until the prompt window pops up indicating the operation is done. During the operation you can switch to the window of PS to view the operation in progress. If PS displays relevant dialogs, you need to handle them manually.

Non-Windows systems have to use this script: addLayers.jsx.

Others
------------------

Use File->Export to export text as a docx document for others to translate. ImageTrans can reimport the translation.

In addition, the tool's project files are stored in json format and you can write your own programs to handle them.