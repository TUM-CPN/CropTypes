![Alt text](https://github.com/TUM-CPN/CropTypes/blob/master/docs/abstract.png "Title")

**cite**

If you find the data and code interesting, we would appreciate a citation.

```bibtex
@article{marszalek2020self,
  title={Multi-Temporal Crop Type and Field Boundary Classification with Google Earth Engine},
  author={Marszalek, M.; L{\"o}sch, M.; K{\"o}rner, M.; Schmidhalter, U.},
  journal={MDPI preprint doi: 10.20944/preprints202004.0316.v1},
  year={2020}
}
```

Source:
[Marszalek, M.; Lösch, M.; Körner, M.; Schmidhalter, U. (2020), *Multi-Temporal Crop Type and Field Boundary Classification with Google Earth Engine*](https://www.researchgate.net/publication/340769396_Multi-Temporal_Crop_Type_and_Field_Boundary_Classification_with_Google_Earth_Engine)


## Environment setup for Python3

Create a new virtual environment with

    python3 -m venv env
    
activate it

    source env/bin/activate
    
and install requirements

    pip3 install -r requirements.txt 

## Introduction

The following code snipplets show examples of how to perform a classification with the sources and what data is required for this. We would be happy if you test your methods with the same data to compare new methods.

## Crop Data

We have received permission from the Bavarian State Ministry of Agriculture and Forestry (StMELF) to publish a part of the data so that further procedures can be compared. The data will be loaded as follows:

```python
fp = r"../data/crop-data/Test_area.shp"
gpd_frame = gpd.read_file(fp)
gpd_frame.head()
```

The codes in column "NC_ant" stand for:
Potato: 600
Winter barley: 131
Corn: 400
Winter rapeseed: 311
Winter wheat: 115
sugar beet: 603
Other: 1

## Satellite Data

The satellite data have a temporary resolution of 2 weeks and include the average values for raw bands (B1-B12), NDVI, NDWI, REIP and NDWI. 
A total of 2099 fields were randomly selected in Upper Bavaria and corresponding Sentinel-2 data from February to August were added.
The data is already preprocessed and downloaded form Google Earth Engine.
(Interpolation: 2 weeks, Cloud Filter: 20%)

![First-Layer Attention Heads](docs/durnast.gif)

## Classification

The notebook CropType describes the classification model based on a trained model. Our data set includes various satellite data if you want to train an own model.

![Alt text](https://github.com/TUM-CPN/CropTypes/blob/master/docs/croptype.png "Title")