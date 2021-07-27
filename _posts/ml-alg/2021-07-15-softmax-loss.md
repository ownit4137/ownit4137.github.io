---
layout: post
title: Softmax Loss
categories: [ML-alg]

hide_last_modified: true
# image: {link}
# related_posts:
#   - /_posts/blog/2021-01-01-writing-01-markdown.md
# accent_image: 
#   background: url('{link}') center/cover
#   overlay: false
# accent_color: '#ccc'  # text underline
# theme_color: '#ccc'   # entire theme

# invert_sidebar: true  # invert sidebar text color b/w
---

# Softmax Loss

Posts about Metric Learning and Softmax Loss

## Metric learning

- practitioners would choose a standard distance metric using a priori knowledge of the domain
- it is difficult to design metrics that are well-suited to the particular data
- Metric learning aims at **automatically constructing task-specific distance metrics** from supervised data
- similar objects get close and dissimilar objects get far away

## Softmax loss

- Various loss functions have been developed for Metric Learning
- Softmax compresses a set of vectors so that the sum of the elements of the vector is 1

$$
L =  \frac{1}{N}  \sum_i -\log \big( \cfrac{e^{W^Tx+b}}{\sum e^{W^Tx+b}} \big) 
$$

A formal expression for the softmax loss
{:.figcaption}

![softmax](https://miro.medium.com/max/424/1*lffJvF1VmeRE4LiD9xIRTw.png){:style='width:40%; margin:0% 30%;' loading='lazy'}

https://towardsdatascience.com/additive-margin-softmax-loss-am-softmax-912e11ce1c6b
{:.figcaption}

그림에서 $$x$$를 Class 1로 판별하기 위해서는

$$ 
\displaylines{
{W_1}^Tx > {W_2}^Tx
\\
\\
\parallel W_2 \parallel  \parallel x  \parallel  \cos \theta_1 \space > \space \parallel W_2 \parallel  \parallel x  \parallel  \cos \theta_2
\\
\\
(\parallel W \parallel = 1, \space  \parallel x  \parallel = s)
}$$

이므로 클래스 벡터 $$W$$와 feature $$x$$ 사이의 각도 $$\theta$$를 metric이라 할 수 있다.

학습 시에는 feature $$x$$의 정답 클래스 벡터 $$W_{correct}$$와의 각 $$\theta_{correct}$$가<br>
오답 클래스 벡터 $$W_{wrong}$$와의 각 $$\theta_{wrong}$$보다 작아져야 한다.

각을 사용한 metric으로 학습을 진행하면 다음과 같이 임베딩된다.

![softmax_loss](https://www.researchgate.net/profile/Rajeev-Ranjan-30/publication/315683968/figure/fig2/AS:477128018927617@1490767592498/Vizualization-of-2-dimensional-features-for-MNIST-digit-classification-test-set-using-a.png){:style='width:70%; margin:0% 15%;' loading='lazy'}


