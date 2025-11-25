---
title:  "[Computer Vision] 카메라의 2D 이미지를 3D 위치로 바꿔보자."
excerpt: ""
categories:
  - AI
tags:
  - [Python, Computer Vision, Depth Estimation, Camera Calibration]

toc: true
toc_label: "List"
toc_icon: "bars"
toc_sticky: true
 
date: 2024-07-25
last_modified_at: 2024-07-25
---

<br>

# <span style="color:rgb(0, 180, 180)">카메라 화면을 3D 위치로 재구성.</span>
<span style="font-size: large"></span>

## ✒️ 소개글
이 글은 제가 한 실습 내용을 다룹니다.  
인생 처음으로 논문을 봤고, 수 많은 영어로 머리가 어지러웠지만..  
최대한 잘 읽히게 쓸게요.

이 분야가 로봇/자동차 등에 시각적 센서를 이용하는 일이 많아서  
궁금하시면 읽어보세요!

## 참고자료
test..  
📌 [ 문서 ](https://loplio.github.io) 📌

<br>

# 2D 화면을 3D 공간으로.
우선 2D 화면을 3D 공간으로 바꾸는 과정에 필요한 것은  
<u>어떤 조건</u>인지 파악해야합니다.  
즉, 카메라가 어떤 정보를 갖고 있는 지 확인해야합니다.    

## 측정 센서의 유무
우선 첫 번째, 카메라마다 **성능**과 **기능**이 다릅니다.  
측정 센서는 **이미지의 Depth**를 구하는 데, 큰 도움을 줍니다.  
<span style="color:rgb(150, 150, 150);">카메라는 주로 휴대폰, 전문 카메라, CCTV 등 다양한 곳에 이용됩니다.</span>

\<휴대폰\>  
- <u>LiDAR/ToF</u>와 같은 거리를 **측정**하거나 물체를 **탐지**하는 기술이 적용된 장치가 들어 있습니다.  

\<CCTV\>  
- 반대로 대부분의 CCTV는 측정 센서가 **없습**니다.

<br>

🪄 제 조건은 `측정 장비 없는 CCTV`였습니다.

## 카메라 캘리브레이션
카메라는 <u>초점거리, 왜곡, 변환(이동, 회전) 등</u>에 대한 정보가 있습니다.  
이 정보들을 알아야 이 분야를 깊이 연구 하신 분들의 기술들을 적용하고 3D위치를 추려낼 수 있습니다.  

카메라의 중요 정보들을 알아내는 과정입니다.

이 과정에서 사용되는 대표 기술로 zhang's "A Flexible New Technique for Camera Calibration"라는 논문이 유명합니다. 



# 참고 논문.
## 논문1. Zhang's "A Flexible New Technique for Camera Calibration"
해당 논문은 
정밀한 기하학적 구조를 통해 전문 장비를 이용한 효율적이고 정밀한 방식의 시각측량학적 캘리브레이션(Photogrammetric Calibration)과  
단일 카메라로 정적 장면의 여러 이미지를 촬영한 방식으로 유연하지만 신뢰성을 보장할 수 없는 캘리브레이션(Self-Calibration)의  
중간단계의 접근법으로 저렴하고 유연한 DVS(Dynamic Vision Sensor)을 위한 기술이며,  
앞선 두 방식에 대중성과 신뢰성을 갖춘 카메라 캘리브레이션 방식이다.

카메라의 단일 평면을 관찰하여 제공되는 카메라의 고유 매개변수의 대한 제약을 조사합니다.  
이는 2D 점의 요소 1을 추가합니다.  
m = [u, v, 1]^T^  
3D 점의 요소  

<span style="font-size: x-large; color:rgb(169, 190, 213);">**⭐ test! ⭐**</span>
<!-- 핵심 멘트 이모지 -->
<!-- 파스텔 컬러
밝은 하늘색 - color:rgb(169, 190, 213) / 
하늘색 - color:rgb(144, 153, 175)-->

🪄 test!
<!-- 마무리 멘트 이모지 -->

<div class="notice" style="padding: 0.5em; text-align: center; font-weight: bold;">
  <span style="font-size: small;">🌠 test. </span>
</div>
<!--  기본 멘트 이모지 -->

<div class="notice--info" style="font-weight: normal;">
  <span style="font-size: medium;">✨개인 공부 글입니다! 언제든지 질문/지적 해주세요!✨</span>
</div>

<!-- 이모지 ☀️☁️☂️☃️⭐🌙🌠🔥💧✨🗨️🎁🎄🎲🪄✔️🕶️🔔📢🎧🎵💡📜📄📌✒️📁 -->