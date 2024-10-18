# Introduction
Chest X-ray (CXR) is a common diagnostic method for chest issues, using a small amount of ionizing radiation to create internal images. It helps doctors identify and monitor lung diseases, but careful diagnosis requires expertise and time, which can lead to errors when many CXRs must be reviewed daily. Research suggests deep learning models can improve diagnostic accuracy. This study focuses on detecting key areas in CXRs for common lung diseases like tuberculosis, pneumonia, mass, and effusion. The results aim to develop automated tools to reduce errors and enhance diagnostic efficiency.<br>
<img width="600" alt="{18703521-2A33-4970-B888-81A45A3C8F2E}" src="https://github.com/user-attachments/assets/01355644-4d84-4648-a7c7-6486ad9fa8b5">

*Figure 1: Overview diagram of the research method.*
# Dataset
Source: Tuberculosis Chest Xray Cleaned Dataset, Tuberculosis classification, NIH Chest Xray dataset, CXR dataset, VinDr CXR Normal <br>
From: Kaggle <br>

| Condition      | Tuberculosis | Pneumonia | Mass | Effusion | Total |
|----------------|--------------|-----------|------|----------|-------|
| Cases          | 7089         | 2773      | 3076 | 1539     | 2898  |


<img width="600" alt="{D9C034BE-63DE-49F7-B8ED-E370158188EB}" src="https://github.com/user-attachments/assets/57210a9c-644e-4912-a02e-5272a0c3774e"><br>
*Figure 2: Distributions of the datasets used.*
# Research Method
- **Occlusion-based Method**: This method involves applying occlusion techniques to different regions of an X-ray image to assess the importance of these areas for disease classification and to observe their impact on the model's predictions. Figure 3 illustrates 9 occluded information regions on the X-ray for experimental purposes. Deep learning models InceptionV3, MobileNet, VGG16, and YOLOv8 are used to predict disease types.<br>
<img width="600" alt="{DEDD07E6-45D0-4406-B704-214BFF58B423}" src="https://github.com/user-attachments/assets/6861de3a-c060-4379-a2d0-10759ebee61c"> <br>
*Figure 3: 9 steps to jump to a glimpse on a chest X-ray image.*

- **RAM Attention Mechanism Model**: This model implements RAM attention mechanisms to predict important regions in X-ray images during classification. It evaluates the model's ability to improve accuracy and classification speed by focusing on critical information areas.

- **Deep Learning Classification Model**: Two of the highest-performing models from the experiments, YOLOv8 and DenseNet121, are trained to predict disease labels or "normal" using X-ray image data.

# Result
| Model                    | Accuracy  | Precision    | Recall     | F1-score   |
|--------------------------|-----------|--------------|------------|------------|
| YOLOv8 (516*516)        | **89.0934**  | **87.8825**    | **83.9925**  | **85.3262**  |
| Densenet201 (516*516)   | 79.3532   | 73.4156      | 72.2743    | 72.5185    |
| YOLOv8 (256*256)        | 80.8214   | 75.3052      | 73.4034    | 73.6246    |
| Densenet201 (256*256)   | 77.3263   | 73.8462      | 74.7169  | 73.9753    |
| RAM                      | 47.4672   | 37.4673      | 36.5757    | 36.4369    |

**Grad-CAM (Gradient-weighted Class Activation Mapping)** is a powerful visualization technique that helps understand and interpret the decision-making process of deep learning models, including YOLOv8. By applying Grad-CAM, we can identify specific areas in an image that the model focuses on to make predictions. YOLOv8 divides the image into four regions for analysis and prediction, with each area being crucial for identifying objects and features. Grad-CAM visualizes these focused regions, clarifying how the model processes information and makes decisions. This understanding aids in improving and fine-tuning the model for better performance. As illustrated in Figure 4,5,6, 7 and 8, Grad-CAM reveals the essential areas YOLOv8 uses in object analysis and recognition, providing insights into the workings of deep learning models and laying a solid foundation for future research and applications in image recognition and computer vision.<br>


<img width="472" alt="{9E3DD0AD-A996-4E6A-87D5-2E8B8E3A248C}" src="https://github.com/user-attachments/assets/d86f3343-459e-4698-b91e-6c4b44e472cb"> <br>
*Figure 4: Image analysis of Effusion disease from the YOLOv8 model using Grad-CAM.*
<img width="475" alt="{7C15B083-AF61-4A24-B7E4-BFBEAB07D9B9}" src="https://github.com/user-attachments/assets/16853ea4-608e-444a-9162-8767b3a8b074"> <br>
*Figure 5: Image analysis of Mass disease from the YOLOv8 model using Grad-CAM.*
<img width="479" alt="{4CF0E789-905D-4894-8F86-D7831644FEDE}" src="https://github.com/user-attachments/assets/b73d7c44-a1ef-4963-b66b-1d691f37e19a"> <br>
*Figure 6: Image analysis of Normal status from the YOLOv8 model using Grad-CAM.*
<img width="483" alt="{CB17B211-52FF-4C7B-8BB2-DAAE95C7C85A}" src="https://github.com/user-attachments/assets/60e232fc-213b-4444-a636-da173f3bc393"> <br>
*Figure 7: Image analysis of Pneumonia disease from the YOLOv8 model using Grad-CAM.*
<img width="481" alt="{C98BC4DC-E9D5-40AA-8F36-1C0F466A6965}" src="https://github.com/user-attachments/assets/698103f8-74af-4d54-9ede-9cf43ed20bb3"> <br>
*Figure 8: Image analysis of Tuberculosis disease from the YOLOv8 model using Grad-CAM.*












