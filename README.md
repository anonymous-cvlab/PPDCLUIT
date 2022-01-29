# Unsupervised Image-to-Image Translation with Patch Pyramid Dual Contrastive Learning for Cross Domain Object Detection   

<br>

<img src='imgs/Overview.gif' align="right" width=960>

<br><br><br>

This repository contains our PyTorch implementation of Unsupervised Image-to-Image Translation with Patch Pyramid Dual Contrastive Learning for Cross Domain Object Detection (PPDCLUIT). In this paper, we propose **P**atch **P**yramid **D**ual **C**ontrastive **L**earning **U**nsupervised **I**mage **T**ranslation (PPDCLUIT) framework to strength the cross domain object detection performance. Built upon the architecture of [CUT](https://github.com/taesungp/contrastive-unpaired-translation) and [DCLGAN](https://github.com/JunlinHan/DCLGAN), our method present a patch pyramid dual contrastive learning startegy for coherent associations at each specific location and include identity loss to further enforce the object instances preservation.  Trained on the images translated by our OA-FSUI2IT, object detection methods (i.e. Faster RCNN, FCOS) can achieve better mAP than those trained on source only, as well as those domain adaptation based methods. As the processing time for our detection framework is determined by the inference time of the employed detector, it can be used for online object detection. 


<img src='./imgs/Overview.png' align="right" width=960>    

<br><br><br>

### **Patch Pyramid Dual Contrastive Learning Unsupervised Image Translation Network**  

<img src='./imgs/Networks.png' align="right" width=960>   

<br><br><br>

## Translation Results  

Qualitative results:  

<img src='./imgs/translation_results.png' align="right" width=960>


### Cityscapes Clear to Foggy  

Quantitative results:   


| Method      |  FID $\downarrow$  | Precision $\uparrow$ | Recall $\uparrow$ | Density $\uparrow$ | Coverage $\uparrow$ |
|-------------|:--------:|:-----------:|:--------:|:---------:|:----------:|
| Source Only |   68.71   |   0.009   |  0.566   |  0.002  |   0.016  |
| CycleGAN    |   45.10   |   0.767   |  0.304   |  **0.729**  |   0.782  |
| CUT         |   42.56   |   0.668   |  0.498   |  0.592  |   **0.930**  |
| DCLGAN      |   48.95   |   0.276   |  0.394   |  0.098  |   0.338  |
| PPDCLUIT    |   **41.96**   |   0.167   |  **0.688**   |  0.053  |   0.340  |

### BDD100K Day to Night  

Quantitative results:   


| Method      |  FID $\downarrow$  | Precision $\uparrow$ | Recall $\uparrow$ | Density $\uparrow$ | Coverage $\uparrow$ |
|-------------|:--------:|:-----------:|:--------:|:---------:|:----------:|
| Source Only |   104.63  |   0.181   |  0.413   |  0.046  |   0.022  |
| CycleGAN    |   17.90   |   0.763   |  0.594   |  0.828  |   0.782  |
| CUT         |   24.17   |   0.711   |  **0.673**   |  0.681  |   0.658  |
| DCLGAN      |   21.92   |   0.784   |  0.485   |  0.965  |   0.633  |
| PPDCLUIT    |   **14.11**   |   **0.842**   |  0.566   |  **1.265**  |   **0.806**  |

&#8595; 

&#8593;









## Detection Results

Qualitative results:  

<img src='./imgs/detection_results.png' align="right" width=960>


### Cityscapes Clear to Foggy  

Quantitative results:   


### BDD100K Day to Night  

Quantitative results:   

| Methods     |   Detector  |  Bike |  Bus  |  Car  | Motor | Person | Rider | Traffic Light | Traffic Sign | Truck |  mAP &#8593; |
|-------------|:-----------:|:-----:|:-----:|:-----:|:-----:|:------:|:-----:|:-------------:|:------------:|:-----:|:-----:|
| Source Only |     FCOS    |  0.3  |  5.7  | 35.4  |  0.7  |  33.0  | 21.4  |     21.5      |     42.3     | 12.6  | 12.5  |
| CycleGAN    |     FCOS    | 15.0  | 16.7  | 53.1  | 35.1  |  37.2  |  9.0  |      9.0      |     38.0     | 24.4  | 23.1  |
| DRIT        |     FCOS    | 12.1  | 12.8  | 52.7  |  2.3  |  29.3  |  3.0  |     15.1      |     38.6     | 20.2  | 20.7  |
| ForkGAN     |     FCOS    | 10.1  | 15.3  | 50.8  |  3.6  |  32.9  |  5.7  |      8.7      |     33.4     | 24.1  | 20.5  |
| CUT         |     FCOS    |  7.2  | 12.7  | 53.2  |  4.1  |  33.5  |  7.8  |     12.8      |     40.0     | 23.8  | 21.7  |
| DCLGAN      |     FCOS    | 15.5  | 15.3  | 55.6  |  2.6  |  35.2  | 10.7  |      8.8      |     35.2     | 23.1  | 22.5  |
| PPDCLUIT    |     FCOS    | 11.2  | 11.8  | 55.0  |  6.3  |  31.9  |  6.8  |     15.6      |     39.0     | 25.8  | 22.6  |
| Oracle      |     FCOS    | 21.5  | 21.4  | 67.6  |  4.9  |  39.8  |  7.9  |     48.9      |     58.3     | 32.5  | 33.6  |



| Methods     |   Detector  |  Bike |  Bus  |  Car  | Motor | Person | Rider | Traffic Light | Traffic Sign | Truck |  mAP &#8593; |
|-------------|:-----------:|:-----:|:-----:|:-----:|:-----:|:------:|:-----:|:-------------:|:------------:|:-----:|:-----:|
| Source Only | Faster RCNN | 18.5  | 29.8  | 37.5  | 16.3  |  26.1  | 14.3  |     14.6      |     33.1     | 30.7  | 22.1  |
| CycleGAN    | Faster RCNN | 12.0  | 15.7  | 57.7  |  8.7  |  34.9  | 16.3  |      8.9      |     38.3     | 26.6  | 24.4  |
| DRIT        | Faster RCNN | 15.7  | 25.3  | 53.2  |  7.7  |  31.8  | 16.1  |     11.7      |     39.3     | 31.0  | 25.7  |
| ForkGAN<sup>*</sup>     | Faster RCNN | 16.4  | 33.3  | 41.2  | 15.9  |  26.3  | 13.0  |     16.2      |     34.5     | 32.1  | 22.9  |
| ForkGAN     | Faster RCNN | 18.7  | 22.7  | 54.1  | 12.0  |  35.5  | 17.0  |      4.3      |     32.9     | 29.7  | 25.2  |
| CUT         | Faster RCNN | 18.9  | 19.5  | 56.4  | 11.6  |  35.4  | 14.1  |     10.4      |     38.6     | 26.2  | 25.7  |
| DCLGAN      | Faster RCNN | 16.6  | 22.1  | 57.6  |  8.6  |  36.7  | 17.1  |      8.6      |     33.2     | 28.4  | 25.4  |
| PPDCLUIT    | Faster RCNN | 19.3  | 22.2  | 57.9  | 10.2  |  35.3  | 12.9  |     14.1      |     37.7     | 25.4  | 26.2  |
| Oracle      | Faster RCNN | 17.6  | 24.4  | 69.3  |  8.2  |  41.3  | 10.2  |     31.3      |     52.4     | 37.8  | 32.5  |




## t\-SNE Result  
To validate our translation method, we use TSNE to visualize distribution of images from source domain, target domain and generated.   


### Acknowledgments   
Our code is developed based on [contrastive-unpaired-translation](https://github.com/taesungp/contrastive-unpaired-translation/) and [DCLGAN](https://github.com/JunlinHan/DCLGAN). We also thanks [pixplot](https://github.com/YaleDHLab/pix-plot) for t\-SNE visualization.   
