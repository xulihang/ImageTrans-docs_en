Tools
==================================================

ImageTrans also comes with a range of tools.

Screen Reader
++++++++++++++++

Make screen captures, OCR and translate. Results can be saved to the project. It can monitor new images copied into the clipboard. The OCR result will be automatically saved in the clipboard.

.. image:: /images/screenreader.jpg

TTS
++++++++++++

It can call the operating system's built-in text-to-speech engines to read text.


Silent Translator
+++++++++++++++++

The pictures can be translated in batch silently. It can be used as in command line.

How:

``java -jar ImageTrans.jar configPath usePrevious detectOnly outdir fileListPath``

Parameters:

configPath: the path of the parameter file. If you open Silent Translator you can see the parameters on the right side.

usePrevious: whether to use the previous data. The optional values are true and false

detectOnly: whether to detect only text areas. The optional values are true and false

outdir: output folder

filelistPath: a list of files to be processed, separated by newlines

It can be used with `ImageTrans_Server <https://github.com/xulihang/ImageTrans_Server>`_ to provide an online service.


Server
+++++++++++++

This tool allows other software to call ImageTrans to translate images.

`ImageTrans Chrome Extension <https://github.com/xulihang/ImageTrans_chrome_extension>`_ relies on this tool.

The extension can use ImageTrans to translate images on webpages Images and processing results will be automatically added to the current project of ImageTrans.


Object Detection Annotation Data Manager
++++++++++++++++++++++++++++++++++++++++

This tool can export or import project data in YOLO data format. Supports OBB format.
