# Whole-Slide-Image sampler

[GitHub](https://github.com/Peter554/WSI_sampler), [Docs](https://peter554.github.io/WSI_sampler/). (Docs autogenerated with [pydocmd](https://github.com/NiklasRosenstein/pydoc-markdown). *To do: Images not working on docs.*)

This respository aims to develop a tool for sampling from Whole-Slide-Images (WSIs) in an efficient manner. By sampling we mean producing mini-batches of patches which can then be fed to e.g. machine learning algorithms. It aims to work with all WSIs that can be read by [openslide](https://github.com/openslide). Sample data for demos is available [here](https://www.dropbox.com/sh/khsvxpe568f77xm/AABqQYLb6SBonAe77tELccY8a?dl=0) (from [Camelyon 16](https://camelyon17.grand-challenge.org/) dataset).

When sampling patches we would like to be able to assign a class label (e.g. a binary label with normal==0 vs cancer==1). This is facilitated by adding a multi-resolution annotation mask. WSI annotations can be made efficiently with a program such as [ASAP](https://github.com/GeertLitjens/ASAP) and are often stored as xml files (see the [sample data](https://www.dropbox.com/sh/khsvxpe568f77xm/AABqQYLb6SBonAe77tELccY8a?dl=0) for example). These in turn can be converted to the multi-resolution annotation masks we want. *To do: Detail how to achieve this!*

Some features:

- `modules.slide_sampler.Slide_Sampler()`

Used to sample patches from a WSI. We can generate a background mask or add a binary multi-resolution annotation mask:

*left: WSI, middle: generated background mask, right: added annotation mask.*

*To do: CHECK annotation as xml files seems to have multiple regions!?*

<img src='demo/Tumor_004_thumb.png' width='20%'/><img src='demo/Tumor_004_background.png' width='20%'/><img src='demo/Tumor_004_annotation.png' width='20%'/>

We can sample patches from the different classes:

*class 0. 256x256 patches at 10X (downsampling of 4.0).*

<img src='demo/class0_1.png' width='30%'/><img src='demo/class0_2.png' width='30%'/><img src='demo/class0_3.png' width='30%'/>

*class 1. 256x256 patches at 10X (downsampling of 4.0).*

*To do: CHECK are these really cancer?!*

<img src='demo/class1_1.png' width='30%'/><img src='demo/class1_2.png' width='30%'/><img src='demo/class1_3.png' width='30%'/>










