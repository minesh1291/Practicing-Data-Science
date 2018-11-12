---
layout: post
title:  "Google Colab Beginner"
date:   2018-11-12
banner_image : google-colab.png
tags: [R, Python, Data Science, Jobs, Machine Learning]
---

# Google Colab Beginner
---

We can open Colab here : https://colab.research.google.com/

After opening the first thing we want to do will be **importing data**:

Data from Google Drive to Colab:
- Mounting Google Drive :
```sh
from google.colab import drive
drive.mount('/gdrive')
```

Data / Code from Git repositories to Colab:
```sh
!git clone [git-repo-url]
```

Data from Kaggle to Colab:
```sh
!pip install kaggle
!kaggle competitions download [competition-name]
```
for more : https://github.com/Kaggle/kaggle-api

Data from Internet / Web to Colab:
```sh
!wget [web-url]
```

Data from local computer:
```sh
from google.colab import files
uploaded = files.upload()
```
