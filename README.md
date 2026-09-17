# before-after_cb-add-on

CollectionBuilder-CSV Add-on: Before-After Image Comparison Slider

This repository provides template files to add an Before-After option into a CollectionBuilder-CSV project. The files in this directory structure can be copied directly into a CB-CSV repository to add the new features.

*note: only compatible with CB-CSV out of the box, not other templates.*

## Before-After Image Comparison Slider

[Before-After](https://github.com/markpbaggett/before-after) is a lightweight web component library for comparing two images, created by markpbaggett for TAMU Library (inspired by twentytwenty and Knight Labs's JuxtaposeJS).
It allows you to compare two images by stacking them on top of each other and providing a slider to reveal one or the other. 

This cb-add-on contains the dependencies and templates files to add a "image_comparison" Item layout and "image-comparison" feature include option to your project.

## How To Use

Add to CB-CSV project:

- Start a CollectionBuilder-CSV project (or use your existing one!).
- Download this add-on to your computer (click "Code" > "Download ZIP", then unzip package).
- Copy all contents in the add-on (all files and folders except the "README.md") and paste into your CollectionBuilder-CSV project. The folder structure in this add-on should match up with your CB-CSV template, adding new files in the correct places (do not delete or overwrite anything in your existing CB project!).

### Embed on Content Page

Select two images from your metadata using their objectid's. 
Use the feature/image-comparison.html include, e.g.

`{% include item/image-comparison.html img1="example001" img2="example002" %}`

Check the comments at the top of the include file "_includes/feature/image-comparison.html" for full options and more details. 

### Add to Item Pages

To create `image_comparison` display_template items:

- Create the Item record following the ["compound object" metadata conventions](https://collectionbuilder.github.io/cb-docs/docs/metadata/compound-objects/). You will have a parent record describing the comparison item, followed by two child rows each describing one image item. 
- The parent record will have the "display_template" value `image_comparison`. The "object_location" column will be blank. 
- The child records will have "display_template" value `image`. Fill in the metadata fields as a normal image Item.

Check the comments at the top of "_layouts/item/image_comparison.html" for front matter options that change the layout for all items. 
There are two main options: "slider" (the image comparison is the main display on the item page) or "side-by-side" (two image thumbs with button to open full screen modal with the image comparison).
