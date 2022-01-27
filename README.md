# Unsupervised Image-to-Image Translation with Patch Pyramid Dual Contrastive Learning for Cross Domain Object Detection   

## Introdcution

This repository contains our PyTorch implementation of Unsupervised Image-to-Image Translation with Patch Pyramid Dual Contrastive Learning for Cross Domain Object Detection (PPDCLUIT). In this paper, we propose **P**atch **P**yramid **D**ual **C**ontrastive **L**earning **U**nsupervised **I**mage **T**ranslation (PPDCLUIT) framework to strength the cross domain object detection performance. Built upon the architecture of [CUT](https://github.com/taesungp/contrastive-unpaired-translation) and [DCLGAN](https://github.com/JunlinHan/DCLGAN), our method present a patch pyramid dual contrastive learning startegy for coherent associations at each specific location and include identity loss to further enforce the object instances preservation.  Trained on the images translated by our OA-FSUI2IT, object detection methods (i.e. Faster RCNN, FCOS) can achieve better mAP than those trained on source only, as well as those domain adaptation based methods. As the processing time for our detection framework is determined by the inference time of the employed detector, it can be used for online object detection. 


<img src='./imgs/Overview.png' align="right" width=960>    


<br><br>
### **Patch Pyramid Dual Contrastive Learning Unsupervised Image Translation Network**    

<img src='./imgs/Networks.png' align="right" width=960>   


## Translation Results  

### Cityscapes Clear to Foggy  
Qualitative results:  

<img src='./imgs/translation_results.png' align="right" width=960>    

#### Quantitative results:   

### Cityscapes Clear to Foggy  

## Detection Results  
Qualitative results:  

<img src='./imgs/detection_results.png' align="right" width=960>   



## t\-SNE Result  
To validate our translation method, we use TSNE to visualize distribution of images from source domain, target domain and generated.   


### Acknowledgments   
Our code is developed based on [contrastive-unpaired-translation](https://github.com/taesungp/contrastive-unpaired-translation/) and [DCLGAN](https://github.com/JunlinHan/DCLGAN). We also thanks [pixplot](https://github.com/YaleDHLab/pix-plot) for t\-SNE visualization.   
