# Masked Texture Synthesis with Multiresolution Pyramid Rendering

This repository contains a Tensorflow implementation which performs texture analysis given a doodle drawing and some input textures corresponding to the colors in this drawing. The algorithm will then create a composition using these input textures and the given drawing.

This algorithm makes use of Multiresolution Pyramid Rendering to improve the quality and increased resolution of the result.
To further improve the quality of the resulting composition we make use of several loss functions, including Gram, Histogram and Total Variance loss.

## Setup

#### Dependencies:
* [tensorflow](https://github.com/tensorflow/tensorflow)
* [Jupyter Notebook](http://jupyter.org/) which can be installed through [Anaconda](https://www.continuum.io/DOWNLOADS)

#### Optional (but recommended) dependencies:
* [CUDA](https://developer.nvidia.com/cuda-downloads) 7.5+
* [cuDNN](https://developer.nvidia.com/cudnn) 5.0+

#### After installing the dependencies: 
* Download the [VGG-19 TensorFlow weights](https://mega.nz/#!xZ8glS6J!MAnE91ND_WyfZ_8mvkuSa2YcA7q-1ehfSm-Q1fxOvvs)

## Usage
Run the iPython notebook `transfer.ipynb` and change the parameters. The code is sufficiently commented to explain itself.

## Examples
### Loss functions
<table>
<tr><th>Input image</th><th>Gram</th><th>Gram + Histogram + TV</th></tr>
<tr><td><img src="examples/starrynight_small_resized.png" width="250"></td><td><img src="examples/gram_starrynight_iter200.png" width="250"></td><td><img src="examples/gram_hist_tv_starrynight_iter200.png" width="250"></td></tr>

<tr><td><img src="examples/panter_resized.png" width="250"></td><td><img src="examples/gram_panter_iter200.png" width="250"></td><td><img src="examples/gram_hist_tv_panter_iter200.png" width="250"></td></tr>

<tr><td><img src="examples/pebbles_resized.png" width="250"></td><td><img src="examples/gram_pebbles_iter200.png" width="250"></td><td><img src="examples/gram_hist_tv_pebbles_iter200.png" width="250"></td></tr>
</table>

### Doodle masking
<table>
<tr><th>Input image</th><th>Corresponding mask</th><th>Synthesized</th><th>Pyramid</th></tr>
<tr><td><img src="examples/panter_resized.png" width="250"></td><td><img src="examples/mask.jpeg" width="250"></td><td rowspan="2"><img src="examples/triangle_tiger_panter_nopyramid_iter200.png" width="250"></td><td rowspan="2"><img src="examples/triangle_tiger_panter_pyramid_iter50.png" width="250"></td></tr>
<tr><td><img src="examples/tiger_resized.png" width="250"></td><td><img src="examples/mask_inv.jpg" width="250"></td></tr>
</table>
