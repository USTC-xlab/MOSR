# MOSR (MSI from Optical Super-Resolution)
MOSR is a Mass Spectrometry Imaging (MSI) super-resolution strategy based on transfer learning, which tremendously reduces the requirement for sample size by transferring the knowledge learned from abundant optical images (~15,000 images) to the MSI model. Once trained, MOSR can take an Low-Resolution MSI image as input and output a reconstructed High-Resolution MSI image in less than one second.

<div align = center> 
<img src="https://github.com/USTC-xlab/MOSR/blob/master/graph.png" width = "600" height = "400" />
</div>

## Introduction
Mass spectrometry imaging (MSI) is a valuable tool for the spatial distribution analysis of chemicals in biological tissue. It has been proven to be extremely useful for applications such as the spatial distribution analysis of molecules in biological tissue, the identification of biomarkers in pathological tissue, and the evaluation of drug pharmacokinetic characteristics. The spatial resolution of MSI is a critical parameter that affects the precise assessment of chemical localizations. Deep learning (DL) utilizing plentiful images is often used to further improve resolution. However, due to limitations in the amount of High-Resolution MSI data publicly available, super-resolution reconstruction of MSI images based on DL is still a challenge. 

## System Requirements
### Hardware requirements
We provide a DEMO model to show the complete pipeline. This DEMO requires only a standard computer with enough GPU memory (at least 5 GB, e.g. NVIDIA RTX3090) to load the model.

### Software requirements
In this work, we used open source image and video restoration toolbox **[BasicSR](https://github.com/xinntao/BasicSR)** to simply build ESRGAN models. Therefore, the software requirements are consistent with the toolbox **BasicSR**.
* **Python >= 3.7 (Recommend to use Anaconda or Miniconda)**
* **PyTorch >= 1.7**
* **NVIDIA GPU + CUDA**
* **Linux**

## Installation Guide
* You can install the toolbox from PyPI, and it will take several minutes.<br/>
```
pip install basicsr
```

## Demo
1. The pre-trained model is released as v1.0.0, and the DEMO **Low-Resolution** images are in the `images/test` folder.
2. Modify the config file in `options/test/test_ESRGAN_x4_MOSR.yml` and assign correct paths for the image and model.
3. Inference. Run the following command, and the images are reconstructed in less than one minute. The `test.py` is in the directory of **BasicSR**.<br/>
```
python basicsr/test.py -opt options/test/test_ESRGAN_x4_MOSR.yml
```

