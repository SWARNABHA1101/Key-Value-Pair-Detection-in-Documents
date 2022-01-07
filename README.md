# Key-Value-Pair-Detection-in-Documents
Optical Character Recognition(OCR) and information extraction

### Dataset and Annotations

The original dataset has a few mistakes. This has been corrected by `scripts/check_data.py` and you can just use the `data` folder in this repo.


The dataset has 1000 whole scanned receipt images. Each receipt image contains around about four key text fields, such as goods name, unit price and total cost, etc. The text annotated in the dataset mainly consists of digits and English characters. An example scanned receipt is shown below:

<div align=center><img src="./Media/data_sample.jpg" width="300"/></div>

The dataset is split into a training/validation set (“trainval”) and a test set (“test”). The “trainval” set consists of 600 receipt images, the “test” set consists of 400 images.

For receipt OCR task, each image in the dataset is annotated with text bounding boxes (bbox) and the transcript of each text bbox. Locations are annotated as rectangles with four vertices, which are in clockwise order starting from the top. Annotations for an image are stored in a text file with the same file name. The annotation format is similar to that of ICDAR2015 dataset, which is shown below:

```
x1_1,y1_1,x2_1,y2_1,x3_1,y3_1,x4_1,y4_1,transcript_1
x1_2,y1_2,x2_2,y2_2,x3_2,y3_2,x4_2,y4_2,transcript_2
x1_3,y1_3,x2_3,y2_3,x3_3,y3_3,x4_3,y4_3,transcript_3
…
```

For the information extraction task, each image in the dataset is annotated with a text file with format shown below:

```json
{
  "company": "STARBUCKS STORE #10208",
  "address": "11302 EUCLID AVENUE, CLEVELAND, OH (216) 229-0749",
  "date": "14/03/2015",
  "total": "4.95"
}
```
