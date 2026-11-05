# Korean ASR Model Comparison
## 1. Project Overview

한국어 음성인식 모델인 Whisper와 Conformer의 성능을 다양한 음성 조건에서 비교한 프로젝트 입니다.

발화 속도, 억양, 배경 잡음 등 음성 조건에 따라 모델의 인식 정확도가 어떻게 달라지는지 분석하고 모델별 오류 유형을 비교했습니다.

## 2. Models

- Whisper Large-v3-turbo
- Korean Conformer CTC (SungBeom/stt_kr_conformer_ctc_medium)

## 3. Experiment

직접 녹음한 한국어 음성을 활용하여 다음 조건에서 실험했습니다.

Normal : 일반적인 발화
Accent : 억양 변화-경상도 억양
Noise : 배경 잡음
Slow/Fast : 발화 속도 변화

모델의 인식 결과를 실제 정답 문장과 비교하고 WER, CER 및 Alignment를 활용하여 오류를 분석했습니다.

## 4. Key results

- Normal 조건에서 Whisper의 WER은 3.89%, Conformer는 8.40%로 나타났습니다.
- Noise 조건에서 두 모델 모두 인식 오류가 증가했습니다.
- Fast 조건에서 Whisper의 WER은 6.23%, Conformer는 12.17%로 나타났습니다.
- Conformer는 Slow 조건에서 WER 기준으로 근소하게 우세했지만 CER에서는 Whisper가 낮은 오류율을 보였습니다.

## 5. Conclusion

실험 결과 Whisper는 발화 속도 변화에 대해 상대적으로 안정적인 인식 성능을 보였습니다. 반면 Conformer는 빠른 발화에서 오류율이 크게 증가했습니다.

이를 통해 ASR 모델의 성능은 모델 자체 뿐 아니라 입력 음성의 조건에 따라서도 달라질 수 있음을 확인하였습니다.

## 6. Tech Stack

Python, Google Colab, PyTorch, Whisper, NVIDIA NeMo, Pandas, JiWER, Matplotlib

## 7. Code

실험 코드 : Project_ASR.ipynb
음성 데이터는 직접 녹음했으며 실행 시 음성 파일과 정답 텍스트 

