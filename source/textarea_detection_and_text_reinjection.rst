Text Area Detection and Translation Reinjection
==================================================

ImageTrans implements a set of text area detection and translation reinjection methods.

.. _text-detection:

Text Area Detection
-------------------

ImageTrans supports four text detection methods: text detection provided by OCR, balloons (bubbles) detection using deep learning object detection, rule-based heuristic detection method and natural scene text detection method. For more information, please refer to this blog post: `Choose a Suitable Text Detection Method for Image Translation <https://www.basiccat.org/choose-a-suitable-text-detection-method-for-image-translation/>`_.

Here, we mainly explain the heuristic and natural scene text detection methods.

Heuristic
+++++++++++++++

The heuristic method can generate text areas more accurately and provide detailed parameter settings, which can be adjusted for different comics to achieve better results.

Operation:

1. Click Edit->Detect text areas (heuristic) to get all the candidate text areas
2. Click Edit->Text area operation->Get text area confidence. The box color of areas which are unlike text areas will turn to yellow. This kind of area can be removed or hidden. But because some areas are mistakenly identified as non-text areas, it is not recommended to remove them directly.
3. Select the text area to perform OCR and translation. After that, you can remove areas without source text or target text through Edit->Text area operations.

.. image:: /images/textareas.jpg

Operations such as OCR will automatically skip low-confidence areas.

Because different comics have varous sizes, different text area detection parameters need to be set, which can be done through Project->Settings->Text Area Detection

The algorithm details of text area detection can be found here: `Rules-based comic text detection method <http://blog.xulihang.me/text-localization-for-comics/>`_.

The confidence of text areas is obtained using a CNN model retrained using TensorFlow's script. See the code here: `<https://github.com/xulihang/text-image-classifier>`_.

The opreations for text area detection can be done manually in steps via Edit-Text area operations and the merge buttons in the right editing area.

Natural Scene Text Detection
++++++++++++++++++++++++++++++

The natural scene text detection allows users to call open source natural scene text detection methods such as DB, EAST and CRAFT, which have high accuracy and can detect tilted text. But it generally take a long time to produce the result.


Translation Reinjection
-----------------------

Translation reinjection consists of two steps: source text removal and replacement of target text.

Source Text Removal
+++++++++++++++++++

There are two modes of text removal One is the precision mode and the other is the imprecision mode.

In precision mode, text mask will be generated first, and then restore the background according to the mask. There are two ways to restore the background: one is to use the image inpainting method, and the other is to use the background color to generate a text mask to cover the text. If the mask is generated incorrectly, it can be modified through Edit->Generate/Edit mask. The mask image will be saved in the picture folder with a mask suffix, while the text-removed image has a text-removed suffix.

Note:

1. If the mask is not generated manually, mask and text-removed images are automatically generated every time you switch to the translated version. The generation will takes time.
2. For areas with light font color, you need to set the background color and text color first or enable relevant project settings so that the program will reverse the image color to generate mask correctly.

In imprecision mode, a rectangular box will be generated with a colored background to cover text. If the box has no source text nor target text, it will be transparent. This mode is more suitable for digital images with a simple background.

The following image shows the Mask Editor and the Text Remover, which can be used to adjust the mask and text removal results:

.. image:: /images/mask_editor_and_text_remover.jpg

There is plug-in support for mask generation and image inpainting to use third-party methods. The existing plug-ins are `Sickzil-machine  <https://github.com/xulihang/ImageTrans_plugins>`_ and `Lama <https://github.com/xulihang/ImageTrans_plugins/tree/master/LamaInpaint>`_.


Other cases:

If a text-free original image exists, that text-free original image can be set through the `Textless Original Image and Pure-Text Image Manager <https://github.com/xulihang/ImageTrans-docs/issues/199#issuecomment-1133639931>`_. The original image will be directly used when viewing the translated image.


For more information, please refer to this blog post: `Details about Image Text Removal using ImageTrans <https://www.basiccat.org/details-about-image-text-removal-using-imagetrans/>`_.

Translation Replacement
+++++++++++++++++++++++

You can adjust the location and size of the target text boxes. The font size will be automatically adjusted. You can set this in the project settings.


Color Detection
+++++++++++++++

This tool can automatically detect the background color and text color roughly. Click Edit->Color operations to do the detection.

Rotation Detection
++++++++++++++++++

This tool supports detecting the angle of rotated text, which can be operated through the Edit->Text Area Operation menu or custom workflow.




