<h2>TensorFlow-FlexUNet-Image-Segmentation-Lung-Cancer-MRI (2026/11/02)</h2>
<h3>Lung-Cancer-MRI: AI Generated Pseudo Masks Segmentation Challenge</h3>
Sarah T. Arai<br>
Software Laboratory antillia.com<br><br>
This is the first experiment of Image Segmentation for <b>Lung-Cancer-MRI </b>
 based on
our <a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">TensorFlowFlexUNet Model</a>
 (<b>TensorFlow Flexible UNet Image Segmentation Model for Multiclass</b>) and a 512x512-pixel PNG
 <a href="https://drive.google.com/file/d/10UIC5Lg6zN5iR8iidYIbjHY5u4MlG1GL/view?usp=sharing">
Lung-Cancer-MRI-ImageMask-Dataset.zip</a> 
which was derived by us from the Kaggle  
<br><br>
<a href="https://www.kaggle.com/datasets/ajithdari/lung-cancer-genomic-and-clinical-dataset">
<b>Lung Cancer Genomic & Clinical Dataset</b>
</a> <br>
<b>Lung cancer MRI images with deterministic patient-level clinical features</b><br>
by Mukesh Dilip.
<br><br>
<hr>
<b>Actual Image Segmentation for Lung-Cancer-MRI Images of 512x512 pixels</b><br>
As shown below, the inferred masks resemble the ground-truth masks. <br>
<br>
<table>
<tr>
<th width="320" height="auto">Input: image</th>
<th width="320" height="auto">Mask (ground_truth)</th>
<th width="320" height="auto">Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/hflipped_Lung_MRI_10010.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/hflipped_Lung_MRI_10010.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/hflipped_Lung_MRI_10010.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/hflipped_Lung_MRI_10966.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/hflipped_Lung_MRI_10966.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/hflipped_Lung_MRI_10966.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/hflipped_Lung_MRI_10647.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/hflipped_Lung_MRI_10647.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/hflipped_Lung_MRI_10647.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>1. Dataset Citation</h3>
The dataset used here was derived from the following Kaggle:<br><br>
<a href="https://www.kaggle.com/datasets/ajithdari/lung-cancer-genomic-and-clinical-dataset">
<b>Lung Cancer Genomic & Clinical Dataset</b>
</a> <br>
<b>Lung cancer MRI images with deterministic patient-level clinical features</b><br>
by Mukesh Dilip.
<br><br>
The following explanation was taken the website above.
<br><br>
<b>About Dataset</b><br>
This dataset provides lung cancer MRI images along with associated clinical and 
genomic features for all patients. Each patient entry includes:
<br><br>
<b>Clinical Features:</b><br>
Histological type (Adenocarcinoma, Squamous cell carcinoma, Large cell carcinoma, Small cell lung carcinoma)
<br><br>
Tumor grade (G1–G4)
<br><br>
Tumor tissue site, laterality, and tumor location
<br><br>
Patient demographics: age at initial pathology, gender, race, ethnicity
<br><br>
Mortality status (death01)
<br><br>
Gene Cluster Annotations:
<br><br>
TP53Cluster (TP53_1 to TP53_5)
<br><br>
EGFRCluster (EGFR_1 to EGFR_5)
<br><br>
CDKN2ACluster (CDKN2A_1α, CDKN2A_1β, CDKN2A_2)
<br>
KRAS G12C Cluster (KRAS G12C_2, KRAS G12C_3)
<br><br>
EML4-ALKCluster (EML4-ALK_1, EML4-ALK_3a, EML4-ALK_3b, EML4-ALK_2, EML4-ALK_5)
<br>
<br>
<b>License</b><br>
Unknown
<br>
<br>
<h3>
2. Lung-Cancer-MRI ImageMask Dataset
</h3>
<h3>2.1 Download ImageMask Dataset</h3>
 If you would like to train this Lung-Cancer-MRI Segmentation model,
 please download the dataset from Google Drive  
 <a href="https://drive.google.com/file/d/10UIC5Lg6zN5iR8iidYIbjHY5u4MlG1GL/view?usp=sharing">
Lung-Cancer-MRI-ImageMask-Dataset.zip</a>. 
Expand the downloaded ImageMaskDataset and put it under the <b>./dataset</b> folder.
<br>
<pre>
./dataset
└─Lung-Cancer-MRI
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
         ├─images
         └─masks
</pre>
<br>
<b>Lung-Cancer-MRI Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/Lung-Cancer-MRI_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images in the training and valid datasets is large enough to use for the
 training set of our segmentation model.
<br>
<h3>2.2 Derivation of ImageMask Dataset</h3>
The folder structure of the original dataset is as follows, but it contains no
annotation (mask) files.
<pre>
./lung_cancer_MRI_dataset
   └─train
       └─cancer (1,122 files)
         ├─LNG001.png
...
         └─LNG1122.png
</pre>
<b>Step 1</b><br>
We generated a 512x512-pixel PNG master images from the image files in <b>cancer</b> folder.
<br><br>
<b>Step 2</b><br>
We generated pseudo masks corresponding to the master images
by applying a segmentation (inference) method of the pretrained model 
<a href="TensorFlow-FlexUNet-Image-Segmentation-Lung-Cancer-CT">
TensorFlow-FlexUNet-Image-Segmentation-Lung-Cancer-CT
</a> to the master images.
<br><br>
<b>Step 3</b><br>
We generated an augmented ImageMask dataset from the pseudo masks and the master images 
by applying flipping augmentation tools to all pairs of the images and masks.
<br><br>
<b>Step 4</b><br>
We generated a new pretrained FlexUNet segmentation model by using the augmented ImageMask 
dataset derived at Step 3.
<br><br>
<b>Step 5</b><br>
We generated a new pseudo masks corresponding to the master images by applying a segmentation method of the new 
pretrained FlexUNet model obtained at Step 4.
<br><br>
We iteratively repeated Steps 3 to 5 two times to generate our curated Lung-Cancer-MRI-ImageMask-Dataset.
<br><br>
<h3>2.3 Train Sample Images and Masks</h3>
<b>Train_sample_images</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_sample_masks</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/train_masks_sample.png" width="1024" height="auto">
<br>
<h3>
3. Train TensorFlowFlexUNet Model
</h3>
 We trained the Lung-Cancer-MRI TensorFlowFlexUNet model using the following
<a href="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorFlowFlexUNet/Lung-Cancer-MRI and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
This runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>
<b>Model parameters</b><br>
Defined a small <b>base_filters=16 </b> and large <b>base_kernels=(11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large <b>num_layers=8</b> (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
; You may specify your own UNet class derived from our TensorFlowFlexModel
model         = "TensorFlowFlexUNet"
generator     =  False
image_width    = 512
image_height   = 512
image_channels = 3
num_classes    = 2
base_filters   = 16
base_kernels   = (11,11)
num_layers     = 8
dropout_rate   = 0.03
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_focal_dice_loss" and <a href="./src/dice_coef_multiclass.py">"dice_coef_hybrid"</a>.<br>
<pre>
[model]
loss           = "categorical_focal_dice_loss"
metrics        = ["dice_coef_hybrid"]
hybrid_alpha   = 1.6
hybrid_beta    = 0.4
</pre>
<b>Dataset class</b><br>
Specifed <a href="./src/ImageCategorizedMaskDataset.py">ImageCategorizedMaskDataset</a> class.<br>
<pre>
[dataset]
class_name    = "ImageCategorizedMaskDataset"
</pre>
<br>
<b>Learning rate reducer callback</b><br>
Enabled the learning_rate_reducer callback and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.4
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with the patience parameter.
<pre>
[train]
patience      = 10
</pre>
<b>RGB Color map</b><br>
Specified RGB color map dict for Lung-Cancer-MRI 2 classes.<br>
<pre>
[mask]
mask_datatype= "categorized"
mask_file_format = ".png"
; Lung-Cancer-MRI RGB color map dict for 1+1 classes.
;      Background: black,  Cancer:dark_red
rgb_map = {(0,0,0):0,(210,20,20):1,}
</pre>

<b>Epoch change inference callback</b><br>
Enabled <a href="./src/EpochChangeInferencer.py">epoch_change_infer callback</a></b>.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
num_infer_images         = 6
</pre>

By using this callback, on every epoch change, the inference procedure can be called
 for 6 images in the <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> 
<br> 

As shown below, early in the model training, the predicted masks from our FlexUNet segmentation model showed 
discouraging results.
 However, as training progressed through the epochs, the predictions gradually improved. 
 <br> 
<br>

<b>Epoch_change_inference output at starting (epoch 1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at middlepoint (epoch 17,18,19)</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/epoch_change_infer_at_middle.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (epoch 35,36,37)</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>
<br>
In this experiment, the training process was stopped at epoch 37 by EarlyStoppingCallback.<br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/train_console_output_at_epoch37.png" width="1024" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/eval/train_metrics.png" width="520" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4. Evaluation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/Lung-Cancer-MRI</b> folder,
and run the following bat file to evaluate the TensorFlowUNet model for Lung-Cancer-MRI.<br>
<pre>
>./2.evaluate.bat
</pre>
This runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetEvaluator.py ./train_eval_infer.config
</pre>

Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/evaluate_console_output_at_epoch37.png" width="1024" height="auto">
<br><br>Image-Segmentation-Lung-Cancer-MRI

<a href="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_focal_dice_loss) on this Lung-Cancer-MRI/test was very low, 
and dice_coef_hybrid was high, as shown below.
<br>
<pre>
categorical_focal_dice_loss,0.0025
dice_coef_hybrid,0.9257
</pre>
<br>
<h3>
5. Inference
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/Lung-Cancer-MRI</b> folder
and run the following bat file to infer segmentation regions for images using the trained TensorFlowUNet model for Lung-Cancer-MRI.<br>
<pre>
>./3.infer.bat
</pre>
This runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/mini_test_masks.png" width="1024" height="auto"><br>

<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks for Lung-Cancer-MRI Images of 512x512 pixels</b><br>
As shown below, the inferred masks look similar to the ground truth masks.<br>
<br>
<table>
<tr>
<th width="320" height="auto">Image</th>
<th width="320" height="auto">Mask (ground_truth)</th>
<th width="320" height="auto">Inferred-mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/hflipped_Lung_MRI_10054.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/hflipped_Lung_MRI_10054.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/hflipped_Lung_MRI_10054.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/hflipped_Lung_MRI_10647.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/hflipped_Lung_MRI_10647.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/hflipped_Lung_MRI_10647.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/Lung_MRI_10195.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/Lung_MRI_10195.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/Lung_MRI_10195.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/Lung_MRI_10949.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/Lung_MRI_10949.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/Lung_MRI_10949.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/Lung_MRI_11031.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/Lung_MRI_11031.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/Lung_MRI_11031.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/images/vflipped_Lung_MRI_10953.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test/masks/vflipped_Lung_MRI_10953.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Lung-Cancer-MRI/mini_test_output/vflipped_Lung_MRI_10953.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>
References
</h3>
<b>1. Lung cancer segmentation dataset with Lung-RADS class</b><br>
Nam, Diana; Panina, Alexandra; Pak, Alexandr <br>
(2024),  Mendeley Data, V1, doi: 10.17632/5rr22hgzwr.1 <br>
<a href ="https://data.mendeley.com/datasets/5rr22hgzwr/1">
  https://data.mendeley.com/datasets/5rr22hgzwr/1
</a>
<br><br>
<b>2. Lung Tumor Image Segmentation from Computer Tomography Images Using MobileNetV2 and Transfer Learning</b><br>
Zainab Riaz, Bangul Khan, Saad Abdullah, Samiullah Khan, Md Shohidul Islam<br>
<a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC10451633/" >
  https://pmc.ncbi.nlm.nih.gov/articles/PMC10451633/
</a>
<br><br>
<b>3. NLSTseg: A Pixel-level Lung Cancer Dataset Based on NLST LDCT Images</b><br>
Kun-Hui Chen, Yi-Hui Lin, Shawn Wu, Nai-Wen Shih, Hsing-Chen Meng, Yen-Yu Lin, Chun-Rong Huang & Jing-Wen Huang <br>
<a href ="https://www.nature.com/articles/s41597-025-05742-x">
https://www.nature.com/articles/s41597-025-05742-x
</a>
<br><br>
<b>4. TensorFlow-FlexUNet-Image-Segmentation-Smokers-Lung-Cancer-CT</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Smokers-Lung-Cancer-CT">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Smokers-Lung-Cancer-CT
</a>
<br><br>
<b>5. TensorFlow-FlexUNet-Image-Segmentation-Lung-Cancer-CT</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Lung-Cancer-CT">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Lung-Cancer-CT
</a>
<br><br>
<b>6. TensorFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
<br><br>
