# konec: Korean Named Entity Corpus

한국어 개체명 말뭉치 `konec`은 KLUE Benchmark의 개체명 주석 말뭉치 중 공개된
전체 원시 문장에 150 세부류 개체명 태그를 부착한 말뭉치이다. 

* [개요](#개요)
  * [규모](#규모)
  * [원천 자료](#원천-자료)
  * [말뭉치 형식](#말뭉치-형식)
  * [태그셋과 가이드라인](#태그셋과-가이드라인)
* [통계](#통계)
* [참고문헌](#참고문헌)

## 개요

### 규모 

문장의 개수로 본 말뭉치의 규모는 다음과 같다.

| source   | train |  dev | total |
|---------:|------:|-----:|------:|
| wikitree | 11435 | 2534 | 13969 |
| nsmc     |  9573 | 2466 | 12039 |
| total    | 21008 | 5000 | 26008 |

### 원천 자료

다음 저장소에서 KLUE benchmark v1.1의 원본 데이터를 확인할 수 있다.
개체명 말뭉치는 dev와 train 2개의 tsv 파일로 제공되고 있다.

- <https://github.com/KLUE-benchmark/KLUE>
- `klue-ner-v1.1_dev.tsv`
- `klue-ner-v1.1_train.tsv`

구축 과정에서 KLUE NER v1.1에 존재하는 형식 오류 및 원문 오류들을 다수
수정하였다. 수정된 결과물은 다음 저장소에서 확인할 수 있다.

- <https://github.com/korean-named-entity/KLUE/tree/ner-fix>

이렇게 수정된 KLUE NER의 원시 문장과 `konec`의 원시 문장은 일치한다.

### 말뭉치 형식

- 문장 고유번호는 klue-ner-v1.1과 동일하게 유지하였다.
- klue-ner-v1.1과 동일한 BIO 형식을 채택하였다. 
- 주석 행(`##` 행)의 문장 정보에서 klue-ner-v1.1은 인라인 태깅 정보를
  제공하지만 konec은 원시 문장 정보를 제공한다.
  
konec:

```
## klue-ner-v1_train_00025_nsmc 이동욱님 재치도 넘치시고 너무좋았어요
이	B-PS_NAME
동	I-PS_NAME
욱	I-PS_NAME
님	O
 	O
재	O
치	O
도	O
```


klue-ner-v1:

```
## klue-ner-v1_train_00025_nsmc <이동욱:PS>님 재치도 넘치시고 너무좋았어요
이	B-PS
동	I-PS
욱	I-PS
님	O
 	O
재	O
치	O
도	O
```
  
  
### 태그셋과 가이드라인

국립국어원의 150개 세부분류 개체명 태그셋과 지침을 기준으로 주석하였다.
태그셋은 다음 파일에서 확인할 수 있다.

- [NIKL_NE_2021_TAGSET_150.tsv](docs/NIKL_NE_2021_TAGSET_150.tsv)
- [NIKL_NE_2021_TAGSET_150.json](docs/NIKL_NE_2021_TAGSET_150.json)

태그셋 및 지침과 관련한 정보는 다음 문서에서 확인할 수 있다.

- 한국전자통신연구원(ETRI)의 '세부분류 개체명 가이드라인 2018'(2018. 12)를 기본으로 하여 국립국어원에서 수정한
- 2020년 개체명 분석 말뭉치 구축 지침 ver 1.6
  - 국립국어원 > 자료 > 연구조사자료 > 연구보고서 > [2020년 개체명 말뭉치 연구분석](https://www.korean.go.kr/front/reportData/reportDataView.do?mn_id=207&report_seq=1050&pageIndex=1)
- 2021년 개체명 분석 말뭉치 구축 지침 ver 2.1
  - 국립국어원 > 자료 > 연구조사자료 > 연구보고서 > [2021년 개체명 분석 및 개체 연결 말뭉치 연구 분석](https://www.korean.go.kr/front/reportData/reportDataView.do?mn_id=207&report_seq=1078)

국립국어원에서는 이 태그셋과 지침에 따라 개체명 표지를 부착한 말뭉치를 모두의
말뭉치 사이트에 공개하고 있다.

- 모두의 말뭉치: <https://corpus.korean.go.kr/>
- 국립국어원 개체명 분석 말뭉치 2020 (버전 2.0) 2022. 4. 1.
- 국립국어원 개체명 분석 말뭉치 2021 (버전 1.0) 2022. 4. 1.


## 통계 



## 참고문헌

- 정유남, 송영숙, 유현조. (2022 예정). 한국어 중첩 개체명 말뭉치 구축의 실제.
  2022년 세계 한국어 한마당 학술대회 발표자료집, 국어학회.

```
@inproceedings{cheong2022,
  author    = {정유남 and 송영숙 and 유현조},
  title     = {한국어 중첩 개체명 말뭉치 구축의 실제},
  booktitle = {2022년 세계 한국어 한마당 학술대회 발표자료집},
  year      = {2022 예정},
  publisher = {국어학회}
}
```




