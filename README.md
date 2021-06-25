# NIC@HMS python2: Intro to image processing

## setup

### install miniconda

https://docs.conda.io/en/latest/miniconda.html

If you haven't already, add conda forge to your channels

```sh
conda config --add channels conda-forge
conda config --set channel_priority strict
```

> tip: to download a version of miniconda with conda-forge already
> setup, use [miniforge](https://github.com/conda-forge/miniforge)

### clone or download this repository

```sh
# to clone
git clone https://github.com/tlambert03/hms_pyintro2.git
```

or download and unzip:
https://github.com/tlambert03/hms_pyintro2/archive/refs/heads/master.zip

... then `cd` into the new directory

```sh
cd hms_pyintro2
```

### create a new environment for this tutorial

```sh
conda create -n imgproc python
conda activate imgproc
```

> note: anytime you close and reopen your terminal, you'll need to
> reactivate your conda environment with `conda activate <name_of_env>`

### install requirements

```sh
pip install -r requirements.txt
```

> this will `pip install` each of the requirements listed
> in the [`requirements.txt`](requirements.txt) file.  You could also install them with
> conda if you'd like.  See the [previous lecture](https://nic.med.harvard.edu/python/) for details on pip vs conda.

### start one of the tutorials

```sh
jupyter-lab 01_image_io.ipynb
```

## Summary & links to more reading

- [`pathlib.Path`](https://docs.python.org/3/library/pathlib.html) for
  filesystem operations. (offers similar functionality to the [`os.path`
  module](https://docs.python.org/3/library/os.path.html), in an object-oriented
  design)
- Open files (like text files) with
  [open](https://docs.python.org/3/library/functions.html#open), or
  [`Path.read_text`](https://docs.python.org/3/library/pathlib.html#pathlib.Path.read_text)
- Loading image data:
  - [tifffile](https://github.com/cgohlke/tifffile) - read and write TIFF files.
    Used internally by many other packages.
  - [imageio](https://github.com/imageio/imageio) - read and write a [wide
    range](https://imageio.readthedocs.io/en/stable/formats.html) of image data
    (but use
    [`volread`](https://imageio.readthedocs.io/en/stable/userapi.html?highlight=volread#imageio.volread)
    instead of `imread` for nd tiffs)
  - [scikit-image io
    module](https://scikit-image.org/docs/dev/api/skimage.io.html) - Utilities
    to read and write images in various formats.  Wraps `tifffile` and
    `imageio`, and other plugins.
  - [pims](https://github.com/soft-matter/pims) - consistent interface for image sequences. offers [Bioformats wrapper](http://soft-matter.github.io/pims/v0.5/bioformats.html), and pure-python nd2 readers with [`nd2reader`](https://github.com/rbnvrw/nd2reader) and [`pims_nd2`](https://github.com/soft-matter/pims_nd2).
  - so many others... let me know if you have a challenging image format...
- Viewing images:
  - [`matplotlib.pyplot.imshow`](https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.imshow.html?highlight=imshow#matplotlib.axes.Axes.imshow) excellent image viewer with lots of options... but mostly designed for 2D data.
  - [`napari.view_image`](https://napari.org/api/stable/napari.html?highlight=view_image#napari.view_image) view n-dimensional arrays in the [napari](https://napari.org/) viewer.
  - [`napari.view_path`](https://napari.org/api/stable/napari.html?highlight=view_path#napari.view_path), open file path in napari viewer.  Can install use [napari plugins](https://pypi.org/search/?q=&o=&c=Framework+%3A%3A+napari) to read proprietary formats.
- [Numpy](https://numpy.org/) - the fundamental package for scientific computing in Python.  It's critical to understand the basics of working with numpy arrays when dealing with image data (indexing, slicing, operations, etc...).  Start with the [quickstart](https://numpy.org/doc/stable/user/quickstart.html) and go from there...
- Saving images:
  - `tifffile.imsave`
  - [`skimage.io.imsave`](https://scikit-image.org/docs/dev/api/skimage.io.html?highlight=io#skimage.io.imsave)
  - [`numpy.save`](https://numpy.org/doc/stable/reference/generated/numpy.save.html)

#### next steps ... (not covered here) 

- Start with [scikit-image](https://scikit-image.org/) for most of your basic image processing and analysis needs.
  - Start with the [user-guide](https://scikit-image.org/docs/stable/user_guide.html)
  - tutorial on [scikit-image with napari](https://github.com/jni/i2k-skimage-napari)
- [`scipy.ndimage`](https://docs.scipy.org/doc/scipy/reference/ndimage.html) has lots of good functions (filtering, interpolation, measurements) for nd images.
- [OpenCV](https://opencv.org/) has a ton of functionality.
- [napari tutorials](https://napari.org/tutorials/#)
  - [napari training course](https://github.com/sofroniewn/napari-training-course) presented for [NEUBIAS webinar](https://www.youtube.com/watch?v=VgvDSq5aCDQ).
