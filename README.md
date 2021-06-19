# :heart: :microscope: Dataset<br> Healthy and MI Left-Ventricular Rabbit Cardiac Tissue  <br> High Resolution Multi-Channel Confocal Microscopy Data


## :peanuts: In a Nutshell

- Image data & segmentations
  - Biopsy regions:
    - Control tissue
    - 200 μm (region 1) away from the myocardial infarction (MI)
    - 250–750 μm (region 2) away from the MI
    - 1,000–1,250 μm (region 3) away from the MI

### Processed Image Data (z-Stack)

https://user-images.githubusercontent.com/24453528/122386380-2049ed00-cf6e-11eb-885a-f456804995c9.mp4

### Segmentation: Control Stack

![controlSeg](https://user-images.githubusercontent.com/24453528/122387530-3efcb380-cf6f-11eb-89ab-3b61077e9e7a.png)

### Segmentation: Infarct Stack

![infarctSeg](https://user-images.githubusercontent.com/24453528/122387330-0e1c7e80-cf6f-11eb-9577-f1656d4331eb.png)

## :writing_hand: Citation / Attribution

The creation and curation of the dataset was long time effort. We would also like to attribute the work of Thomas Kok, who contributed with segmentations. If you use the dataset or find it helpful, please reference our paper:


> <b>Greiner†, J., Sankarankutty†
, A. C., Seemann, G., Seidel, T., & Sachse, F. B. (2018).</b> <br>
> Confocal microscopy-based estimation of parameters for computational modeling of electrical conduction in the normal and infarcted heart. Frontiers in physiology, 9, 239. <br><br><b>† authors contributed equally</b>

[https://www.frontiersin.org/articles/10.3389/fphys.2018.00239/full](https://www.frontiersin.org/articles/10.3389/fphys.2018.00239/full)

```
@article{greiner2018confocal,
  title={Confocal microscopy-based estimation of parameters for computational modeling of electrical conduction in the normal and infarcted heart},
  author={Greiner, Joachim and Sankarankutty, Aparna C and Seemann, Gunnar and Seidel, Thomas and Sachse, Frank B},
  journal={Frontiers in physiology},
  volume={9},
  pages={239},
  year={2018},
  publisher={Frontiers}
}
```

## :gear: In Detail
- See publication!
- Subepicardial/midwall left ventricular tissue biopsies
- Multi-Channel:
    - DAPI (Sequence 1)
    - WGA (Sequence 2)
    - Connexin43 (Sequence 1)
    - aSMA (Sequence 2)
    - Vimentin (Sequence 3)
- Resolution of 200nm
- Field of view: 204µm x 204µm
- Healthy & diseased
- Segmented: cardiomyocytes, fibroblasts, myofibroblasts, capillaries

## :snake:	Getting Started: Python
### Reading
```python
import h5py
filePath = 'path_to_downloaded_h5_file.h5'
with h5py.File(filePath, 'r') as hdf5fileObj:
  data = hdf5fileObj['ITKImage/0/VoxelData'][:]
```

```python
import itk
filePath = 'path_to_downloaded_h5_file.h5'
data_itk = itk.imread(filePath)
data_numpy = itk.GetArrayFromImage(data_itk)
```
### Visualization

- matplotlib

```python
import matplotlib.pyplot as plt
z_index = 10
plt.figure()
plt.imshow(data[z_index,:,:])
plt.show()
```

- napari

```python
import napari
viewer = napari.view_image(image_data, name='image name')
labels_layer = viewer.add_labels(segmentation_data, name='segmentation name')
```


[comment]: <> (Include napari visualization)


## :desert_island:	Getting Started: Fiji

- Download [Fiji](https://imagej.net/software/fiji/downloads)

https://user-images.githubusercontent.com/24453528/122604702-abaea580-d076-11eb-97d4-54630f031de1.mp4

## :mag_right:	Getting Started: 3D Visualization

- Download [ParaView](https://www.paraview.org/download/)

## :mag:	Getting Started: Virtual Reality

- Download [ParaView](https://www.paraview.org/download/)

## :printer:	Getting Started: 3D Printing

![3dprint](https://user-images.githubusercontent.com/24453528/122407897-3f527a00-cf82-11eb-93ec-d0081c064edc.png)
