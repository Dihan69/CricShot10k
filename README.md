![My Image](https://github.com/user-attachments/assets/bda16c2d-fd2b-4a0a-a96b-f7c77a0e9fe0)

## About

CricShot10k is a large-scale video dataset for cricket shot classification, consisting of **10,086 video clips across 15 shot classes**. It covers **men’s, women’s, and under-19 matches**, including older matches dating back to 1996, making it one of the most diverse cricket shot datasets available.

The dataset was created using a **novel automated data-collection method**, which splits full-length match videos into individual shot clips. This eliminates the **time-consuming manual trimming process** that limits the size of existing datasets.

Along with the dataset, we introduce a **modified cricket shot classification framework, CricShotNet**, which incorporates two new layers: automated batter cropping and semi-transparent segmentation mask overlay. The subsequent layers use EfficientNetV2-S and GRU, achieving a classification accuracy of 89% on CricShot10k, outperforming previous state-of-the-art methods.

The purpose of CricShot10k is to provide a solid foundation for research aimed at developing and benchmarking cricket video analysis models.

## Paper Link

Our work is available as a research article in [IEEE Access](https://doi.org/10.1109/ACCESS.2026.3663220).  If you find our work useful or for any use of the dataset or model structure, **please cite** using:

```bibtex
@ARTICLE{11389735,
  author={Dihan, Mubtasim Kamal and Abdullah and Amina and Ahmed, Sabbir},
  journal={IEEE Access}, 
  title={CricShot10k: A Large-Scale Video Dataset for Cricket Shot Classification}, 
  year={2026},
  volume={14},
  number={},
  pages={23428-23447},
  keywords={Videos;Sports;Accuracy;Feature extraction;Convolutional neural networks;Games;Manuals;Image color analysis;Annotations;Video sequences;Action recognition;cricket shot classification;cricket shot video dataset;EfficientNetV2;GRU;sports analytics;video classification},
  doi={10.1109/ACCESS.2026.3663220}
}
```


## Dataset Distribution
| No | Class Label       | Count |
|----|-------------------|-------|
| 1  | Cover Drive       | 793   |
| 2  | Defensive         | 587   |
| 3  | Down The Wicket   | 844   |
| 4  | Flick             | 947   |
| 5  | Hook              | 532   |
| 6  | Late Cut          | 325   |
| 7  | Lofted Legside    | 1094  |
| 8  | Lofted Offside    | 1054  |
| 9  | Pull              | 769   |
| 10 | Reverse Sweep     | 257   |
| 11 | Scoop             | 279   |
| 12 | Square Cut        | 1000  |
| 13 | Straight Drive    | 419   |
| 14 | Sweep             | 905   |
| 15 | Upper Cut         | 281   |
|    | **TOTAL**         | **10086** |

## Dataset Examples
https://github.com/user-attachments/assets/091cf5c6-0d5b-4f4e-a2bd-d1c79634f269

https://github.com/user-attachments/assets/27413c3d-52b0-4320-8453-dac0588a72c7

https://github.com/user-attachments/assets/c5338f03-ad1d-41b0-9492-426a11c90b34

https://github.com/user-attachments/assets/0ee5adbc-c2b8-42ef-8dae-3c63718c55b4

## Dataset Demo

A Google Drive link has been added as a demo, containing 5 randomly selected videos from each class: [Demo Videos on Google Drive](https://drive.google.com/drive/folders/1bQd1shtQCnGI1uwrhSw8AB-esi-Xkz_C?usp=drive_link)


## Dataset Link

The link for the full dataset is available at [Google Drive](https://drive.google.com/drive/folders/13dQHHW8v9gt_jIssQ5PTrJToWGUXvZey?usp=sharing). Each class is  in a separate compressed archive and one needs extract the archives to view the dataset. 

Note that the dataset is intended solely for non-commercial research purposes, and the copyright of the original videos remains with the respective rights holders. Any research use of the dataset should include an appropriate citation.

Each of our videos is numbered from 1–536 based on the original match videos they were collected from. The list of match videos can be found here: [Match Videos Spreadsheet](https://docs.google.com/spreadsheets/d/1q8bdNIEX9vDCJiFbykNoNb0VNoeNupNwrM-AZHLBXSg/edit)

For any emergency contact, mail: mubtasimkamal@iut-dhaka.edu

## Data Collection Process

![My Image](https://github.com/user-attachments/assets/ce73067a-d072-46db-b07a-4c36b9868d8e)

We have developed a novel pipeline to automatically trim cricket match highlights into one-second shot videos.

This approach uses multiple fine-tuned YOLOv11 object detection models to detect the striker, bowler, and ball in cricket broadcasts, and then applies logical rules based on recurring patterns during shot execution to identify the starting frame. 

By automating this process, the data collection workflow is reduced to an annotation pipeline similar to those used for text or image datasets, making it more efficient and scalable.

## Model Details


![My Image](https://github.com/user-attachments/assets/db92e93d-acc6-4740-b9b2-44e0b16fb8ce)

All best-performing models used for data collection and different model layers are available at:  [Google Drive](https://drive.google.com/drive/folders/1-nScFpGMzET1SlvQPrFH1XQwG4ChVA8L?usp=sharing)

For efficient preprocessing, we use separate models for cropping and segmentation.  To perform inference, follow the pipeline below:

1. Use the object detection model to crop the region around the **striker and bat**.
2. Resize the cropped video and uniformly sample **15 frames**.
3. Apply the segmentation model to segment the striker and bat.
4. Apply semi-transparent coloring:
   - Striker → **blue**
   - Bat → **green**
5. Pass the processed frames to the **EfficientNetV2 + GRU (128 units)** model for final inference.

## Miscellaneous Datasets

Apart from the shot video dataset, we used four additional image datasets for automated shot splitting and model preprocessing layers:

1. **Player Type Detection**
   - ~600 images of size 1280 × 720  
   - Detects eight types of individuals on cricket fields: Striker, Bowler, Non-striker, Fielder, Umpire, Keeper, Batsman, Other  
   - Used for automated shot splitting during data collection and striker cropping in the model pipeline  

2. **Bat Detection**
   - ~670 images of size 1280 × 720  
   - Detects the bat in the striker’s hand  
   - Used for cropping the bat alongside the striker in the model pipeline  

3. **Ball Detection**
   - ~1900 images of size 1280 × 720, with ~1400 containing objects and the rest being negative samples  
   - Detects the ball in different states  
   - Used for automated shot splitting during data collection  

4. **Striker and Bat Segmentation**
   - ~650 images of size 224 × 224  
   - Masks the exact shapes of two objects: the striker’s body and the bat  
   - Used to semi-transparently color the striker and bat  

The link to these datasets, along with their corresponding YOLO-formatted annotation text files, is available on  [Google Drive](https://drive.google.com/drive/folders/15PndEu4piuzOHA7ZyOWgTKDnyeDn1Xw_?usp=drive_link)

