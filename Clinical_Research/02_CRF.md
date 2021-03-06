# Case Report Form

> 계획서에 명시된 임상시험의 목적을 달성하기 위한 최소한의 data collection tool.

2021.07.08

---

[TOC]

---



## 용어

```markdown
### Hierarchy
- CRF Group (Page)
- CRF
- Question
- Item
- (Layout)
```



## Type

### Cycle

```markdown
- Normal (NV)
- All Visit (AV)
- Unscheduled (UV)
- Follow-up (FU)
- Report (SAE)
```



### Page

```markdown
1. CRF Page
2. Registration Page
3. Enroll/Random Page
4. AE Page
5. SAE Page
6. Laboratory Test
```

|       Page Type        |                     특징                      |      CRF Group       |
| :--------------------: | :-------------------------------------------: | :------------------: |
| **Registration Page**  |           Subject Registration Page           |        **EN**        |
| **Enroll/Random Page** |                                               |        **RN**        |
|      **AE Page**       | SAE 와 연계를 위하여 Item Event가 설정된 page |        **AE**        |
|      **SAE Page**      |                                               |       **SAE**        |
|  **Laboratory Test**   |                                               |        **LB**        |
|      **CRF Page**      |                                               | 이외 SV, DM, IP 등등 |



### Question

```markdown
- Normal Question (NL)
- Category Question (CT)
- Table Question (TB)
- Static rownum table (ST)
```

- :white_check_mark: 이외에도 `Paging Question`과 `System hidden question`이 있다.

|         Qustion Type         |                          특징                          |          예시          |
| :--------------------------: | :----------------------------------------------------: | :--------------------: |
|   **Normal Question (NL)**   |                   일반적인 Question                    |                        |
|  **Category Question (CT)**  |                하위 Question을 갖는다.                 | `PG_CT, VS_CT, SAE_CT` |
|   **Table Question (TB)**    |               추가 가능한 행으로 구성됨                | `MH_TB, AE_TB, CM_TB`  |
| **Static rownum table (ST)** |             고정된 행을 가지는 테이블 형태             |     `LB_ST, DA_ST`     |
|       Paging Question        |            페이징 처리를 가지는 테이블 형태            |                        |
|    System hidden question    | 시스템에서 필요에 의해 생성된 사용자에게 노출되지 않음 |                        |

- :ballot_box_with_check: Static rownum table의 가장 큰 특징은 각각의 행마다 다른 layout(형식)을 지정할 수 있다.

**ID 설정방식**

|        Question         |                 ID 설정방식                 |
| :---------------------: | :-----------------------------------------: |
|   **Normal Question**   |              `ITEM_ID`와 동일               |
|  **Category Question**  | `<CRF_ID>_CT, <CRF_ID>_CT01, <CRF_ID>_CT02` |
|   **Table Question**    | `<CRF_ID>_TB, <CRF_ID>_TB01, <CRF_ID>_TB02` |
| **Static rownum table** | `<CRF_ID>_ST, <CRF_ID>_ST01, <CRF_ID>_ST02` |





### Layout

|          Layout           |                       대상 item                       |
| :-----------------------: | :---------------------------------------------------: |
|         **CHECK**         |                     `~ND, ~NONE`                      |
|         **CONST**         |                       `LBTEST`                        |
|         **DATE**          |                        `~DTC`                         |
|       **DROPDOWN**        | `AEOUT, AESER, AESEV, AEREL, AEACN, AEACNOTH, CMINDC` |
| **DROPDOWN_OTHER_MEDCOD** |                 `CMINDCMH, CMINDCAE`                  |
|    **DROPDOWN_OTHER**     |                       `CMINDCO`                       |
|         **DUMMY**         |                      `CRF_IE` 등                      |
|         **GROUP**         |                                                       |
|      **INNERTABLE**       |                 (Table QST 하위 항목)                 |
|        **MEDCOD**         |                `MHTERM, AETERM, CMTRT`                |
|         **RADIO**         |       `~YN, ~REAS, ~ONGO, SEX, LBNOR, DSDECOD`        |
|        **ROWNUM**         |                         `SEQ`                         |
|      **SYSDEFINED**       |                       `SUBJID`                        |
|       **TEXT_AREA**       |                 `REASON, COMMENT` 등                  |
|      **TEXT_INPUT**       |                 `VS, LBORRES, AGE` 등                 |

- :white_check_mark: Date, YearMon, Time:
  - `YYYY-MM-DD`, `HH:MM:SS` 형태로 입력
  - Date의 경우 년월까지 입력하거나 혹은 년월일에 각각 UK가 적용된 형태의 달력 사용할 수 있음(2021-UK-UK)



***Copyright* © 2021 Song_Artish**

