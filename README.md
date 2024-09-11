[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHsKfIy0)
# Title (Please modify the title)
## Team



| ![현재호](https://avatars.githubusercontent.com/u/156163982?v=4) | ![최제우](https://avatars.githubusercontent.com/u/156163982?v=4) |
| :--------------------------------------------------------------: | :--------------------------------------------------------------: |
|            [현재호](https://github.com/dochyun123)             |            [최제우](https://github.com/UpstageAILab)             |
|                            모델링 및 데이터 분석 전반                             |                            모델링 및 데이터 분석 전반                             |

## 0. Overview
### Environment
- 컴퓨팅 환경 : RTX3090 서버를 VSC와 SSH를 통해 사용
- 협업 환경 : Github, Wandb
- 회의 환경 : Slack, Zoom

## 1. Competiton Info

### Overview

Dialogue Summarization 경진대회는 주어진 데이터를 활용하여 일상 대화에 대한 요약을 효과적으로 생성하는 모델을 개발하는 대회입니다. 

일상생활에서 대화는 항상 이루어지고 있습니다. 회의나 토의는 물론이고, 사소한 일상 대화 중에도 서로 다양한 주제와 입장들을 주고 받습니다. 나누는 대화를 녹음해두더라도 대화 전체를 항상 다시 들을 수는 없기 때문에 요약이 필요하고, 이를 위한 통화 비서와 같은 서비스들도 등장하고 있습니다.

그러나 하나의 대화에서도 관점, 주제별로 정리하면 수 많은 요약을 만들 수 있습니다. 대화를 하는 도중에 이를 요약하게 되면 대화에 집중할 수 없으며, 대화 이후에 기억에 의존해 요약하게 되면 오해나 누락이 추가되어 주관이 많이 개입되게 됩니다.

이를 돕기 위해, 우리는 이번 대회에서 일상 대화를 바탕으로 요약문을 생성하는 모델을 구축합니다!
### Timeline

- August 29, 2024 - Start Date
- September 10, 2024 - Final submission deadline

## 2. Components

### Directory


```
├── README.md
├── jaeho
│   │   ├── 파일명1
│   │   ├── 파일명2
│   │   └── 파일명3
│   ├── data
│   │   ├── data1
│   │   └── data2
├── jewoo
│   ├── code
│   │   ├── 파일명1
│   │   ├── 파일명2
│   │   └── 파일명3
│   ├── data
│   │   ├── data1
│   │   └── data2
│   ├── pdf
        └── (Template) [패스트캠퍼스] Upstage AI Lab 1기_그룹 스터디 .pptx
```

## 3. Data descrption

### Dataset overview

- 해당 대회의 데이터는 모두 해화문 데이터이며 train data, vaidation data, test data는 각각 12,457개, 499개, 499개로 이루어져 있습니다.
- 대화(dialogue)를 통해 요약(summary)를 예측하는것이 최종 목표입니다.
- 최소 2명에서 최대 7명의 담화자가 등장하며

### EDA

- _Describe your EDA process and step-by-step conclusion_

### Data Processing

- 다양한 모델의 구조에 맞추어 input, output데이터를 수정
- 일부 과정에서 데이터의 오타등의 수정을 위해 한글 > 영어 > 한글로 back translate 실행

## 4. Modeling

### 현제호

- _Write model information and why your select this model_

### 최제우

- Bart
  - pretrained 모델
    - digit82/kobart-summarization
    - 기존의 데이터에 google번역기를 통해 한>영>한으로 번역체로 바꾸어 학습
  - 결과
    - vaild loss : 0.750846
    - 리더보드 : 제출 실패
- Gpt2
  - pretrained 모델
    - digit82/kogpt2-summarization
    - skt/kogpt2-base-v2
  - 결과
    - vaild loss : 2.58616 ~ 2.88616
    - 리더보드 : 13.3814 ~ 15.6050
- T5
  - pretrained 모델
    - eenzeenee/t5-base-korean-summarization
    - eenzeenee/t5-small-korean-summarization
    - digit82/kolang-t5-base
  - 결과
    - vaild loss : 0.73032 ~ 1.7084
    - 리더보드 : 19.5923 ~ 20.8458

## 5. Result

### Leader Board

- 최종 등수 : 10등
- 최종 점수 : 39.5166
  
![image](https://github.com/user-attachments/assets/247029f8-9f4b-4916-82b6-592022381855)
