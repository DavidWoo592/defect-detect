# Defect-Detect

Defect-Detect is a image visualization tool to identify and quantify defects in TEM images, utilizing image masks to expedite defect or ROI counting for microscopists.

This code is still in development, but was curated by Justin Lee (Johns Hopkins University, Department of Materials Science & Engineering) and is currently being developed by Emily Hopkins and Nicholas Gigliotti (Johns Hopkins University, Department of Materials Science & Engineering) for further applications.

**About:**

This work was done as part of a study analyzing He bubble size in irradiated nanocrystalline thin films of varying composition and grain size as a starting point for expedited identification and counting of defects.


The framework consists of two parts. First, the defect-train code utilizes previously trained masks in combination with raw image files to load a machine learning model with scikit-learn, which is then saved in pickle format. Second, the defect-detect code calls on the trained defect-train model, and applies the same filters and learned qualities to raw microscopy image files. An example of the masks, raw image files, and results are shown below.


Future work will seek to expand classification from binary to multi-class defects and reduce memory capacity to allow for ease in running.


![image](https://user-images.githubusercontent.com/87487374/158637189-a21a72b1-3609-485a-baef-8fee987cbdbb.png)

![image](https://user-images.githubusercontent.com/87487374/158637392-0f48d556-42a2-4447-a35f-f5cffc4a1858.png)


**Descriptions:**

 - defect-train
    - Notebook to train your own ML model on defects you are interested in.
    - Uses 20% of masked data as an accuracy test, trains with 80% of mask data.
    - Image type is not important: .jpg, .png, .tiff, etc. are acceptable formats.
 - defect-detect
    - Notebook which calls on defect-train to identify defects in similar image types.
    - Exports mask files, and csv including total defect count and area per each defect.

**Usage Requirements**

- Requires the open source Python libraries: numpy, pandas, cv2, pickle, and matplotlib
- Python 3.9.7
