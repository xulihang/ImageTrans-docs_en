Manga OCR
============

The text of Japanese manga is arranged vertically from right to left, and there will be Furigana for phonetic notation, so the processing methods will be different.

The following is the related features of ImageTrans for manga OCR.

1. Strip Furigana

Check Strip Furigana on the OCR toolbar to remove Furigana in the image during OCR.

Original image:

.. image:: /images/manga/image.jpg

After:

.. image:: /images/manga/no_furigana.jpg

2. Vertical to Horizontal

Check Vertical to Horizontal in the OCR toolbar so that the text will be rearranged in during OCR. In this way, many OCR engines that can only recognize horizontal Japanese can also be used. However, this method only applies to images with a simple background.

Original image:

.. image:: /images/manga/vertical.jpg

After:

.. image:: /images/manga/horizontal.jpg

3. Parameter Setting of The Heuristic Text Detection Method

The default heuristic text detection method merges horizontally and then vertically. For manga, it can be set to merge vertically and then horizontally. The overlapping ratio of text lines can also be adjusted to avoid the problem of merging different paragraphs.

4. Right to Left Reading Order

Check this option in project settings so that when merging text areas, the text on the right will be placed in the front.

Note: If the OCR engine can directly recognize vertical Japanese, you don't have to perform Vertical to Horizontal conversions.
