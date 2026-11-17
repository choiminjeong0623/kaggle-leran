# Kaggle Learn 복습 노트

[Kaggle Learn](https://www.kaggle.com/learn) 데이터 분석 마이크로코스에서 배운 개념을, 강의 예제 대신 **반도체 공정 센서 데이터(UCI SECOM)** 에 적용해 다시 풀어 보는 복습 저장소입니다. 실습은 구글 코랩에서 하고, 노트북을 이 저장소에 기록합니다.

복습한 내용은 설비 센서 이상 감지 → 품질 부적합 대응 에이전트 프로젝트 [QualiGuard](https://github.com/choiminjeong0623/qualiguard-agent)의 데이터 처리에 이어서 활용합니다.

## 진행 현황

| 과정 | 수료 | 복습 노트북 | 상태 |
|---|---|---|---|
| Pandas | ✅ | [`pandas/pandas_01_secom.ipynb`](pandas/pandas_01_secom.ipynb) | 1차 복습 완료 (2026-11-17) |
| Data Cleaning | ✅ | `data-cleaning/` | 예정 |
| Intermediate Machine Learning | ✅ | `intermediate-ml/` | 예정 |

## 폴더 구조

```
kaggle-leran/
├── README.md
├── data/
│   └── README.md          # 데이터 받는 방법 (데이터 파일 자체는 올리지 않음)
├── pandas/
│   └── pandas_01_secom.ipynb
├── data-cleaning/
└── intermediate-ml/
```

## Pandas 복습 — `pandas_01_secom.ipynb`

Kaggle Pandas 과정 6개 레슨의 개념을 SECOM 데이터 처리 흐름에 맞춰 사용했습니다.

| 레슨 | 사용한 개념 | 노트북 위치 |
|---|---|---|
| L1 Creating, Reading and Writing | `read_csv`(sep, header), `shape`, `head`, `to_csv` | 1장, 9장 |
| L2 Indexing, Selecting & Assigning | `iloc`, `loc`, 조건 선택(`&`), 새 열 대입 | 2장, 5장 |
| L3 Summary Functions and Maps | `describe`, `value_counts`, `map`, `apply`, `nunique` | 6장 |
| L4 Grouping and Sorting | `groupby`, `agg`, `size`, `sort_values` | 7장 |
| L5 Data Types and Missing Values | `dtypes`, `astype`, `to_datetime`, `isnull`, `fillna` | 4장, 8장 |
| L6 Renaming and Combining | `rename`, `pd.concat(axis=1)` | 2장, 3장 |

**주요 결과**
- 불합격 104건(6.6%)뿐인 불균형 데이터 → 정확도보다 재현율 등으로 평가해야 함
- 합격/불합격 평균 차이가 큰 센서 후보 6개: 059, 103, 510, 348, 431, 434 (단, 센서 하나로는 구분이 안 됨)
- 불량이 2008년 7~8월에 집중
- 결측 50% 초과 센서 28개, 값이 하나뿐인 센서 116개 삭제 → 센서 446개, 결측치 0개인 `secom_clean.csv` 생성

## 실행 방법

1. `data/README.md`에 따라 구글 드라이브에 SECOM 파일을 올립니다.
2. 노트북을 코랩에서 열고 **런타임 → 모두 실행**을 누릅니다. 셀은 위에서부터 차례대로 실행해야 합니다.
