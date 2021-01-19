---
title: Matrix Completion for Recommendation System Based on Federated Learning
summary:  .
tags:
- Deep Learning
date: "2020-12-15T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

#links:
#- icon: twitter
 # icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
# url_code: ""
# url_pdf: ""
# url_slides: ""
# url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

In this project, an algorithm would be designed to solve the Matrix Complication problems based on Federated Learning. For general Matrix Complication problems, the main idea is to deconstruct a huge sparse matrix M^(m×n) to subsets X^(m×r),Y^(r×n), and then let  M ̂=X^(m×r)×Y^(r×n) to be a complication matrix. In Federated Learning structure, the model would be divided into two parts, one stores in the Server and the other stores in the Clients. The two parts could not transfer data directly, which could enhance the data security for users. In the Federated Matrix Complication problem, the matrix M^(m×n) would be stored in m Clients’ device, each client holds an n-length vector. During the training process, there would be two steps for each iteration. 

Step1: Local Training. In this process, the Server would broadcast the gradient to each client, and the clients update their model at the local device.
Step2: Server Training. The server collects the gradients from clients, does some change (e.g., take the average), and then uses it to update its model.

The challenge for this project is to enhance the accuracy and robustness of each user’s result. The normal Matrix Complication model could be trained well because of the correlation among different users. But for Federated Learning, this advantage may disappear. Another challenge is to ensure the security of user’s data. And in this project’s setting, our target is to guarantee that server could not know directly or deduce the raw scoring data from user’s uploading gradients.

In this project, we designed a distributed algorithm for the Recommendation System based on a Federated Learning setting called the Fed_MF algorithm, using the Random Gradient Merge method to guarantee the security of raw data. And the results showed that the accuracy of Fed_MF is close to original algorithms, with only 1.23% accuracy loss. Thus, the Fed_MF algorithm is an acceptable and efficient method to solve Recommendation System problems.
