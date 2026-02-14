## About

CricShot10k is a large-scale video dataset for cricket shot classification, consisting of **10,086 video clips across 15 shot classes**. It covers **men’s, women’s, and under-19 matches**, including older matches dating back to 1996, making it one of the most diverse cricket shot datasets available.

The dataset was created using a **novel automated data-collection method**, which splits full-length match videos into individual shot clips. This eliminates the **time-consuming manual trimming process** that limits the size of existing datasets.

Along with the dataset, we introduce a **modified cricket shot classification framework, CricShotNet**, which incorporates two new layers: automated batter cropping and semi-transparent segmentation mask overlay. The subsequent layers use EfficientNetV2-S and GRU, achieving a classification accuracy of 89% on CricShot10k, outperforming previous state-of-the-art methods.

The purpose of CricShot10k is to provide a solid foundation for research aimed at developing and benchmarking cricket video analysis models.

## Paper Link

Our work is available as a research article in [IEEE Access](https://doi.org/10.1109/ACCESS.2026.3663220).   For any use of the dataset or model structure, **please cite** using:

```bibtex
@ARTICLE{11389735,
  author={Dihan, Mubtasim Kamal and Abdullah and Amina and Ahmed, Sabbir},
  journal={IEEE Access}, 
  title={CricShot10k: A Large-Scale Video Dataset for Cricket Shot Classification}, 
  year={2026},
  volume={},
  number={},
  pages={1-1},
  keywords={Videos;Sports;Accuracy;Feature extraction;Convolutional neural networks;Games;Manuals;Image color analysis;Annotations;Video sequences;Action Recognition;Cricket Shot Classification;Cricket Shot Video Dataset;Efficient-NetV2;GRU;Sports Analytics;Video Classification},
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

The link for the full dataset is available at [Google Drive](https://drive.google.com/drive/folders/13dQHHW8v9gt_jIssQ5PTrJToWGUXvZey?usp=sharing). Each class is be in a separate compressed archive and one needs extract the archives to view the dataset. Note that the dataset is intended solely for non-commercial research purposes, and the copyright of the original videos remains with the respective rights holders. Any research use of the dataset should include an appropriate citation.

Each of our videos is numbered from 1–536 based on the original match videos they were collected from. The list of match videos can be found here: [Match Videos Spreadsheet](https://docs.google.com/spreadsheets/d/1q8bdNIEX9vDCJiFbykNoNb0VNoeNupNwrM-AZHLBXSg/edit)

For any emergency contact, mail: mubtasimkamal@iut-dhaka.edu

## Model Details

Will be updated later.

