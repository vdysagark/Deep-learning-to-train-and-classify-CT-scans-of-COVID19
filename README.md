# Deep-learning-to-train-and-classify-CT-scans-of-COVID19


Introduction

On March 11, 2020, the World Health Organization (WHO) declared the novel coronavirus (also referred to as COVID-19), a pandemic. As we all are well aware that COVID-19 is an infectious disease that has caused and is continuing to cause numerous deaths all over the world infecting millions of people. The ultimate solution to put an end to the pandemic is to find an effective vaccine. Scientific community around the world is racing to find a vaccine and meanwhile, many measures are being taken by countries to contain this pandemic. To contain the pandemic, one of the important steps to be taken is to test the infected patients. 


COVID-19 causes severe respiratory symptoms and is associated with relatively high ICU admission and mortality. Testing COVID-19 involves analyzing samples that indicate the present or past presence of severe acute respiratory syndrome-associated coronavirus 2 (SARS-CoV-2). The test is done to detect either the presence of the virus or of antibodies produced in response to infection. COVID-19 diagnostic approach is mainly divided into two broad categories, a laboratory-based approach, which includes point of care-testing, nucleic acid testing, antigens tests, and serology (antibody) tests. The other approach is using medical imaging diagnostic tools such as X-ray and computed tomography (CT). CT scan involves transmitting X-rays through the patient’s chest, which are then detected by radiation detectors and reconstructed into high-resolution medical images. There are certain patterns to look out for in a chest CT scans which present themselves in different characteristic manifestations. (Ilker Ozsahin, 2020). 


Right now, the gold standard of testing COVID-19 in infected patients is a nucleic acid testing called - RT-PCR (Reverse Transcription – Polymerase Chain Reaction). However, due to some underlying technicalities, the test is not always reliable and is shown to have sensitivity between 60-71%  (H. Bai, 2020). Also, during the peak of the pandemic, there was shortage of test kits and healthcare providers had to look for alternative methods for confirming the disease in an infected patient. Among the alternative methods, CT scans have been successfully used for screening and diagnosing COVID-19. Very recently, these CT scans have been open sourced to seek help from general public from various scientific backgrounds. Various studies reported that sensitivity for CT scans is about 98% while for RT-PCR, it is about 71% (Yicheng Fang, 2020). 

The three main distinctive features of COVID-19 CT scans observed are – 

1.	Ground-glass appearance - Opacities in the lung look like ground-glass
2.	Striking peripheral distribution along with the pleura – Implies that the majority of these opacities occur along the edge of the lung
3.	More than one independent focus of infections for one case – Implies that there can be more than one such cluster of opacities 

Now, what does artificial learning have to do with all this?  Machine learning has proven to be useful in medical applications since its inception, and it became widely accepted due to its high prediction and accuracy rates. In the diagnosis stage of COVID-19, machine learning algorithms can be used to recognize patterns on medical images taken by CT. Machine learning algorithms can be used to segment regions of interest and capture fine structures in chest CT images, self-learned features can easily be extracted for diagnosis and other applications. A recent study showed that machine learning models can accurately detect COVID-19 in CT images and was also able to differentiate it from other lung diseases and community-acquired pneumonia (Ilker Ozsahin, 2020). Deep learning technologies, such as convolutional neural network (CNN) with the strong ability of nonlinear modeling, have extensive applications in medical image processing. For this study, I will be using transfer learning to build a model that will classify COVID-19 and non-COVID-19 images. 

Data sources

The CT scan images are obtained from Github page provided by University of California, San Diego (Zhao, 2020). According to the Github page, the images are collected from COVID19-related papers from medRxiv, bioRxiv, NEJM, JAMA, Lancet, etc. CTs containing COVID-19 abnormalities are selected by reading the figure captions in the papers. All copyrights of the data belong to the authors and publishers of these papers.
Here is the link to the UCSD Github page: https://github.com/UCSD-AI4H/COVID-CT


Problem statement

The objective of this project is to apply computer vision-based deep learning algorithms as a tool to help diagnose COVID-19 by using CT scan of a patient. This project is focused on testing a model that can classify the CT scan images of COVID-19 and non-COVID-19 with greater accuracy.

Approach


For this project, I will be using Python program, Jupyter notebook and PyTorch to build the classifier. First step is to understand the images. After the images are loaded, they have to be preprocessed to evaluate the model. Performance metrics such as sensitivity, specificity and area under ROC are calculated. 
It is challenging to train a new deep learning model targeting COVID19 medical images, due to insufficient amounts of sample data available publicly. In this scenario, the best alternative is to apply transfer learning where a deep learning network is pre weighted with the results of a previous training cycle from a different domain. For this study, I would like to use the pretrained VGG-19 with batch normalization. Next step is to train the hyperparameters. Once the model is run, the model with best validation accuracy will be chosen to compute performance metrics. Finally, I intend to use another pretrained model (VGG-16) which has fewer layers of architecture compared to VGG-19 to observe if we can achieve better or diminished accuracy. 

