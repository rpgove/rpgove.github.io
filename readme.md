To convert an image named `speed-comparison.png` to 1x and 2x thumbnails:

    convert speed-comparison.png -set filename:basename "%[basename]" -thumbnail x200 +write %[filename:basename]-thumb-2x.png -thumbnail x100 +write %[filename:basename]-thumb-1x.png

