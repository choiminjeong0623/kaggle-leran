# 데이터

데이터 파일은 용량과 라이선스 문제로 이 저장소에 올리지 않습니다. 노트북은 구글 드라이브를 마운트해서 데이터를 읽습니다.

## UCI SECOM (반도체 공정 센서 데이터)

| 파일 | 내용 |
|---|---|
| `secom.data` | 1,567행 × 590열 센서 측정값 (공백 구분, 결측치는 `NaN` 글자) |
| `secom_labels.data` | 행마다 `-1`(합격) / `1`(불합격) 라벨과 측정 시각 (`"19/07/2008 11:55:00"` 형식) |
| `secom.names` | 데이터 설명서 |

- 출처: [UCI Machine Learning Repository — SECOM](https://archive.ics.uci.edu/dataset/179/secom)
- 구글 드라이브 위치: `내 드라이브/kaggle-learn/secom/`
- 코랩 경로: `/content/drive/MyDrive/kaggle-learn/secom`

```python
from google.colab import drive
drive.mount('/content/drive')
DATA_DIR = '/content/drive/MyDrive/kaggle-learn/secom'
```

`pandas/pandas_01_secom.ipynb`를 끝까지 실행하면 같은 폴더에 정리된 데이터 `secom_clean.csv`(1,567행 × 449열, 결측치 없음)가 저장됩니다. 다음 복습(Data Cleaning, Intermediate ML)에서 이 파일을 이어서 사용합니다.
