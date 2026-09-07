Settings
==================================================

General settings
----------------

.. _balloon-detection:

Balloon Detection
++++++++++++++++++++


The tool's balloon (bubble) detection uses offline balloon detection models trained by Darknet YOLO, YOLOv8 or TensorFlow Object Detection API.

You can find existing offline models and training methods here: `<https://github.com/xulihang/balloon-dataset>`_.

It can also uses object detection services provided by Baidu EasyDL and Azure.  You need to create your own account and train your own model.

Recommended labeling methods:

Box text areas in all balloons. Let the box fits the text as closely as possible.

.. image:: /images/image_annotation.JPG

After the model is published, you can set the URL through File-Preferences-API setting. The corresponding API key is also required.


Text Image Recognition
+++++++++++++++++++++++

By default, the software uses the local model to recognize text and non text areas. You can also call an API service.

The default address is: `<http://127.0.0.1:8082/classify>`_

Please run the code in the following repository: `<https://github.com/xulihang/text-image-classifier>`_.

Natural Scene Text Detection
+++++++++++++++++++++++++++++

DB, EAST and CRAFT natural scene text detection methods are supported.

The default address is: `<http://127.0.0.1:8080/detect>`_

Project 1: `<https://github.com/xulihang/ImageTrans_plugins/tree/master/mangaTranslatorOCR>`_.

Project 2: `<https://github.com/xulihang/ImageTrans_SceneText_Detection>`_.


API Settings
------------

Click File->Preferences->API to set up APIs for OCR and machine translation services provided by Baidu, Youdao, Microsoft, Tencent, etc.

.. image:: /images/api_setting.jpg

The following is a list of services that need to set the API key.

OCR:

* `Google <https://cloud.google.com/vision/docs/ocr>`_
* `Clova <https://clova.ai/>`_
* `Baidu <https://cloud.baidu.com/product/ocr_general>`_
* `Tencent <https://cloud.tencent.com/product/generalocr>`_
* `Youdao <http://ai.youdao.com/product-ocr-print.s>`_
* `OCRSPACE <https://ocr.space/OCRAPI>`_
* `Microsoft Azure <https://azure.microsoft.com/zh-cn/services/cognitive-services/computer-vision/>`_


For Machine translation, see BasicCAT's `docs <https://docs.basiccat.org/en/latest/advancedFeatures.html#id2>`_.

Appearance Settings
-------------------

Go to File->Preferences->Theme to adjust the appearance. In addition to the default theme, there are black and green themes.

You can also use external CSS to adjust the appearance of the software.

For example, the following CSS can control the text size of the text editing areas:

::

    .text-area {
        -fx-font-size: 25 !important;
    }


The font of the text editing areas can also be configured in project settings.

Shortcut Settings
-----------------

All operations on the menu can be set with shortcut keys for quick access.

In addition, it also supports several shortcut key settings:

1. When adjusting the size of the text area, holding SHIFT can maintain the proportion of the text area.
2. When moving the text area, holding SHIFT can keep the horizontal coordinates unchanged. Hold SHIFT as well as Z to keep the vertical coordinates unchanged.
3. The delete key can be used to delete the selected text areas.
4. Multiple selection operations can be performed holding the control key or the command key.
