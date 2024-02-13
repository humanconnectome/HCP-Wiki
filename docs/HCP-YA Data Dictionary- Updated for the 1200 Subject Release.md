## HCP-YA Data Dictionary- Updated for the 1200 Subject Release

### ***Updated S1200 HCP Young Adult (HCP-YA) Data Dictionary spreadsheet******:***

### **Excel version:** [HCP_S1200_DataDictionary_Oct_30_2023.xlsx](./assets/HCP_S1200_DataDictionary_Oct_30_2023.xlsx)

### **CSV version:** [HCP_S1200_DataDictionary_Oct_30_2023.csv](./assets/HCP_S1200_DataDictionary_Oct_30_2023.csv)

### *Up to date variable descriptions are also viewable within the ConnectomeDB subject dashboard by mousing over the column name or selecting "Data Dictionary" from the column name dropdown.*

### ***Note: Much of the information below is out of date or incomplete-- please download the spreadsheet at the link above for current variable descriptions.***

Dashboard filtering starts at the Category level, and each category is represented by a separate data table in the ConnectomeDB interface. Multiple data tables are arranged in a tabbed format. 

Each "Instrument" contains multiple "Attributes" - these attributes correspond to actual columns of data in ConnectomeDB. 

**All Categories and Instruments**

### Category: Subject Information

#### Instrument: Demographics



| Display Name (in menu) | Column Header | Access | Validation | (Enumerated) Values | Comparators | Description |
| --- | --- | --- | --- | --- | --- | --- |
| Subject | Subject | Open | ^[A-z0-9\_,|]+$ |  | =, NOT =, CONTAINS, DOESN'T CONTAIN, IS EMPTY, IS NOT EMPTY | HCP Subject ID |
| Quarterly Release | Release | Open |  | * Q1
* Q2
* Q3
* 500
 | = | HCP data release in which this subject's data was initially published to ConnectomeDB. Note: “Release” does not indicate the version of the pipelines used to process subject data. Check the release-notes distributed with each processed dataset for pipeline version information. |
| Gender | Gender | Open |  | * M
* F
 | = | Gender of Subject |
| Age Range | Age | Open |  | * 22-25
* 26-30
* 31-35
* >35
 | =  | Age group of Participant, banded in five-year increments |
| Age in Years | Age\_in\_Yrs | **Tier 1 Restricted** | 
```
^[0-9]+$
```
 |  | =, NOT =, <, > | Age of Participant in Years |
| Twin Status | Twin\_Stat | **Tier 1 Restricted** |  | * Not a twin
* Twin
 | =, NOT = |  |
| Zygosity | Zygosity | **Tier 1 Restricted** |  | * Not a twin
* Monozygotic
* Not Monozygotic
 | =, NOT = |  |
| Mother ID | Mother\_ID | **Tier 1 Restricted** | ^[0-9]+$ |  | =, NOT = |  |
| Father ID | Father\_ID | **Tier 1 Restricted** | ^[0-9]+$ |  | =, NOT = |  |
| Race | Race | **Tier 1 Restricted** |  | * Am. Indian/Alaskan Nat.
* Asian/Nat. Hawaiian/Othr Pacific Is.
* Black or African Am.
* White
* More than one
* Unknown or Not Reported
 | =, NOT = |  |
| Ethnicity | Ethnicity | **Tier 1 Restricted** |  | * Hispanic/Latino
* Not Hispanic/Latino
* Unknown or Not Reported
 | =, NOT = |  |
| Handedness | Handedness | **Tier 1 Restricted** | 
```
^[-+]?([0-9]{1,2}|100)$
```
 |  | =, NOT =, <, > | Handedness of participant from -100 to 100. Negative numbers indicate that a subject is more left-handed than right-handed, while positive numbers indicate that a subject is more right-handed than left-handed. See Schachter et al., Associations of handedness with hair color and learning disabilities. Neuropsychologia, 25:269-276, 1987. for more information on how these laterality scores are calculated. |
| Employment Status | SSAGA\_Employ | **Tier 1 Restricted** |  |  |  | Participant's employment status: not working = 0, part-time employment = 1; full-time employment = 2 |
| Income | SSAGA\_Income | **Tier 1 Restricted** |  |  |  | Total household income: <$10,000 = 1,10K-19,999 = 2, 20K-29,999 = 3,30K-39,999 = 4, 40K-49,999 = 5, 50K-74,999 = 6, 75K-99,999 = 7, >=100,000 = 8 |
| Education | SSAGA\_Educ | **Tier 1 Restricted** |  |  |  | Years of education completed: <11 = 11; 12; 13; 14; 15; 16; 17+ = 17 |
| Still in School | SSAGA\_InSchool | **Tier 1 Restricted** |  |  |  | Is respondent still in school for degree course? no = 0; yes = 1 |
| Relationship Status | SSAGA\_Rlshp | **Tier 1 Restricted** |  |  |  | Is respondent married or in live-in relationship? no = 0; yes = 1 |
| Missouri Born | SSAGA\_MOBorn | **Tier 1 Restricted** |  |  |  | Is respondent Missouri born? no = 0; yes = 1 |

### Category: Study Completion

#### Instrument: Study Completion: 3T MR



| Display Name (in menu) | Column Header | Access | Validation | (Enumerated) Values | Comparators | Description |
| --- | --- | --- | --- | --- | --- | --- |
| Full Imaging Protocol Completed | Full\_MR\_Compl | Open |  | * True
* False
 | = | Full HCP MRI protocol was completed |
| T1 Scan Count | T1\_Count | Open |  | 0,1,2 | =,NOT =,<,> | Number of T1 scans collected |
| T2 Scan Count | T2\_Count | Open |  | 0,1,2 | =,NOT =,<,> | Number of T2 scans collected |
| Resting State fMRI Count | RS-fMRI\_Count | Open |  | 0,1,2,3,4 | =,NOT =,<,> | Number of resting state scans collected |
| Full Task fMRI Protocol Completed | Full\_Task\_fMRI | Open |  | * True
* False
 | =   | Full task fMRI protocol was completed |
| Task fMRI – Working Memory Completed | fMRI\_WM\_Compl | Open |  | * True
* False
 | =   | Working memory task fMRI was collected |
| Task fMRI – Gambling Completed | fMRI\_Gamb\_Compl | Open |  | * True
* False
 | =   | Gambling task fMRI was collected |
| Task fMRI – Motor Completed | fMRI\_Mot\_Compl | Open |  | * True
* False
 | =   | Motor task fMRI was collected |
| Task fMRI – Language Completed | fMRI\_Lang\_Compl | Open |  | * True
* False
 | =   | Language task fMRI was collected |
| Task fMRI – Social Cognition Completed | fMRI\_Soc\_Compl | Open |  | * True
* False
 | =   | Social cognition task fMRI was collected |
| Task fMRI – Relational Processing Completed | fMRI\_Rel\_Compl | Open |  | * True
* False
 | =   | Relational processing task fMRI was collected |
| Task fMRI – Emotion Processing Completed | fMRI\_Emo\_Compl | Open |  | * True
* False
 | =   | Emotion processing task fMRI was collected |
| Diffusion MRI Completed | dMRI\_Compl | Open |  | * True
* False
 | =   | Full diffusion MRI protocol was collected |

#### Instrument: Image Reconstruction Info: 3T MR



| Display Name (in menu) | Column Header | Access | Validation | (Enumerated) Values | Comparators | Description |
| --- | --- | --- | --- | --- | --- | --- |
| 3T MR dMRI Recon Version | dMRI\_3T\_ReconVrs | Open |  |  |  |  |
| 3T MR fMRI Recon Version | fMRI\_3T\_ReconVrs | Open |  |  |  |  |

#### Instrument: Study Completion - MEG



| Display Name (in menu) | Column Header | Access | Validation | (Enumerated) Values | Comparators | Description |
| --- | --- | --- | --- | --- | --- | --- |
| Any MEG Data Available | MEG\_AnyData | Open |  | True False | = |  |
| Full Protocol Complete | MEG\_FullProt\_Compl | Open |  | True False | = |  |
| Head Model Available | MEG\_HeadModel\_Avail | Open |  | True False | = |  |
| Cortical Ribbon Available | MEG\_CortRibn\_Avail | Open |  | True False | = |  |
| Anatomy Data Available | MEG\_Anatomy\_Avail | Open |  | True False | = |  |
| Anatomy Data Complete | MEG\_Anatomy\_Compl | Open |  | True False | = |  |
| Noise Data Available | MEG\_Noise\_Avail | Open |  | True False | = |  |
| Noise Data Complete | MEG\_Noise\_Compl | Open |  | True False | = |  |
| Resting State Data Available | MEG\_RS\_Avail | Open |  | True False | = |  |
| Resting State Data Complete | MEG\_RS\_Compl | Open |  | True False | = |  |
| Working Memory Data Available | MEG\_WM\_Avail | Open |  | True False | = |  |
| Working Memory Data Complete | MEG\_WM\_Compl | Open |  | True False | = |  |
| Story Math Data Available | MEG\_StoryMath\_Avail | Open |  | True False | = |  |
| Story Math Data Complete | MEG\_StoryMath\_Compl | Open |  | True False | = |  |
| Motor Data Available | MEG\_Motor\_Avail | Open |  | True False | = |  |
| Motor Data Complete | MEG\_Motor\_Compl | Open |  | True False | = |  |

#### Instrument: Study Completion - Behavioral



| Display Name | Column Header | Access | Validation | (Enumerated) Values | Comparators | Description |
| --- | --- | --- | --- | --- | --- | --- |
| Full Non-Toolbox Battery Completed | Non-TB\_Compl | Open |  | * True
* False
 | = | Full non-NIH Toolbox behavioral battery was completed |
| Visual Processing Completed | VisProc\_Compl | Open |  | * True
* False
 | = | Mars Contrast Sensitivity Test (Visual Processing) was completed |
| Delay Discounting Completed | DelDisc\_Compl | Open |  | * True
* False
 | = | Self-regulation/Impulsivity (Delay Discounting) assessment was completed |
| Short Penn Continuous Performance Test (SCPT) Completed | SCPT\_Compl | Open |  | * True
* False
 | = | Short Penn Continuous Performance Test (SCPT) (Sustained Attention) was completed |
| Penn Word Memory Test (IWRD) Completed | IWRD\_Compl | Open |  | * True
* False
 | = | Penn Word Memory Test (IWRD) (Verbal Episodic Memory) was completed |
| Penn Matrix Test (PMAT) Completed | PMAT\_Compl | Open |  | * True
* False
 | = | Fluid Intelligence (Penn Progressive Matrices) was completed |
| Variable Short Penn Line Orientation Test (VSPLOT) Completed | VSPLOT\_Compl | Open |  | * True
* False
 | = | Spatial Orientation (Variable Short Penn Line Orientation Test) was completed |
| Emotion Recognition (Penn Emotion Recognition Test) Completed | EmoRecog\_Compl | Open |  | * True
* False
 | = | Emotion Recognition (Penn Emotion Recognition Test) was completed |
| Five Factor Model (NEO-FFI) Completed | NEO-FFI\_Compl | Open |  | * True
* False
 | = | Five Factor Model (NEO-FFI) was completed |
| Achenbach Adult Self Report (ASR) - Syndrome Scale Completed | ASR-Syn\_Compl | Open |  | * True
* False
 | = | Achenbach Adult Self Report (ASR) - Syndrome Scale was completed |
| Achenbach Adult Self Report (ASR) - DSM-Oriented Scale Completed | ASR-DSM\_Compl | Open |  | * True
* False
 | = | Achenbach Adult Self Report (ASR) - DSM-Oriented Scale was completed |
| Full NIH Toolbox Battery Completed | Toolbox\_Compl | Open |  | * True
* False
 | = | Full NIH Toolbox behavioral battery was completed |
| Mini Mental State Examination (MMSE) Completed | MMSE\_Score | Open |  | * True
* False
 | = | Mini Mental State Examination (MMSE) was completed |
| Pittsburgh Sleep Quality Index (PSQI) Completed | PSQI\_Score | Open |  | * True
* False
 | = | Pittsburgh Sleep Quality Index (PSQI) was completed |
| Full Alertness Battery Completed | Alert\_Compl | Open |  | * True
* False
 | = | Full alertness battery was completed |
| Alcohol and Smoking Questionnaire (ASQ) Completed | ASQ\_Compl | Open |  | * True
* False
 | = |  |
| Family Psychiatric and Neuro. | FamPsychNeuro\_Compl | Open |  | * True
* False
 | = |  |
| SSAGA Demographics Completed | SSAGA\_Demo\_Compl | Open |  | * True
* False
 | = |  |
| SSAGA Mental Health Completed | SSAGA\_Mental\_Compl | Open |  | * True
* False
 | = |  |
| SSAGA Alcohol Use and Dependence Completed | SSAGA\_Alc\_Compl | Open |  | * True
* False
 | = |  |
| SSAGA Illicit Drug Use and Dependence Completed | SSAGA\_Illicit\_Compl | Open |  | * True
* False
 | = |  |
| SSAGA Tobacco Use and Dependence Completed | SSAGA\_Tob\_Compl | Open |  | * True
* False
 | = |  |
| SSAGA Marijuana Use and Dependence Completed | SSAGA\_Mj\_Compl | Open |  | * True
* False
 | = |  |

### Category: MR Sessions

#### Instrument: Session Information



| Display Name (in menu) | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| MR Session Label | MRsession\_Label | Open | ^[A-z0-9\_,|]+$ | =, NOT =, CONTAINS, DOESN'T CONTAIN, IS EMPTY, IS NOT EMPTY |  |
| MR Session Scanner | MRsession\_Scanner | Open |  ^[A-z0-9\_,|]+$ | =, NOT =, CONTAINS, DOESN'T CONTAIN, IS EMPTY, IS NOT EMPTY |  |
| MR Session Scans | MRsession\_Scans | Open |  ^[A-z0-9\_,|()]+$ | =, NOT =, CONTAINS, DOESN'T CONTAIN, IS EMPTY, IS NOT EMPTY |  |

### Category: Health and Family History

#### Instrument: Physical Health



| Display Name (in menu) | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Height | Height | **Tier 1 Restricted** | ^[0-9]+$ | =, NOT =, <, > | Height of Participant in Inches |
| Weight | Weight | **Tier 1 Restricted** | ^[0-9]+$ | =, NOT =, <, > | Weight of Participant in Pounds |
| Body Mass Index | BMI | **Tier 1 Restricted** | ^[0-9]+$ | =, NOT =, <, > | BMI = 703 \* weight (lb) / (height in.)^2 |
| BMI Category | SSAGA\_BMICat | **Tier 1 Restricted** | ^[0-9]+$ | =, NOT =, <, > | Participant's current self-reported BMI category: lean/underweight = 1; overweight = 2; obese =3 ; obese II or III (BMI>=35) = 4 |
| BMI Category Heaviest | SSAGA\_BMICatHeaviest | **Tier 1 Restricted** | ^[0-9]+$ | =, NOT =, <, > | Participant' self-reported BMI category for their heaviest period: lean/underweight = 1; overweight = 2; obese =3 ; obese II or III (BMI>=35) = 4 |
| Blood Drawn? | Blood\_Drawn | **Tier 1 Restricted** |  | = | Was blood drawn from participant for hematocrit, TSH and HBA1C testing?  Yes = 1, No = 2 |
| Hematocrit Sample 1 | Hematocrit\_1 | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Blood sample 1 percentage of total blood volume that are red blood cells. The normal range is 38.8 to 50 percent for men and 34.9 to 44.5 percent for women. |
| Hematocrit Sample 2 | Hematocrit\_2 | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Blood sample 2 percentage of total blood volume that are red blood cells. The normal range is 38.8 to 50 percent for men and 34.9 to 44.5 percent for women. |
| Blood Pressure - Systolic | BPSystolic | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Systolic blood pressure of subject. A normal systolic blood pressure is below 120. |
| Blood Pressure - Diastolic | BPDiastolic | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Diastolic blood pressure of subject. A normal diastolic blood pressure is below 80. |
| Thyroid Stimulating Hormone | ThyroidHormone | **Tier 2 Restricted** | ^[A-z0-9\_,|]+$ | =,NOT =,<,> | Amount of thyroid stimulating hormone (TSH) in subject's blood in milliunits per liter (mU/L). A normal range for TSH is 0.4 mU/L to 4.0 mU/L. |
| Hemoglobin A1C (HbA1C) | HbA1C | **Tier 2 Restricted** | ^[A-z0-9\_,|]+$ | =,NOT =,<,> | Percentage of subject's hemoglobin that is coated with sugar (glycated). Normal A1C level range is 4.5 to 6 percent. Higher than normal levels indicate risk for diabetes. |
| Hypothyroidism | Hypothyroidism | **Tier 2 Restricted** |  | = | History of Hypothyroidism? Yes = 1, No = 0 |
| Hypothyroidism - Age at onset | Hypothyroidism\_Onset | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Age in years of hypothyroidism onset, if applicable  |
| Hyperthyroidism | Hyperthyroidism | **Tier 2 Restricted** |  | = | History of Hyperthyroidism? Yes = 1, No = 0 |
| Hyperthyroidism - Age at onset | Hyperthyroidism\_Onset | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Age in years of hyperthyroidism onset, if applicable |
| Other Endocrine Problem | OtherEndocrn\_Prob | **Tier 2 Restricted** |  | = | History of other endocrine disorder? Yes = 1, No = 0 |
| Other Endocrine Problem - Age at onset | OtherEndocrine\_ProbOnset | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Age in years of other endocrine disorder onset, if applicable |
| Menstrual - Regular cycles | Menstrual\_RegCycles | **Tier 1 Restricted** |  | = | Does the participant report having regular menstrual cycles? Yes = 1, No = 0 (Asked of female participants only) |
| Menstrual - Explain (If no) | Menstrual\_Explain | **Tier 1 Restricted** | ^[A-z0-9\_,|]+$ | =,NOT =,<,> | If participant is not having regular menstrual cycles, explain possible reasons why. (Asked of female participants only) |
| Menstrual - Age Cycle Began | Menstrual\_AgeBegan | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant's age at first menstrual cycle. (Asked of female participants only) |
| Menstrual - Cycle Length (between start dates) | Menstrual\_CycleLength | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Average length of participant's menstrual cycles in days. 1=Less than 25 days, 2=Between 25-35 days, and 3=More than every 35 days (Asked of female participants only) |
| Menstrual - Days Since Last Period | Menstrual\_DaysSinceLast | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Number of days since last menstrual period occurred. (Asked of female participants only) |
| Menstrual - Age Cycles Became Irregular | Menstrual\_AgeIrreg | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant's age when menstrual cycles became irregular in length? (Asked of female participants only) |
| Menstrual - Age Cycles Stopped | Menstrual\_AgeStop | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant's age when menstrual cycles stopped. (Asked of female participants only) |
| Menstrual - If amenorrheic, months since menarche | Menstrual\_MonthsSinceStop | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | If participant is amenorrheic, months since menarche (cycle stopped). (Asked of female participants only) |
| Menstrual - Using birth control pills, progesterone, or fertility drugs | Manstrual\_UsingBirthControl | **Tier 1 Restricted** |  | = | Is participant using birth control pills, progesterone, or fertility drugs? Yes = 1, No = 0 (Asked of female participants only) |
| Menstrual - Birth control/Fertility drug code | Menstrual\_BirthControlCode | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT =,<,> | What birth control, progesterone, or fertility drugs is the participant using? 1=OC's for contraception, 2=OC's primarily for menstrual regulation, 3=estradiol for menstrual regulation, 4=progesterone for menstrual regulation, 5=fertility therapy, 6=other, 7=unknown  (Asked of female participants only) |

#### Instrument: Family History of Psychiatric and Neurologic Disorders



| Display Name | Column Header | Access | Validation | Comparators   | Description |
| --- | --- | --- | --- | --- | --- |
| Schizophrenia or Psychosis - Mother | FamHist\_Moth\_Scz | **Tier 2 Restricted** |  | = | Does the participant report that their mother had schizophrenia or psychosis. |
| Schizophrenia or Psychosis - Father | FamHist\_Fath\_Scz | **Tier 2 Restricted** |  | = | Does the participant report that their father had schizophrenia or psychosis. |
| Depression - Mother | FamHist\_Moth\_Dep | **Tier 2 Restricted** |  | = | Does the participant report that their mother had depression. |
| Depression - Father | FamHist\_Fath\_Dep | **Tier 2 Restricted** |  | = | Does the participant report that their father had depression. |
| Bipolar Disorder - Mother | FamHist\_Moth\_BP | **Tier 2 Restricted** |  | = | Does the participant report that their mother had bipolar disorder. |
| Bipolar Disorder - Father | FamHist\_Fath\_BP | **Tier 2 Restricted** |  | = | Does the participant report that their father had bipolar disorder. |
| Anxiety - Mother | FamHist\_Moth\_Anx | **Tier 2 Restricted** |  | = | Does the participant report that their mother had anxiety. |
| Anxiety - Father | FamHist\_Fath\_Anx | **Tier 2 Restricted** |  | = | Does the participant report that their father had anxiety. |
| Drug or Alcohol Problems - Mother | FamHist\_Moth\_DrgAlc | **Tier 2 Restricted** |  | = | Does the participant report that their mother had drug or alcohol problems. |
| Drug or Alcohol Problems - Father | FamHist\_Fath\_DrgAlc | **Tier 2 Restricted** |  | = | Does the participant report that their father had drug or alcohol problems. |
| Alzheimer's Disease or Dementia - Mother | FamHist\_Moth\_Alz | **Tier 2 Restricted** |  | = | Does the participant report that their mother had Alzheimer's Disease or dementia. |
| Alzheimer's Disease or Dementia - Father | FamHist\_Fath\_Alz | **Tier 2 Restricted** |  | = | Does the participant report that their father had Alzheimer's Disease or dementia. |
| Parkinson's Disease - Mother | FamHist\_Moth\_PD | **Tier 2 Restricted** |  | = | Does the participant report that their mother had Parkinson's Disease. |
| Parkinson's Disease - Father | FamHist\_Fath\_PD | **Tier 2 Restricted** |  | = | Does the participant report that their father had Parkinson's Disease. |
| Tourette's Syndrome - Mother | FamHist\_Moth\_TS | **Tier 2 Restricted** |  | = | Does the participant report that their mother had Tourette's Syndrome. |
| Tourette's Syndrome - Father | FamHist\_Fath\_TS | **Tier 2 Restricted** |  | = | Does the participant report that their father had Tourette's Syndrome. |
| None of the above - Mother | FamHist\_Moth\_None | **Tier 2 Restricted** |  | = |  |
| None of the above - Father | FamHist\_Fath\_None | **Tier 2 Restricted** |  | = |  |

### Category: Alertness

#### Instrument: Cognitive Status (Mini Mental Status Exam)



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Mini Mental Status Exam Total Score | MMSE\_Score | Open | ^[0-9]+$ | =,NOT =,<,> |  |

#### Excluded Fields: Cognitive Status (Mini Mental Status Exam)



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| I. Orientation - Today's Year | MMSE\_Orientation\_Year | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - Current Month | MMSE\_Orientation\_Month | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - Day (e.g. Monday) | MMSE\_Orientation\_Day | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - Season | MMSE\_Orientation\_Season | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - Name of Hospital/Clinic | MMSE\_Orientation\_Hospital | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - What Floor | MMSE\_Orientation\_Floor | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - What City | MMSE\_Orientation\_City | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - What County | MMSE\_Orientation\_County | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| I. Orientation - What State | MMSE\_Orientation\_State | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| II. Immediate Recall - Ball | MMSE\_IR\_Ball | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| II. Immediate Recall - Flag | MMSE\_IR\_Flag | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| II. Immediate Recall - Tree | MMSE\_IR\_Tree | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| II. Immediate Recall - Number of Trials | MMSE\_IR\_Num\_Trials | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation A. Counting Backwards Test - 93 | MMSE\_AC\_CountBW\_93 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation A. Counting Backwards Test - 86 | MMSE\_AC\_CountBW\_86 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation A. Counting Backwards Test - 79 | MMSE\_AC\_CountBW\_79 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation A. Counting Backwards Test - 72 | MMSE\_AC\_CountBW\_72 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation A. Counting Backwards Test - 65 | MMSE\_AC\_CountBW\_65 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation B. Spelling Backwards Test - D | MMSE\_AC\_SpellBW\_D | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation B. Spelling Backwards Test - L | MMSE\_AC\_SpellBW\_L | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation B. Spelling Backwards Test - R | MMSE\_AC\_SpellBW\_R | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation B. Spelling Backwards Test - O | MMSE\_AC\_SpellBW\_O | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation B. Spelling Backwards Test - W | MMSE\_AC\_SpellBW\_W | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| III. Attention and Calculation C. Final Score | MMSE\_AC\_Final\_Score | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| IV. Recall - Ball | MMSE\_Recall\_Ball | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| IV. Recall - Flag | MMSE\_Recall\_Flag | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| IV. Recall - Tree | MMSE\_Recall\_Tree | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - Naming - Watch | MMSE\_Lang\_Naming\_Watch | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - Naming - Pencil | MMSE\_Lang\_Naming\_Pencil | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - Repetition - No if's, ands, or buts | MMSE\_Lang\_Repetition | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - 3 Stage Command - 1. Takes paper in hand | MMSE\_Lang\_3StageCommand\_S1 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - 3 Stage Command - 2. Folds paper in half | MMSE\_Lang\_3StageCommand\_S2 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - 3 Stage Command - 3. Puts paper on floor | MMSE\_Lang\_3StageCommand\_S3 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - Reading - Closes Eyes | MMSE\_Lang\_Reading | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - Writing - Writes sentence | MMSE\_Lang\_Writing | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| V. Language - Copying - Copies pentagons | MMSE\_Lang\_Copying | Open | ^[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Sleep (Pittsburgh Sleep Questionnaire)



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Sleep (Pittsburgh Sleep Questionnaire) Total Score | PSQI\_Score | Open | ^[0-9]+$ | =,NOT =,<,> | The total score across all items on the Pittsburgh Sleep Questionnaire |

#### Excluded Instrument Fields: Sleep (Pittsburgh Sleep Questionnaire)



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| 1. Usual bed time (past month) | PSQI\_Bed\_Time | Open | ^.+$ | =, NOT =, CONTAINS, DOESN'T CONTAIN, IS EMPTY, IS NOT EMPTY |  |
| 2. Minutes to fall asleep (past month) | PSQI\_Time\_Fall\_AsleepMPH: PSQI\_Minutes\_Fall\_Asleep ("time" is ambiguous in this context) | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 3. Time get up in morning (past month) | PSQI\_GetUp\_Time | Open | ^.+$ | =, NOT =, CONTAINS, DOESN'T CONTAIN, IS EMPTY, IS NOT EMPTY |  |
| 4. Hours of sleep per night (past month) | PSQI\_Sleep\_Hours | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| 5a. Sleep Trouble - Can't get to sleep within 30 minutes | PSQI\_Trouble\_Within30 | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5b. Sleep Trouble - Wake up in middle of night or early morning | PSQI\_Trouble\_WakeUp | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5c. Sleep Trouble - Get up to use bathroom | PSQI\_Trouble\_Bathroom | Open | ^[0-9]+$ YES ORNO | =,NOT =,<,> |  |
| 5d. Sleep Trouble - Can't breathe comfortably | PSQI\_Trouble\_Breath | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5e. Sleep Trouble - Cough or snore loudly | PSQI\_Trouble\_Snore | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5f. Sleep Trouble - Feel too cold | PSQI\_Trouble\_Cold | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5g. Sleep Trouble - Feel too hot | PSQI\_Trouble\_Hot | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5h. Sleep Trouble - Had bad dreams | PSQI\_Trouble\_Dreams | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5i. Sleep Trouble - Have pain | PSQI\_Trouble\_Pain | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5j. Sleep Trouble - Other | PSQI\_Trouble\_Other | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 5j. Sleep Trouble - Describe other | PSQI\_Trouble\_Describe | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 6. Describe overall sleep quality | PSQI\_Sleep\_Quality | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 7. How often taken sleep medicine | PSQI\_Sleep\_Medicine | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 8. How often trouble staying awake | PSQI\_Staying\_Awake | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 9. How often trouble keeping up enthusiasm | PSQI\_Keeping\_Enthusiasm | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| 10. Have bed partner or roommate | PSQI\_Sleep\_Partner | Open | ^[0-9]+$ | =,NOT =,<,> |  |

### Category: Cognition

#### Instrument: Episodic Memory (Picture Sequence Memory)

**Instrument Description:**


> The Picture Sequence Memory Test is a measure developed for the Open of episodic memory for ages 3-85 years. It involves recalling increasingly lengthy series of illustrated objects and activities that are presented in a particular order on the computer screen. The participants are asked to recall the sequence of pictures that is demonstrated over two learning trials; sequence length varies from 6-18 pictures, depending on age. Participants are given credit for each adjacent pair of pictures (i.e., if pictures in locations 7 and 8 and placed in that order and adjacent to each other anywhere - such as slots 1 and 2 - one point is awarded) they correctly place, up to the maximum value for the sequence, which is one less than the sequence length (if there are 18 pictures in the sequence, the maximum score is 17, because that is the number of adjacent pairs of pictures that exist). The test takes approximately 7 minutes to administer. This test is recommended for ages 3-85.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Picture Sequence Memory Test: Unadjusted Scale Score | PicSeq\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | The Picture Sequence Memory Test is a measure developed for the assessment of episodic memory for ages 3-85 years. It involves recalling increasingly lengthy series of illustrated objects and activities that are presented in a particular order on the computer screen. The participants are asked to recall the sequence of pictures that is demonstrated over two learning trials; sequence length varies from 6-18 pictures, depending on age. Participants are given credit for each adjacent pair of pictures (i.e., if pictures in locations 7 and 8 and placed in that order and adjacent to each other anywhere – such as slots 1 and 2 – one point is awarded) they correctly place, up to the maximum value for the sequence, which is one less than the sequence length (if there are 18 pictures in the sequence, the maximum score is 17, because that is the number of adjacent pairs of pictures that exist). The test takes approximately 7 minutes to administer. This test is recommended for ages 3-85. |
| NIH Toolbox Picture Sequence Memory Test: Age-Adjusted Scale Score | PicSeq\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | The Picture Sequence Memory Test is a measure developed for the assessment of episodic memory for ages 3-85 years. It involves recalling increasingly lengthy series of illustrated objects and activities that are presented in a particular order on the computer screen. The participants are asked to recall the sequence of pictures that is demonstrated over two learning trials; sequence length varies from 6-18 pictures, depending on age. Participants are given credit for each adjacent pair of pictures (i.e., if pictures in locations 7 and 8 and placed in that order and adjacent to each other anywhere – such as slots 1 and 2 – one point is awarded) they correctly place, up to the maximum value for the sequence, which is one less than the sequence length (if there are 18 pictures in the sequence, the maximum score is 17, because that is the number of adjacent pairs of pictures that exist). The test takes approximately 7 minutes to administer. This test is recommended for ages 3-85. |

#### Instrument: Executive Function/Cognitive Flexibility (Dimensional Change Card Sort)

**Instrument Description:**


> DCCS is a measure of cognitive flexibility. Two target pictures are presented that vary along two dimensions (e.g., shape and color). Participants are asked to match a series of bivalent test pictures (e.g., yellow balls and blue trucks) to the target pictures, first according to one dimension (e.g., color) and then, after a number of trials, according to the other dimension (e.g., shape). "Switch" trials are also employed, in which the participant must change the dimension being matched. For example, after 4 straight trials matching on shape, the participant may be asked to match on color on the next trial and then go back to shape, thus requiring the cognitive flexibility to quickly choose the correct stimulus. Scoring is based on a combination of accuracy and reaction time, and the test takes approximately 4 minutes to administer. This test is recommended for ages 3-85.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Dimensional Change Card Sort Test: Unadjusted Scale Score | CardSort\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | DCCS is a measure of cognitive flexibility. Two target pictures are presented that vary along two dimensions (e.g., shape and color). Participants are asked to match a series of bivalent test pictures (e.g., yellow balls and blue trucks) to the target pictures, first according to one dimension (e.g., color) and then, after a number of trials, according to the other dimension (e.g., shape). “Switch” trials are also employed, in which the participant must change the dimension being matched. For example, after 4 straight trials matching on shape, the participant may be asked to match on color on the next trial and then go back to shape, thus requiring the cognitive flexibility to quickly choose the correct stimulus. Scoring is based on a combination of accuracy and reaction time, and the test takes approximately 4 minutes to administer. This test is recommended for ages 3-85. |
| NIH Toolbox Dimensional Change Card Sort Test: Age-Adjusted Scale Score | CardSort\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | DCCS is a measure of cognitive flexibility. Two target pictures are presented that vary along two dimensions (e.g., shape and color). Participants are asked to match a series of bivalent test pictures (e.g., yellow balls and blue trucks) to the target pictures, first according to one dimension (e.g., color) and then, after a number of trials, according to the other dimension (e.g., shape). “Switch” trials are also employed, in which the participant must change the dimension being matched. For example, after 4 straight trials matching on shape, the participant may be asked to match on color on the next trial and then go back to shape, thus requiring the cognitive flexibility to quickly choose the correct stimulus. Scoring is based on a combination of accuracy and reaction time, and the test takes approximately 4 minutes to administer. This test is recommended for ages 3-85. |

#### Instrument: Executive Function/Inhibition (Flanker Task)

**Instrument Description:**


> The Flanker task measures both a participant's attention and inhibitory control. The test requires the participant to focus on a given stimulus while inhibiting attention to stimuli (fish for ages 3-7 or arrows for ages 8-85) flanking it. Sometimes the middle stimulus is pointing in the same direction as the "flankers" (congruent) and sometimes in the opposite direction (incongruent). Scoring is based on a combination of accuracy and reaction time, and the test takes approximately 3 minutes to administer. This test is recommended for ages 3-85.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Flanker Inhibitory Control and Attention Test: Unadjusted Scale Score | Flanker\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | The Flanker task measures both a participant’s attention and inhibitory control. The test requires the participant to focus on a given stimulus while inhibiting attention to stimuli (fish for ages 3-7 or arrows for ages 8-85) flanking it. Sometimes the middle stimulus is pointing in the same direction as the “flankers” (congruent) and sometimes in the opposite direction (incongruent). Scoring is based on a combination of accuracy and reaction time, and the test takes approximately 3 minutes to administer. This test is recommended for ages 3-85. |
| NIH Toolbox Flanker Inhibitory Control and Attention Test: Age-Adjusted Scale Score | Flanker\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | The Flanker task measures both a participant’s attention and inhibitory control. The test requires the participant to focus on a given stimulus while inhibiting attention to stimuli (fish for ages 3-7 or arrows for ages 8-85) flanking it. Sometimes the middle stimulus is pointing in the same direction as the “flankers” (congruent) and sometimes in the opposite direction (incongruent). Scoring is based on a combination of accuracy and reaction time, and the test takes approximately 3 minutes to administer. This test is recommended for ages 3-85. |

#### Instrument: Fluid Intelligence (Penn Progressive Matrices)

**Instrument Description:**


> Fluid intelligence is measured using Raven’s Progressive Matrices (Prabhakaran et al. 1997; Christoff et al. 2001; Gray et al. 2003; Conway et al. 2005; Gray et al. 2005; Wendelken et al. 2008). We use Form A of an abbreviated version of the Raven’s developed by Gur and colleagues (Bilker et al. 2012). Participants are presented with patterns made up of 2x2, 3x3 or 1x5 arrangements of squares, with one of the squares missing. The participant must pick one of five response choices that best fits the missing square on the pattern. The task has 24 items and 3 bonus items, arranged in order of increasing difficulty. However, the task discontinues if the participant makes 5 incorrect responses in a row.
> 
> 1. [Duncan et al. 2000](http://www.ncbi.nlm.nih.gov/pubmed/10903207); [Duncan 2003](http://www.ncbi.nlm.nih.gov/pubmed/12601376); [Duncan 2005](http://www.ncbi.nlm.nih.gov/pubmed/15714904)
> 2. [Prabhakaran et al. 1997](http://www.ncbi.nlm.nih.gov/pubmed/9212721); [Christoff et al. 2001](http://www.ncbi.nlm.nih.gov/pubmed/11697945); [Gray et al. 2003](http://www.ncbi.nlm.nih.gov/pubmed/12592404); [Conway et al. 2005](http://www.ncbi.nlm.nih.gov/pubmed/16523997); [Gray et al. 2005](http://www.ncbi.nlm.nih.gov/pubmed/16180624); [Wendelken et al. 2008](http://www.ncbi.nlm.nih.gov/pubmed/18052787)
> 3. [Bilker et al. 2012](http://www.ncbi.nlm.nih.gov/pubmed/22605785)
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Penn Progressive Matrices: Number of Correct Responses (PMAT24\_A\_CR) | PMAT24\_A\_CR | Open | ^0\*([0-9]|1[0-9]|2[0-4])$ | =,NOT =,<,> | Penn Matrix Test: Number of Correct Responses |
| Penn Progressive Matrices: Total Skipped Items (PMAT24\_A\_SI) | PMAT24\_A\_SI | Open | ^0\*([0-9]|1[0-9])$ | =,NOT =,<,> | Penn Matrix Test: Total Skipped Items (items not presented because maximum errors allowed reached) |
| Penn Progressive Matrices: Median Reaction Time for Correct Responses (PMAT24\_A\_RTCR) | PMAT24\_A\_RTCR | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Penn Matrix Test: Median Reaction Time for Correct Responses |

#### Instrument: Language/Reading Decoding (Oral Reading Recognition)

**Instrument Description:**


> Separate but parallel reading tests have been developed in English and in Spanish. In either language, the participant is asked to read and pronounce letters and words as accurately as possible. The test administrator scores them as right or wrong. For the youngest children, the initial items require them to identify letters (as opposed to symbols) and to identify a specific letter in an array of 4 symbols. The test is given via a computerized adaptive format and requires approximately 3 minutes. This test is recommended for ages 7-85, but is available for use as young as age 3, if requested.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Oral Reading Recognition Test: Unadjusted Scale Score | ReadEng\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Separate but parallel reading tests have been developed in English and in Spanish. In either language, the participant is asked to read and pronounce letters and words as accurately as possible. The test administrator scores them as right or wrong. For the youngest children, the initial items require them to identify letters (as opposed to symbols) and to identify a specific letter in an array of 4 symbols. The test is given via a computerized adaptive format and requires approximately 3 minutes. This test is recommended for ages 7-85, but is available for use as young as age 3, if requested. |
| NIH Toolbox Oral Reading Recognition Test: Age-Adjusted Scale Score | ReadEng\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Separate but parallel reading tests have been developed in English and in Spanish. In either language, the participant is asked to read and pronounce letters and words as accurately as possible. The test administrator scores them as right or wrong. For the youngest children, the initial items require them to identify letters (as opposed to symbols) and to identify a specific letter in an array of 4 symbols. The test is given via a computerized adaptive format and requires approximately 3 minutes. This test is recommended for ages 7-85, but is available for use as young as age 3, if requested. |

#### Instrument: Language/Vocabulary Comprehension (Picture Vocabulary)

**Instrument Description:**


> This measure of receptive vocabulary is administered in a computerized adaptive format. The respondent is presented with an audio recording of a word and four photographic images on the computer screen and is asked to select the picture that most closely matches the meaning of the word. This test takes approximately 4 minutes to administer and is recommended for ages 3-85.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Picture Vocabulary Test: Unadjusted Scale Score | PicVocab\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This measure of receptive vocabulary is administered in a computerized adaptive format. The respondent is presented with an audio recording of a word and four photographic images on the computer screen and is asked to select the picture that most closely matches the meaning of the word. This test takes approximately 4 minutes to administer and is recommended for ages 3-85. |
| NIH Toolbox Picture Vocabulary Test: Age-Adjusted Scale Score | PicVocab\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This measure of receptive vocabulary is administered in a computerized adaptive format. The respondent is presented with an audio recording of a word and four photographic images on the computer screen and is asked to select the picture that most closely matches the meaning of the word. This test takes approximately 4 minutes to administer and is recommended for ages 3-85. |

#### Instrument: Processing Speed (Pattern Completion Processing Speed)

**Instrument Description:**


> This test measures speed of processing by asking participants to discern whether two side-by-side pictures are the same or not. Participants' raw score is the number of items correct in a 90-second period. The items are designed to be simple to most purely measure processing speed. The test overall takes approximately 3 minutes to administer. This test is recommended for ages 7-85, but is available for use as young as age 3, if requested.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Pattern Comparison Processing Speed Test: Unadjusted Scale Score | ProcSpeed\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This test measures speed of processing by asking participants to discern whether two side-by-side pictures are the same or not. Participants’ raw score is the number of items correct in a 90-second period. The items are designed to be simple to most purely measure processing speed. The test overall takes approximately 3 minutes to administer. This test is recommended for ages 7-85, but is available for use as young as age 3, if requested. |
| NIH Toolbox Pattern Comparison Processing Speed Test: Age-Adjusted Scale Score | ProcSpeed\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This test measures speed of processing by asking participants to discern whether two side-by-side pictures are the same or not. Participants’ raw score is the number of items correct in a 90-second period. The items are designed to be simple to most purely measure processing speed. The test overall takes approximately 3 minutes to administer. This test is recommended for ages 7-85, but is available for use as young as age 3, if requested. |

#### Instrument: Self-regulation/Impulsivity (Delay Discounting)

**Instrument Description:** 


> Delay discounting describes the undervaluing of rewards that are delayed in time. It is illustrated by the fact that humans (and other animals) will often choose a smaller immediate reward over an objectively larger, but delayed reward. We use a version of the discounting task that identifies ‘indifference points’ at which a person is equally likely to choose a smaller reward (e.g., $100) sooner versus a larger reward later (e.g., $200 in 3 years). Based on the work of Green and Myerson (Estle et al. 2006; Green et al. 2007), we use an adjusting-amount approach, in which delays are fixed and reward amounts are adjusted on a trial-by-trial basis based on participants’ choices, to rapidly hone in on indifference points. This approach has been repeatedly validated to provide reliable estimates of delay discounting (Estle et al. 2006). As a summary measure, we use an area-under-the-curve discounting measure (AUC) that provides a valid and reliable index of how steeply an individual discounts delayed rewards (Myerson et al. 2001).
> 
> 1. [Estle et al. 2006](http://www.ncbi.nlm.nih.gov/pubmed/17063921); [Green et al. 2007](http://www.ncbi.nlm.nih.gov/pubmed/17575900)
> 2. [Estle et al. 2006](http://www.ncbi.nlm.nih.gov/pubmed/17063921)
> 3. [Myerson et al. 2001](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1284836/)
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Delay Discounting: Subjective Value for $200 at 1 month (DDisc\_SV\_1mo\_200) | DDisc\_SV\_1mo\_200 | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $200 at 1 month |
| Delay Discounting: Subjective Value for $200 at 6 months (DDisc\_SV\_6mo\_200) | DDisc\_SV\_6mo\_200 | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $200 at 6 months |
| Delay Discounting: Subjective Value for $200 at 1 year (DDisc\_SV\_1yr\_200) | DDisc\_SV\_1yr\_200 | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $200 at 1 year |
| Delay Discounting: Subjective Value for $200 at 3 years (DDisc\_SV\_3yr\_200) | DDisc\_SV\_3yr\_200 | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $200 at 3 years |
| Delay Discounting: Subjective Value for $200 at 5 years (DDisc\_SV\_5yr\_200) | DDisc\_SV\_5yr\_200 | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $200 at 5 years |
| Delay Discounting: Subjective Value for $200 at 10 years (DDisc\_SV\_10yr\_200) | DDisc\_SV\_10yr\_200 | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $200 at 10 years |
| Delay Discounting: Subjective Value for $40K at 1 month (DDisc\_SV\_1mo\_40K) | DDisc\_SV\_1mo\_40K | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $40K at 1 month |
| Delay Discounting: Subjective Value for $40K at 6 months (DDisc\_SV\_6mo\_40K) | DDisc\_SV\_6mo\_40K | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $40K at 6 months |
| Delay Discounting: Subjective Value for $40K at 1 year (DDisc\_SV\_1yr\_40K) | DDisc\_SV\_1yr\_40K | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $40K at 1 year |
| Delay Discounting: Subjective Value for $40K at 3 years (DDisc\_SV\_3yr\_40K) | DDisc\_SV\_3yr\_40K | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $40K at 3 years |
| Delay Discounting: Subjective Value for $40K at 5 years (DDisc\_SV\_5yr\_40K) | DDisc\_SV\_5yr\_40K | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $40K at 5 years |
| Delay Discounting: Subjective Value for $40K at 10 years (DDisc\_SV\_10yr\_40K) | DDisc\_SV\_10yr\_40K | Open | ^[0-9]\*[.][0-9][0-9]$ | =,NOT =,<,> | Subjective Value for $40K at 10 years |
| Delay Discounting: Area Under the Curve for Discounting of $200 (DDisc\_AUC\_200) | DDisc\_AUC\_200 | Open | ^(([1][.][0]+)|([0]([.][0-9]+)?)|([.][0-9]+))$ | =,NOT =,<,> | Area Under the Curve for Discounting of $200 |
| Delay Discounting: Area Under the Curve for Discounting of $40,000 (DDisc\_AUC\_40K) | DDisc\_AUC\_40K | Open | ^(([1][.][0]+)|([0]([.][0-9]+)?)|([.][0-9]+))$ | =,NOT =,<,> | Area Under the Curve for Discounting of $40,000 |

#### Instrument: Spatial Orientation (Variable Short Penn Line Orientation Test)

**Instrument Description:**


> Spatial orientation processing is measured using the Variable Short Penn Line Orientation Test (Gur et al. 2001a; Gur et al. 2010). Participants are shown two lines with different orientations. They have to rotate one of the lines (a moveable blue one) so that is parallel to the other line (a fixed red line). The rotation of the blue line is accomplished by clicking buttons on the keyboard that rotate the lines either clockwise or counterclockwise. Across trials, the lines vary in their relative location on the screen, though the distance between the centers of the two lines is always the same. The length of the red line is always the same, but the length of the blue line can be either short or long. There are a total of 24 trials
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Variable Short Penn Line Orientation: Total Number Correct (VSPLOT\_TC) | VSPLOT\_TC | Open | ^([0-9]|1[0-9]|2[0-4])$ | =,NOT =,<,> | Penn Line Orientation: Total Number Correct |
| Variable Short Penn Line Orientation: Median Reaction Time Divided by Expected Number of Clicks for Correct (VSPLOT\_CRTE) | VSPLOT\_CRTE | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Penn Line Orientation: Median Reaction Time Divided by Expected Number of Clicks for Correct Trials |
| Variable Short Penn Line Orientation: Total Positions Off for All Trials (VSPLOT\_OFF) | VSPLOT\_OFF | Open | ^([0-9]{1,2}|1[0-5][0-9]|16[0-5])$ | =,NOT =,<,> | Penn Line Orientation:  Total Positions Off for All Trials |

#### Instrument: Sustained Attention (Short Penn Continuous Performance Test)

**Instrument Description:**


> Continuous sustained attention is measured using the Short Penn Continuous Performance Test (Number/Letter Version) (Gur et al. 2001; Gur et al. 2001; Gur et al. 2010). Participants see vertical and horizontal red lines flash on the computer screen. In one block, they must press the spacebar when the lines form a number and in the other block they press the spacebar when the lines form a letter. The lines are displayed for 300 ms followed by a 700 ms ITI. Each block contains 90 stimuli and lasts for 1.5 minutes.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Short Penn Continuous Performance Test: True Positives = Sum of CPN\_TP and CPL\_TP  (SCPT\_TP) | SCPT\_TP | Open | ^[0-9]+$ | =,NOT =,<,> | Short Penn CPT True Positives = Sum of CPN\_TP and CPL\_TP |
| Short Penn Continuous Performance Test: True Negatives = Sum of CPN\_TN and CPL\_TPN  (SCPT\_TN ) | SCPT\_TN | Open | ^[0-9]+$ | =,NOT =,<,> | Short Penn CPT True Negatives = Sum of CPN\_TN and CPL\_TPN |
| Short Penn Continuous Performance Test: Open Positives = Sum of CPN\_FP and CPL\_FP  (SCPT\_FP) | SCPT\_FP | Open | ^[0-9]+$ | =,NOT =,<,> | Short Penn CPT Open Positives = Sum of CPN\_FP and CPL\_FP |
| Short Penn Continuous Performance Test: Open Negatives = Sum of CPN\_FN and CPL\_FN  (SCPT\_FN) | SCPT\_FN | Open | ^[0-9]+$ | =,NOT =,<,> | Short Penn CPT Open Negatives = Sum of CPN\_FN and CPL\_FN |
| Short Penn Continuous Performance Test: Median Response Time for True Positive Responses  (SCPT\_TPRT) | SCPT\_TPRT | Open | ^[0-9]+$ | =,NOT =,<,> | Short Penn CPT Median Response Time for True Positive Responses |
| Short Penn Continuous Performance Test: Sensitivity = SCPT\_TP/(SCPT\_TP + SCPT\_FN  (SCPT\_SEN) | SCPT\_SEN | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Short Penn CPT Sensitivity = SCPT\_TP/(SCPT\_TP + SCPT\_FN) |
| Short Penn Continuous Performance Test: Specificity = SCPT\_TN/(SCPT\_TN + SCPT\_FP)  (SCPT\_SPEC) | SCPT\_SPEC | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Short Penn CPT Specificity = SCPT\_TN/(SCPT\_TN + SCPT\_FP) |
| Short Penn Continuous Performance Test: Longest Run of Non-Responses (SCPT\_LRNR) | SCPT\_LRNR | Open | ^[0-9]+$ | =,NOT =,<,> | Short Penn CPT Longest Run of Non-Responses) |

#### Instrument: Verbal Episodic Memory (Penn Word Memory Test)

**Instrument Description:**


> Verbal episodic memory is measured using Form A of the Penn Word Memory Test (Gur et al. 2001a; Gur et al. 2010). Participants are shown 20 words and asked to remember them for a subsequent memory test. They are then shown 40 words (the 20 previously presented words and 20 new words matched on memory related characteristics). They decide whether they have seen the word previously by choosing among “definitely yes,” “probably yes,” “probably no,” and “definitely no.”
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Penn Word Memory Test:  Total Number of Correct Responses (IWRD\_TOT) | IWRD\_TOT | Open | ^[0-9]+$ | =,NOT =,<,> | Penn Word Memory:  Total Number of Correct Responses |
| Penn Word Memory Test:  Median Reaction Time for Correct Responses (IWRD\_RTC) | IWRD\_RTC | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Penn Word Memory:  Median Reaction Time for Correct Responses |

#### Instrument: Working Memory (List Sorting)

**Instrument Description:**


> This task assesses working memory and requires the participant to sequence different visually- and orally-presented stimuli. Pictures of different foods and animals are displayed with both a sound clip and written text that name the item. The task has two different conditions: 1-List and 2-List. In the 1-List condition, participants are required to order a series of objects (either food or animals) in size order from smallest to largest. In the 2-List condition, participants are presented both food and animals and are asked to report the food in size order, followed by the animals in size order. Children ages 3-6 have four practice items in each condition: two practice items in which the images appear simultaneously on the screen and two practice items in which the images briefly "flash" sequentially on the screen. Participants ages 7-85 have two practice items, both "flashing" in each condition. Different instructions are provided for 3-6 and 7-85 year olds in English and for 3-6, 7-17 and 18-85 year olds in Spanish.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox List Sorting Working Memory Test: Unadjusted Scale Score | ListSort\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This task assesses working memory and requires the participant to sequence different visually- and orally-presented stimuli. Pictures of different foods and animals are displayed with both a sound clip and written text that name the item. The task has two different conditions: 1-List and 2-List. In the 1-List condition, participants are required to order a series of objects (either food or animals) in size order from smallest to largest. In the 2-List condition, participants are presented both food and animals and are asked to report the food in size order, followed by the animals in size order. Children ages 3-6 have four practice items in each condition: two practice items in which the images appear simultaneously on the screen and two practice items in which the images briefly “flash” sequentially on the screen. Participants ages 7-85 have two practice items, both “flashing” in each condition. Different instructions are provided for 3-6 and 7-85 year olds in English and for 3-6, 7-17 and 18-85 year olds in Spanish. |
| NIH Toolbox List Sorting Working Memory Test: Age-Adjusted Scale Score | ListSort\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This task assesses working memory and requires the participant to sequence different visually- and orally-presented stimuli. Pictures of different foods and animals are displayed with both a sound clip and written text that name the item. The task has two different conditions: 1-List and 2-List. In the 1-List condition, participants are required to order a series of objects (either food or animals) in size order from smallest to largest. In the 2-List condition, participants are presented both food and animals and are asked to report the food in size order, followed by the animals in size order. Children ages 3-6 have four practice items in each condition: two practice items in which the images appear simultaneously on the screen and two practice items in which the images briefly “flash” sequentially on the screen. Participants ages 7-85 have two practice items, both “flashing” in each condition. Different instructions are provided for 3-6 and 7-85 year olds in English and for 3-6, 7-17 and 18-85 year olds in Spanish. |

  


  


### Category: Emotion

#### Instrument: Emotion Recognition (Penn Emotion Recognition Test)

**Instrument Description:**


> Emotion processing is measured using the Penn Emotion Recognition Test (Gur et al. 2001a; Gur et al. 2010). Participants are presented with 40 faces, one at a time. They are asked to choose what emotion the face is showing from five choices: Happy, Sad, Angry, Scared and No Feeling. Half of the faces are males and half are females. There are 8 faces each that have a happy, sad, angry, scared or no feeling expression.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Penn Emotion Recognition Test: Number of Correct Responses (ER40\_CR) | ER40\_CR | Open | ^([0-9]|[1-3][0-9]|40)$ | =,NOT =,<,> | Penn Emotion Recognition: Number of Correct Responses |
| Penn Emotion Recognition Test: Correct Responses Median Response Time (ms) (ER40\_CRT) | ER40\_CRT | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Penn Emotion Recognition: Correct Responses Median Response Time (ms) |
| Penn Emotion Recognition Test: Number of Correct Anger Identifications (ER40ANG) | ER40ANG | Open | ^[0-8]$ | =,NOT =,<,> | Penn Emotion Recognition: Number of Correct Anger Identifications |
| Penn Emotion Recognition Test: Number of Correct Fear Identifications (ER40FEAR) | ER40FEAR | Open | ^[0-8]$ | =,NOT =,<,> | Penn Emotion Recognition: Number of Correct Fear Identifications |
| Penn Emotion Recognition Test: Number of Correct Happy Identifications (ER40HAP) | ER40HAP | Open | ^[0-8]$ | =,NOT =,<,> | Penn Emotion Recognition: Number of Correct Happy Identifications |
| Penn Emotion Recognition Test: Number of Correct Neutral Identifications (ER40NOE) | ER40NOE | Open | ^[0-8]$ | =,NOT =,<,> | Penn Emotion Recognition: Number of Correct Neutral Identifications |
| Penn Emotion Recognition Test: Number of Correct Sad Identifications (ER40SAD) | ER40SAD | Open | ^[0-8]$ | =,NOT =,<,> | Penn Emotion Recognition: Number of Correct Sad Identifications |

#### Instrument: Negative Affect

**Instrument Description:**


> (Sadness, Fear, Anger)
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Anger-Affect Survey: Unadjusted Scale Score | AngAffect\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Anger is a concept within the Negative Affect subdomain of Emotion. Anger is characterized by attitudes of hostility and cynicism and is often associated with experiences of frustration impeding goal-directed behavior. For adult self-report (ages 18 and above), Anger is comprised of three components:  anger as an emotion, aggression as a behavioral component, and hostility as a set of cynical attitudes and mistrust of others and their motives. The NIH Toolbox Anger-Affect Survey is a computer-adaptive test (CAT) comprised of items from the PROMIS Anger Item Bank. It assesses anger as an emotion. |
| NIH Toolbox Anger-Hostility Survey: Unadjusted Scale Score | AngHostil\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Anger is a concept within the Negative Affect subdomain of Emotion. Anger is characterized by attitudes of hostility and cynicism and is often associated with experiences of frustration impeding goal-directed behavior. For adult self-report (ages 18 and above), Anger is comprised of three components:  anger as an emotion, aggression as a behavioral component, and hostility as a set of cynical attitudes and mistrust of others and their motives. The NIH Toolbox Anger-Affect Survey is a computer-adaptive test (CAT) comprised of items from the PROMIS Anger Item Bank. It assesses anger as an emotion. |
| NIH Toolbox Anger-Physical Aggression Survey: Unadjusted Scale Score | AngAggr\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Anger is a concept within the Negative Affect subdomain of Emotion. Anger is characterized by attitudes of hostility and cynicism and is often associated with experiences of frustration impeding goal-directed behavior. For adult self-report (ages 18 and above), Anger is comprised of three components:  anger as an emotion, aggression as a behavioral component, and hostility as a set of cynical attitudes and mistrust of others and their motives. The NIH Toolbox Anger-Affect Survey is a computer-adaptive test (CAT) comprised of items from the PROMIS Anger Item Bank. It assesses anger as an emotion. |
| NIH Toolbox Fear-Affect Survey: Unadjusted Scale Score | FearAffect\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Fear is a concept within the Negative Affect subdomain of Emotion. Fear is best characterized by symptoms of anxiety that reflect autonomic arousal and perceptions of threat. The NIH Toolbox Fear-Affect Survey is a CAT comprised of items from the PROMIS Anxiety Item Bank. It assesses self-reported fear and anxious misery. |
| NIH Toolbox Fear-Somatic Arousal Survey: Unadjusted Scale Score | FearSomat\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Fear is a concept within the Negative Affect subdomain of Emotion. Fear is best characterized by symptoms of anxiety that reflect autonomic arousal and perceptions of threat. The NIH Toolbox Fear-Somatic Arousal Survey is a 6-item calibrated scale comprised of items from the Mood and Anxiety Symptom Questionnaire. It assesses somatic symptoms related to arousal. |
| NIH Toolbox Sadness Survey: Unadjusted Scale Score | Sadness\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Sadness is a concept within the Negative Affect subdomain of Emotion. Sadness is distinguished by low levels of positive affect and comprised of symptoms that are primarily affective (poor mood) and cognitive (negative perceptions of self, the world, and the future) indicators of depression. The NIH Toolbox Sadness Survey is a CAT comprised of items from the PROMIS Depression Item Bank. |

#### Instrument: Psychological Well-being

**Instrument Description:**


> (Positive Affect, Life Satisfaction, Meaning and Purpose)
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox General Life Satisfaction Survey: Unadjusted Scale Score | LifeSatisf\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Life Satisfaction is a concept within the Psychological Well-Being subdomain of Emotion. Life Satisfaction is one's cognitive evaluation of life experiences and is concerned with whether people like their lives or not. Life satisfaction includes both general (e.g., my life is going well) and domain-specific (e.g., I am satisfied with my family life) aspects. This self-report measure for adults (ages 18 and above) is a 10-item calibrated scale comprised of items from the Satisfaction with Life Scale  and the Students' Life Satisfaction Scale.  It assesses global feelings and attitudes about one's life. |
| NIH Toolbox Meaning and Purpose Survey: Unadjusted Scale Score | MeanPurp\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Meaning and Purpose is a concept within the Psychological Well-Being subdomain of Emotion. Meaning and Purpose is characterized by the extent to which people feel their life matters or makes sense. This self-report measure for adults (ages 18 and above) is a CAT comprised of items from the Meaning in Life Questionnaire, the Life Engagement Test, the MHI, and the FACIT-Sp. |
| NIH Toolbox Positive Affect Survey: Unadjusted Scale Score | PosAffect\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Positive Affect is a concept within the Psychological Well-Being subdomain of Emotion. Positive Affect can be described as feelings that reflect a level of pleasurable engagement with the environment such as happiness, joy, excitement, enthusiasm, and contentment. This parent-report measure (for children ages 8-12) is a CAT comprised of items from the PANAS-X. It assesses both activated (i.e., happiness, joy) as well as unactivated (i.e., serenity, peace) aspects of positive affect. |

#### Instrument: Social Relationships

**Instrument Description:**


> (Social Support, Companionship, Social Distress, Positive Social Development)
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Friendship Survey: Unadjusted Scale Score | Friendship\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Companionship is a concept within the Social Relationships subdomain of Emotion. Companionship is characterized by self-reported perceptions of the availability of friends or companions with whom to interact or affiliate (i.e., friendship) and that one is alone, lonely or socially isolated from others (i.e., loneliness).  The NIH Toolbox Friendship Survey is a self-report measure for adults (ages 18 and above) comprised of 5 calibrated items. |
| NIH Toolbox Loneliness Survey: Unadjusted Scale Score | Loneliness\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Companionship is a concept within the Social Relationships subdomain of Emotion. Companionship is characterized by self-reported perceptions of the availability of friends or companions with whom to interact or affiliate (i.e., friendship) and that one is alone, lonely or socially isolated from others (i.e., loneliness).  The NIH Toolbox Loneliness Survey is a self-report measure for adults (ages 18 and above) comprised of 8 calibrated items. |
| NIH Toolbox Perceived Hostility Survey: Unadjusted Scale Score | PercHostil\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Social Distress is a concept within the Social Relationships subdomain of Emotion. Social distress is the extent to which an individual perceives his/her daily social interactions as negative or distressing.  This can include aspects of perceived hostility (e.g., how often people argue with me, yell at me, or criticize me) and perceived rejection (e.g., how often people don't listen when I ask for help, or don't pay attention to me). The NIH Toolbox Perceived Hostility Survey is a self-report measure for children and adolescents (ages 8-17) comprised of 5 calibrated items. |
| NIH Toolbox Perceived Rejection Survey: Unadjusted Scale Score | PercReject\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Social Distress is a concept within the Social Relationships subdomain of Emotion. Social distress is the extent to which an individual perceives his/her daily social interactions as negative or distressing.  This can include aspects of perceived hostility (e.g., how often people argue with me, yell at me, or criticize me) and perceived rejection (e.g., how often people don't listen when I ask for help, or don't pay attention to me). The NIH Toolbox Perceived Rejection Survey is a self-report measure for children and adolescents (ages 8-17) comprised of 5 calibrated items. |
| NIH Toolbox Emotional Support Survey: Unadjusted Scale Score | EmotSupp\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Social Support is a concept within the Social Relationships subdomain of Emotion. Perceived social support is the extent to which an individual views his/her social relationships as available to provide aid in times of need or when problems arise (Cohen, 2004).   This includes emotional/informational types of perceived social support for children and adolescents. Emotional Support refers to the perception that people in one's social network are available to listen to one's problems with empathy, caring and understanding, and Informational Support refers to the perception that people in one's social network are available to provide information or advice needed to solve problems that arise.  This self-report measure for children and adolescents (ages 8-17) is a 7-item calibrated scale. |
| NIH Toolbox Instrumental Support Survey: Unadjusted Scale Score | InstruSupp\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Social Support is a concept within the Social Relationships subdomain of Emotion. Perceived social support is the extent to which an individual views his/her social relationships as available to provide aid in times of need or when problems arise. This includes instrumental and emotional/informational types of perceived social support. Instrumental Support refers to the perception that people in one's social network are available to provide material or functional aid in completing daily tasks (such as making meals or providing transportation) if needed. This self-report measure for adults (ages 18 and above) is an 8-item calibrated scale. |

#### Instrument: Stress and Self Efficacy

**Instrument Description:**


> Perceived Stress and Self Efficacy
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Perceived Stress Survey: Unadjusted Scale Score | PercStress\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Perceived Stress is a concept within the Stress & Self-Efficacy subdomain of Emotion. Perceived Stress is defined by individual perceptions about the nature of events and their relationship to the values and coping resources of an individual. This self-report measure for adults (ages 18 and above) is a CAT comprised of items from the Perceived Stress Scale-10. . It assesses how unpredictable, uncontrollable, and overloading respondents find their lives. |
| NIH Toolbox Self-Efficacy Survey: Unadjusted Scale Score | SelfEff\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Self-Efficacy is a concept within the Stress & Self-Efficacy subdomain of Emotion. Self-Efficacy can be described as a person's belief in their capacity to manage their functioning and have control over meaningful events. This self-report measure for adults (ages 18 and above) is a CAT comprised of items modified from the General Self-Efficacy Scale (Schwarzer). It assesses respondents' sense of global self-efficacy. |

### Category: FreeSurfer

#### Instrument: FreeSurfer Summary Statistics



| Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Left hemisphere cortical gray matter volume | FS\_LCort\_GM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Right hemisphere cortical gray matter volume | FS\_RCort\_GM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Total cortical gray matter volume | FS\_TotCort\_GM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Total subcortical gray matter volume | FS\_SubCort\_GM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Total gray matter volume | FS\_Total\_GM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Supratentorial volume | FS\_SupraTentorial\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Left hemisphere cortical white matter volume | FS\_L\_WM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Right hemisphere cortical white matter volume | FS\_R\_WM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Total cortical white matter volume | FS\_Tot\_WM\_Vol | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Volume (Subcortical) Segmentation



| Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Left-Lateral-Ventricle Volume | FS\_L\_LatVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Lateral_ventricle>\">Lateral\_ventricle</a> |
| Left-Inf-Lat-Vent Volume | FS\_L\_InfLatVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Inferior_horn_of_the_lateral_ventricle>\">Inferior\_horn\_of\_the\_lateral\_ventricle</a> |
| Left-Cerebellum-White-Matter Volume | FS\_L\_Cerebellum\_WM\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Cerebellum>\">Cerebellum</a> |
| Left-Cerebellum-Cortex Volume | FS\_L\_Cerebellum\_Cort\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Cerebellar_cortex>\">Cerebellar\_cortex</a> |
| Left-Thalamus-Proper Volume | FS\_L\_ThalamusProper\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Thalamus>\">Thalamus</a> |
| Left-Caudate Volume | FS\_L\_Caudate\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Caudate_nucleus>\">Caudate\_nucleus</a> |
| Left-Putamen Volume | FS\_L\_Putamen\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Putamen>\">Putamen</a> |
| Left-Pallidum Volume | FS\_L\_Pallidum\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Globus_pallidus>\">Globus\_pallidus</a> |
| 3rd-Ventricle Volume | FS\_3rdVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Third_ventricle>\">Third\_ventricle</a> |
| 4th-Ventricle Volume | FS\_4thVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Fourth_ventricle>\">Fourth\_ventricle</a> |
| Brain-Stem Volume | FS\_BrainStem\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Brainstem>\">Brainstem</a> |
| Left-Hippocampus Volume | FS\_L\_Hippo\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Hippocampus>\">Hippocampus</a> |
| Left-Amygdala Volume | FS\_L\_Amygdala\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Amygdala>\">Amygdala</a> |
| CSF Volume | FS\_CSF\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Cerebral_Spinal_Fluid>\">Cerebral\_Spinal\_Fluid</a> |
| Left-Accumbens-area Volume | FS\_L\_AccumbensArea\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Nucleus_accumbens>\">Nucleus\_accumbens</a> |
| Left-VentralDC Volume | FS\_L\_VentDC\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Ventral_diencephalon>\">Ventral\_diencephalon</a> |
| Left-vessel Volume | FS\_L\_Vessel\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Left-choroid-plexus Volume | FS\_L\_ChoroidPlexus\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Choroid_plexus>\">Choroid\_plexus</a> |
| Right-Lateral-Ventricle Volume | FS\_R\_LatVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Lateral_ventricle>\">Lateral\_ventricle</a> |
| Right-Inf-Lat-Vent Volume | FS\_R\_InfLatVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Inferior_horn_of_the_lateral_ventricle>\">Inferior\_horn\_of\_the\_lateral\_ventricle</a> |
| Right-Cerebellum-White-Matter Volume | FS\_R\_Cerebellum\_WM\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Cerebellum>\">Cerebellum</a> |
| Right-Cerebellum-Cortex Volume | FS\_R\_Cerebellum\_Cort\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Cerebellar_cortex>\">Cerebellar\_cortex</a> |
| Right-Thalamus-Proper Volume | FS\_R\_ThalamusProper\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Thalamus>\">Thalamus</a> |
| Right-Caudate Volume | FS\_R\_Caudate\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Caudate_nucleus>\">Caudate\_nucleus</a> |
| Right-Putamen Volume | FS\_R\_Putamen\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Putamen>\">Putamen</a> |
| Right-Pallidum Volume | FS\_R\_Pallidum\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Globus_pallidus>\">Globus\_pallidus</a> |
| Right-Hippocampus Volume | FS\_R\_Hippo\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Hippocampus>\">Hippocampus</a> |
| Right-Amygdala Volume | FS\_R\_Amygdala\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Amygdala>\">Amygdala</a> |
| Right-Accumbens-area Volume | FS\_R\_AccumbensArea\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Nucleus_accumbens>\">Nucleus\_accumbens</a> |
| Right-VentralDC Volume | FS\_R\_VentDC\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Ventral_diencephalon>\">Ventral\_diencephalon</a> |
| Right-vessel Volume | FS\_R\_Vessel\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Right-choroid-plexus Volume | FS\_R\_ChoroidPlexus\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Choroid_plexus>\">Choroid\_plexus</a> |
| 5th-Ventricle Volume | FS\_5thVent\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Septum_pellucidum>\">Septum\_pellucidum</a> |
| WM-hypointensities Volume | FS\_WM\_Hypointens\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Non-WM-hypointensities Volume | FS\_Non-WM\_Hypointens\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Left-WM-hypointensities Volume | FS\_L\_WM\_Hypointens\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Right-WM-hypointensities Volume | FS\_R\_WM\_Hypointens\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Left-non-WM-hypointensities Volume | FS\_L\_Non-WM\_Hypointens\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Right-non-WM-hypointensities Volume | FS\_R\_Non-WM\_Hypointens\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Optic-Chiasm Volume | FS\_OpticChiasm\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Optic_chiasm>\">Optic\_chiasm</a> |
| CC\_Posterior Volume | FS\_CC\_Posterior\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Corpus_callosum>\">Corpus\_callosum</a> |
| CC\_Mid\_Posterior Volume | FS\_CC\_MidPosterior\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Corpus_callosum>\">Corpus\_callosum</a> |
| CC\_Central Volume | FS\_CC\_Central\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Corpus_callosum>\">Corpus\_callosum</a> |
| CC\_Mid\_Anterior Volume | FS\_CC\_MidAnterior\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Corpus_callosum>\">Corpus\_callosum</a> |
| CC\_Anterior Volume | FS\_CC\_Anterior\_Vol | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition:  <a href=\"<http://neurolex.org/wiki/Category:Corpus_callosum>\">Corpus\_callosum</a> |

#### Instrument: Surface Area



| Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Left bankssts Surface Area | FS\_L\_Bankssts\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Banks_of_superior_temporal_sulcus>\">Banks of the Superior Temporal Sulcus</a> |
| Left caudalanteriorcingulate Surface Area | FS\_L\_Caudalanteriorcingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_anterior_cingulate_cortex>\">Caudal Anterior Cingulate Cortex</a> |
| Left caudalmiddlefrontal Surface Area | FS\_L\_Caudalmiddlefrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_middle_frontal_gyrus>\">Caudal Middle Frontal Gyrus</a> |
| Left cuneus Surface Area | FS\_L\_Cuneus\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Cuneus_cortex>\">Cuneus Cortex</a> |
| Left entorhinal Surface Area | FS\_L\_Entorhinal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Entorhinal_cortex>\">Entorhinal Cortex</a> |
| Left fusiform Surface Area | FS\_L\_Fusiform\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Fusiform_gyrus>\">Fusiform Gyrus</a> |
| Left inferiorparietal Surface Area | FS\_L\_Inferiorparietal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_parietal_cortex>\">Inferior Parietal Cortex </a> |
| Left inferiortemporal Surface Area | FS\_L\_Inferiortemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_temporal_gyrus>\">Inferior Temporal Gyrus</a> |
| Left isthmuscingulate Surface Area | FS\_L\_Isthmuscingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Isthmus_of_cingulate_gyrus>\">Isthmus Cingulate Gyrus</a> |
| Left lateraloccipital Surface Area | FS\_L\_Lateraloccipital\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_occipital_cortex>\">Lateral Occipital Cortex</a> |
| Left lateralorbitofrontal Surface Area | FS\_L\_Lateralorbitofrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_orbital_frontal_cortex>\">Lateral Orbital Frontal Cortex</a> |
| Left lingual Surface Area | FS\_L\_Lingual\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lingual_gyrus>\">Lingual Gyrus</a> |
| Left medialorbitofrontal Surface Area | FS\_L\_Medialorbitofrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Medial_orbital_frontal_cortex>\">Medial Orbital Frontal Cortex</a> |
| Left middletemporal Surface Area | FS\_L\_Middletemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Middle_temporal_gyrus>\">Middle Temporal Gyrus</a> |
| Left parahippocampal Surface Area | FS\_L\_Parahippocampal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Parahippocampal_gyrus>\">Parahippocampal Gyrus</a> |
| Left paracentral Surface Area | FS\_L\_Paracentral\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Paracentral_sulcus>\">Paracentral Sulcus</a> |
| Left parsopercularis Surface Area | FS\_L\_Parsopercularis\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Opercular_part_of_inferior_frontal_gyrus>\">Opercular Part of Inferior Frontal Gyrus</a> |
| Left parsorbitalis Surface Area | FS\_L\_Parsorbitalis\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Orbital_part_of_inferior_frontal_gyrus>\">Orbital Part of Inferior Frontal Gyrus</a> |
| Left parstriangularis Surface Area | FS\_L\_Parstriangularis\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Triangular_part_of_inferior_frontal_gyrus>\">Triangular Part of Inferior Frontal Gyrus</a> |
| Left pericalcarine Surface Area | FS\_L\_Pericalcarine\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Pericalcarine_cortex>\">Pericalcarine Cortex</a> |
| Left postcentral Surface Area | FS\_L\_Postcentral\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Postcentral_gyrus>\">Postcentral Gyrus</a> |
| Left posteriorcingulate Surface Area | FS\_L\_Posteriorcingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Posterior_cingulate_gyrus>\">Posterior Cingulate Gyrus</a> |
| Left precentral Surface Area | FS\_L\_Precentral\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precentral_gyrus>\">Precentral Gyrus</a> |
| Left precuneus Surface Area | FS\_L\_Precuneus\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precuneus_cortex>\">Precuneus Cortex</a> |
| Left rostralanteriorcingulate Surface Area | FS\_L\_Rostralanteriorcingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_anterior_cingulate_cortex>\">Rostral Anterior Cingulate Cortex</a> |
| Left rostralmiddlefrontal Surface Area | FS\_L\_Rostralmiddlefrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_middle_frontal_gyrus>\">Rostral Middle Frontal Gyrus</a> |
| Left superiorfrontal Surface Area | FS\_L\_Superiorfrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_frontal_gyrus>\">Superior Frontal Gyrus</a> |
| Left superiorparietal Surface Area | FS\_L\_Superiorparietal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_parietal_cortex>\">Superior Parietal Cortex </a> |
| Left superiortemporal Surface Area | FS\_L\_Superiortemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_temporal_gyrus>\">Superior Temporal Gyrus</a> |
| Left supramarginal Surface Area | FS\_L\_Supramarginal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Supramarginal_gyrus>\">Supramarginal Gyrus</a> |
| Left frontalpole Surface Area | FS\_L\_Frontalpole\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Frontal_pole>\">Frontal Pole</a> |
| Left temporalpole Surface Area | FS\_L\_Temporalpole\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Temporal_pole>\">Temporal Pole</a> |
| Left transversetemporal Surface Area | FS\_L\_Transversetemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Transverse_temporal_cortex>\">Transverse Temporal Cortex</a> |
| Left insula Surface Area | FS\_L\_Insula\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Insula>\">Insula</a> |
| Right bankssts Surface Area | FS\_R\_Bankssts\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Banks_of_superior_temporal_sulcus>\">Banks of the Superior Temporal Sulcus</a> |
| Right caudalanteriorcingulate Surface Area | FS\_R\_Caudalanteriorcingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_anterior_cingulate_cortex>\">Caudal Anterior Cingulate Cortex</a> |
| Right caudalmiddlefrontal Surface Area | FS\_R\_Caudalmiddlefrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_middle_frontal_gyrus>\">Caudal Middle Frontal Gyrus</a> |
| Right cuneus Surface Area | FS\_R\_Cuneus\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Cuneus_cortex>\">Cuneus Cortex</a> |
| Right entorhinal Surface Area | FS\_R\_Entorhinal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Entorhinal_cortex>\">Entorhinal Cortex</a> |
| Right fusiform Surface Area | FS\_R\_Fusiform\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Fusiform_gyrus>\">Fusiform Gyrus</a> |
| Right inferiorparietal Surface Area | FS\_R\_Inferiorparietal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_parietal_cortex>\">Inferior Parietal Cortex </a> |
| Right inferiortemporal Surface Area | FS\_R\_Inferiortemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_temporal_gyrus>\">Inferior Temporal Gyrus</a> |
| Right isthmuscingulate Surface Area | FS\_R\_Isthmuscingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Isthmus_of_cingulate_gyrus>\">Isthmus Cingulate Gyrus</a> |
| Right lateraloccipital Surface Area | FS\_R\_Lateraloccipital\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_occipital_cortex>\">Lateral Occipital Cortex</a> |
| Right lateralorbitofrontal Surface Area | FS\_R\_Lateralorbitofrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_orbital_frontal_cortex>\">Lateral Orbital Frontal Cortex</a> |
| Right lingual Surface Area | FS\_R\_Lingual\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lingual_gyrus>\">Lingual Gyrus</a> |
| Right medialorbitofrontal Surface Area | FS\_R\_Medialorbitofrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Medial_orbital_frontal_cortex>\">Medial Orbital Frontal Cortex</a> |
| Right middletemporal Surface Area | FS\_R\_Middletemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Middle_temporal_gyrus>\">Middle Temporal Gyrus</a> |
| Right parahippocampal Surface Area | FS\_R\_Parahippocampal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Parahippocampal_gyrus>\">Parahippocampal Gyrus</a> |
| Right paracentral Surface Area | FS\_R\_Paracentral\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Paracentral_sulcus>\">Paracentral Sulcus</a> |
| Right parsopercularis Surface Area | FS\_R\_Parsopercularis\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Opercular_part_of_inferior_frontal_gyrus>\">Opercular Part of Inferior Frontal Gyrus</a> |
| Right parsorbitalis Surface Area | FS\_R\_Parsorbitalis\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Orbital_part_of_inferior_frontal_gyrus>\">Orbital Part of Inferior Frontal Gyrus</a> |
| Right parstriangularis Surface Area | FS\_R\_Parstriangularis\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Triangular_part_of_inferior_frontal_gyrus>\">Triangular Part of Inferior Frontal Gyrus</a> |
| Right pericalcarine Surface Area | FS\_R\_Pericalcarine\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Pericalcarine_cortex>\">Pericalcarine Cortex</a> |
| Right postcentral Surface Area | FS\_R\_Postcentral\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Postcentral_gyrus>\">Postcentral Gyrus</a> |
| Right posteriorcingulate Surface Area | FS\_R\_Posteriorcingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Posterior_cingulate_gyrus>\">Posterior Cingulate Gyrus</a> |
| Right precentral Surface Area | FS\_R\_Precentral\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precentral_gyrus>\">Precentral Gyrus</a> |
| Right precuneus Surface Area | FS\_R\_Precuneus\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precuneus_cortex>\">Precuneus Cortex</a> |
| Right rostralanteriorcingulate Surface Area | FS\_R\_Rostralanteriorcingulate\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_anterior_cingulate_cortex>\">Rostral Anterior Cingulate Cortex</a> |
| Right rostralmiddlefrontal Surface Area | FS\_R\_Rostralmiddlefrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_middle_frontal_gyrus>\">Rostral Middle Frontal Gyrus</a> |
| Right superiorfrontal Surface Area | FS\_R\_Superiorfrontal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_frontal_gyrus>\">Superior Frontal Gyrus</a> |
| Right superiorparietal Surface Area | FS\_R\_Superiorparietal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_parietal_cortex>\">Superior Parietal Cortex </a> |
| Right superiortemporal Surface Area | FS\_R\_Superiortemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_temporal_gyrus>\">Superior Temporal Gyrus</a> |
| Right supramarginal Surface Area | FS\_R\_Supramarginal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Supramarginal_gyrus>\">Supramarginal Gyrus</a> |
| Right frontalpole Surface Area | FS\_R\_Frontalpole\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Frontal_pole>\">Frontal Pole</a> |
| Right temporalpole Surface Area | FS\_R\_Temporalpole\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Temporal_pole>\">Temporal Pole</a> |
| Right transversetemporal Surface Area | FS\_R\_Transversetemporal\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Transverse_temporal_cortex>\">Transverse Temporal Cortex</a> |
| Right insula Surface Area | FS\_R\_Insula\_Area | Open | ^[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Insula>\">Insula</a> |

#### Instrument: Surface Thickness



| Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| Left bankssts Average Thickness | FS\_L\_Bankssts\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Banks_of_superior_temporal_sulcus>\">Banks of the Superior Temporal Sulcus</a> |
| Left caudalanteriorcingulate Average Thickness | FS\_L\_Caudalanteriorcingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_anterior_cingulate_cortex>\">Caudal Anterior Cingulate Cortex</a> |
| Left caudalmiddlefrontal Average Thickness | FS\_L\_Caudalmiddlefrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_middle_frontal_gyrus>\">Caudal Middle Frontal Gyrus</a> |
| Left cuneus Average Thickness | FS\_L\_Cuneus\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Cuneus_cortex>\">Cuneus Cortex</a> |
| Left entorhinal Average Thickness | FS\_L\_Entorhinal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Entorhinal_cortex>\">Entorhinal Cortex</a> |
| Left fusiform Average Thickness | FS\_L\_Fusiform\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Fusiform_gyrus>\">Fusiform Gyrus</a> |
| Left inferiorparietal Average Thickness | FS\_L\_Inferiorparietal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_parietal_cortex>\">Inferior Parietal Cortex </a> |
| Left inferiortemporal Average Thickness | FS\_L\_Inferiortemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_temporal_gyrus>\">Inferior Temporal Gyrus</a> |
| Left isthmuscingulate Average Thickness | FS\_L\_Isthmuscingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Isthmus_of_cingulate_gyrus>\">Isthmus Cingulate Gyrus</a> |
| Left lateraloccipital Average Thickness | FS\_L\_Lateraloccipital\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_occipital_cortex>\">Lateral Occipital Cortex</a> |
| Left lateralorbitofrontal Average Thickness | FS\_L\_Lateralorbitofrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_orbital_frontal_cortex>\">Lateral Orbital Frontal Cortex</a> |
| Left lingual Average Thickness | FS\_L\_Lingual\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lingual_gyrus>\">Lingual Gyrus</a> |
| Left medialorbitofrontal Average Thickness | FS\_L\_Medialorbitofrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Medial_orbital_frontal_cortex>\">Medial Orbital Frontal Cortex</a> |
| Left middletemporal Average Thickness | FS\_L\_Middletemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Middle_temporal_gyrus>\">Middle Temporal Gyrus</a> |
| Left parahippocampal Average Thickness | FS\_L\_Parahippocampal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Parahippocampal_gyrus>\">Parahippocampal Gyrus</a> |
| Left paracentral Average Thickness | FS\_L\_Paracentral\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Paracentral_sulcus>\">Paracentral Sulcus</a> |
| Left parsopercularis Average Thickness | FS\_L\_Parsopercularis\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Opercular_part_of_inferior_frontal_gyrus>\">Opercular Part of Inferior Frontal Gyrus</a> |
| Left parsorbitalis Average Thickness | FS\_L\_Parsorbitalis\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Orbital_part_of_inferior_frontal_gyrus>\">Orbital Part of Inferior Frontal Gyrus</a> |
| Left parstriangularis Average Thickness | FS\_L\_Parstriangularis\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Triangular_part_of_inferior_frontal_gyrus>\">Triangular Part of Inferior Frontal Gyrus</a> |
| Left pericalcarine Average Thickness | FS\_L\_Pericalcarine\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Pericalcarine_cortex>\">Pericalcarine Cortex</a> |
| Left postcentral Average Thickness | FS\_L\_Postcentral\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Postcentral_gyrus>\">Postcentral Gyrus</a> |
| Left posteriorcingulate Average Thickness | FS\_L\_Posteriorcingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Posterior_cingulate_gyrus>\">Posterior Cingulate Gyrus</a> |
| Left precentral Average Thickness | FS\_L\_Precentral\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precentral_gyrus>\">Precentral Gyrus</a> |
| Left precuneus Average Thickness | FS\_L\_Precuneus\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precuneus_cortex>\">Precuneus Cortex</a> |
| Left rostralanteriorcingulate Average Thickness | FS\_L\_Rostralanteriorcingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_anterior_cingulate_cortex>\">Rostral Anterior Cingulate Cortex</a> |
| Left rostralmiddlefrontal Average Thickness | FS\_L\_Rostralmiddlefrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_middle_frontal_gyrus>\">Rostral Middle Frontal Gyrus</a> |
| Left superiorfrontal Average Thickness | FS\_L\_Superiorfrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_frontal_gyrus>\">Superior Frontal Gyrus</a> |
| Left superiorparietal Average Thickness | FS\_L\_Superiorparietal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_parietal_cortex>\">Superior Parietal Cortex </a> |
| Left superiortemporal Average Thickness | FS\_L\_Superiortemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_temporal_gyrus>\">Superior Temporal Gyrus</a> |
| Left supramarginal Average Thickness |  FS\_L\_Supramarginal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Supramarginal_gyrus>\">Supramarginal Gyrus</a> |
| Left frontalpole Average Thickness |  FS\_L\_Frontalpole\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Frontal_pole>\">Frontal Pole</a> |
| Left temporalpole Average Thickness |  FS\_L\_Temporalpole\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Temporal_pole>\">Temporal Pole</a> |
| Left transversetemporal Average Thickness |  FS\_L\_Transversetemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Transverse_temporal_cortex>\">Transverse Temporal Cortex</a> |
| Left insula Average Thickness |  FS\_L\_Insula\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Insula>\">Insula</a> |
| Right bankssts Average Thickness |  FS\_R\_Bankssts\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Banks_of_superior_temporal_sulcus>\">Banks of the Superior Temporal Sulcus</a> |
| Right caudalanteriorcingulate Average Thickness |  FS\_R\_Caudalanteriorcingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_anterior_cingulate_cortex>\">Caudal Anterior Cingulate Cortex</a> |
| Right caudalmiddlefrontal Average Thickness |  FS\_R\_Caudalmiddlefrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Caudal_middle_frontal_gyrus>\">Caudal Middle Frontal Gyrus</a> |
| Right cuneus Average Thickness |  FS\_R\_Cuneus\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Cuneus_cortex>\">Cuneus Cortex</a> |
| Right entorhinal Average Thickness | FS\_R entorhinal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Entorhinal_cortex>\">Entorhinal Cortex</a> |
| Right fusiform Average Thickness |  FS\_R\_Fusiform\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Fusiform_gyrus>\">Fusiform Gyrus</a> |
| Right inferiorparietal Average Thickness |  FS\_R\_Inferiorparietal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_parietal_cortex>\">Inferior Parietal Cortex </a> |
| Right inferiortemporal Average Thickness |  FS\_R\_Inferiortemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Inferior_temporal_gyrus>\">Inferior Temporal Gyrus</a> |
| Right isthmuscingulate Average Thickness |  FS\_R\_Isthmuscingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Isthmus_of_cingulate_gyrus>\">Isthmus Cingulate Gyrus</a> |
| Right lateraloccipital Average Thickness |  FS\_R\_Lateraloccipital\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_occipital_cortex>\">Lateral Occipital Cortex</a> |
| Right lateralorbitofrontal Average Thickness |  FS\_R\_Lateralorbitofrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lateral_orbital_frontal_cortex>\">Lateral Orbital Frontal Cortex</a> |
| Right lingual Average Thickness |  FS\_R\_Lingual\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Lingual_gyrus>\">Lingual Gyrus</a> |
| Right medialorbitofrontal Average Thickness |  FS\_R\_Medialorbitofrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Medial_orbital_frontal_cortex>\">Medial Orbital Frontal Cortex</a> |
| Right middletemporal Average Thickness |  FS\_R\_Middletemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Middle_temporal_gyrus>\">Middle Temporal Gyrus</a> |
| Right parahippocampal Average Thickness | FS\_R\_Parahippocampal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Parahippocampal_gyrus>\">Parahippocampal Gyrus</a> |
| Right paracentral Average Thickness |  FS\_R\_Paracentral\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Paracentral_sulcus>\">Paracentral Sulcus</a> |
| Right parsopercularis Average Thickness |  FS\_R\_Parsopercularis\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Opercular_part_of_inferior_frontal_gyrus>\">Opercular Part of Inferior Frontal Gyrus</a> |
| Right parsorbitalis Average Thickness |  FS\_R\_Parsorbitalis\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Orbital_part_of_inferior_frontal_gyrus>\">Orbital Part of Inferior Frontal Gyrus</a> |
| Right parstriangularis Average Thickness |  FS\_R\_Parstriangularis\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Triangular_part_of_inferior_frontal_gyrus>\">Triangular Part of Inferior Frontal Gyrus</a> |
| Right pericalcarine Average Thickness |  FS\_R\_Pericalcarine\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Pericalcarine_cortex>\">Pericalcarine Cortex</a> |
| Right postcentral Average Thickness |  FS\_R\_Postcentral\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Postcentral_gyrus>\">Postcentral Gyrus</a> |
| Right posteriorcingulate Average Thickness |  FS\_R\_Posteriorcingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Posterior_cingulate_gyrus>\">Posterior Cingulate Gyrus</a> |
| Right precentral Average Thickness |  FS\_R\_Precentral\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precentral_gyrus>\">Precentral Gyrus</a> |
| Right precuneus Average Thickness |  FS\_R\_Precuneus\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Precuneus_cortex>\">Precuneus Cortex</a> |
| Right rostralanteriorcingulate Average Thickness | FS\_R rostralanteriorcingulate\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_anterior_cingulate_cortex>\">Rostral Anterior Cingulate Cortex</a> |
| Right rostralmiddlefrontal Average Thickness | FS\_R rostralmiddlefrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Rostral_middle_frontal_gyrus>\">Rostral Middle Frontal Gyrus</a> |
| Right superiorfrontal Average Thickness |  FS\_R\_Superiorfrontal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_frontal_gyrus>\">Superior Frontal Gyrus</a> |
| Right superiorparietal Average Thickness |  FS\_R\_Superiorparietal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_parietal_cortex>\">Superior Parietal Cortex </a> |
| Right superiortemporal Average Thickness |  FS\_R\_Superiortemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Superior_temporal_gyrus>\">Superior Temporal Gyrus</a> |
| Right supramarginal Average Thickness |  FS\_R\_Supramarginal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Supramarginal_gyrus>\">Supramarginal Gyrus</a> |
| Right frontalpole Average Thickness |  FS\_R\_Frontalpole\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Frontal_pole>\">Frontal Pole</a> |
| Right temporalpole Average Thickness |  FS\_R\_Temporalpole\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Temporal_pole>\">Temporal Pole</a> |
| Right transversetemporal Average Thickness |  FS\_R\_Transversetemporal\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Transverse_temporal_cortex>\">Transverse Temporal Cortex</a> |
| Right insula Average Thickness |  FS\_R\_Insula\_Thck | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | Neurolex definition: <a href=\"<http://neurolex.org/wiki/Category:Insula>\">Insula</a> |

### Category: Motor

#### Instrument: Endurance (2 minute walk test)


> This test is adapted from the American Thoracic Society's 6-Minute Walk Test Protocol.  This test measures sub-maximal cardiovascular endurance by recording the distance that the participant is able to walk on a 50-foot (out and back) course in 2 minutes.  The participant's raw score is the distance in feet and inches walked in 2 minutes. The test overall takes approximately 4 minutes to administer (with instructions and practice). This test is recommended for ages 3-85.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox 2-minute Walk Endurance Test: Unadjusted Scale Score | Endurance\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This test is adapted from the American Thoracic Society’s 6-Minute Walk Test Protocol. This test measures sub-maximal cardiovascular endurance by recording the distance that the participant is able to walk on a 50-foot (out and back) course in 2 minutes. The participant’s raw score is the distance in feet and inches walked in 2 minutes. The test overall takes approximately 4 minutes to administer (with instructions and practice). This test is recommended for ages 3-85. |
| NIH Toolbox 2-minute Walk Endurance Test: Age-Adjusted Scale Score | Endurance\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This test is adapted from the American Thoracic Society’s 6-Minute Walk Test Protocol. This test measures sub-maximal cardiovascular endurance by recording the distance that the participant is able to walk on a 50-foot (out and back) course in 2 minutes. The participant’s raw score is the distance in feet and inches walked in 2 minutes. The test overall takes approximately 4 minutes to administer (with instructions and practice). This test is recommended for ages 3-85. |

#### Instrument: Locomotion (4-meter walk test)


> This test is adapted from the American Thoracic Society's 6-Minute Walk Test Protocol.  This test measures sub-maximal cardiovascular endurance by recording the distance that the participant is able to walk on a 50-foot (out and back) course in 2 minutes.  The participant's raw score is the distance in feet and inches walked in 2 minutes. The test overall takes approximately 4 minutes to administer (with instructions and practice). This test is recommended for ages 3-85.
> 
> 



| Display Name | Column Header | Access | Validation | Comparators | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox 4-Meter Walk Gait Speed Test: Computed Score | GaitSpeed\_Comp | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This test is adapted from the 4-meter walk test in the Short Physical Performance Battery. Participants are asked to walk a short distance (four meters) at their usual pace. Participants complete one practice and then two timed trials. Raw scores are recorded as the time in seconds required to walk 4 meters on each of the two trials, with the better trial used for scoring. The test takes approximately three minutes to administer (including instructions and practice). This test is recommended for ages 7-85. Computed scores are in meters per second. |

#### Instrument: Dexterity (9-hole Pegboard)


> This simple test of manual dexterity records the time required for the participant to accurately place and remove 9 plastic pegs into a plastic pegboard.  The protocol includes 1 practice and 1 timed trial with each hand.  Raw scores are recorded as time in seconds that it takes the participant to complete the task with each hand (a separate score for each). The test takes approximately 4 minutes to administer and is recommended for ages 3-85.
> 
> 



       | Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox 9-hole Pegboard Dexterity Test: Unadjusted Scale Score | Dexterity\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This simple test of manual dexterity records the time required for the participant to accurately place and remove 9 plastic pegs into a plastic pegboard. The protocol includes 1 practice and 1 timed trial with each hand. Raw scores are recorded as time in seconds that it takes the participant to complete the task with the dominant hand. The test takes approximately 4 minutes to administer and is recommended for ages 3-85. |
| NIH Toolbox 9-hole Pegboard Dexterity Test: Age-Adjusted Scale Score | Dexterity\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This simple test of manual dexterity records the time required for the participant to accurately place and remove 9 plastic pegs into a plastic pegboard. The protocol includes 1 practice and 1 timed trial with each hand. Raw scores are recorded as time in seconds that it takes the participant to complete the task with the dominant hand. The test takes approximately 4 minutes to administer and is recommended for ages 3-85. |

#### Instrument: Strength (Grip Strength Dynamometry)


> This protocol is adapted from the grip strength testing protocol of the American Society of Hand Therapy.  Participants are seated in a chair with their feet touching the ground.  With the elbow bent to 90 degrees and the arm against the trunk, wrist at neutral, participants squeeze the Jamar Plus Digital dynamometer as hard as they can for a count of three.  The dynamometer provides a digital reading of force in pounds.  A practice trial at less than full force and 1 test trial are completed with each hand. The test takes approximately 3 minutes to administer and is recommended for ages 3-85.
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Grip Strength Test: Unadjusted Scale Score | Strength\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This protocol is adapted from the grip strength testing protocol of the American Society of Hand Therapy. Participants are seated in a chair with their feet touching the ground. With the elbow bent to 90 degrees and the arm against the trunk, wrist at neutral, participants squeeze the Jamar Plus Digital dynamometer as hard as they can for a count of three. The dynamometer provides a digital reading of force in pounds. A practice trial at less than full force and 1 test trial are completed with each hand.The Grip Strength Test provides a score for each hand, with the primary Toolbox score being the number of pounds of force the participant was able to generate using his/her dominant hand.The test takes approximately 3 minutes to administer and is recommended for ages 3-85. |
| NIH Toolbox Grip Strength Test: Age-Adjusted Scale Score | Strength\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This protocol is adapted from the grip strength testing protocol of the American Society of Hand Therapy. Participants are seated in a chair with their feet touching the ground. With the elbow bent to 90 degrees and the arm against the trunk, wrist at neutral, participants squeeze the Jamar Plus Digital dynamometer as hard as they can for a count of three. The dynamometer provides a digital reading of force in pounds. A practice trial at less than full force and 1 test trial are completed with each hand. The test takes approximately 3 minutes to administer and is recommended for ages 3-85. |

### Category: Personality

#### Instrument: Five Factor Model (NEO-FFI)


> There is consensus that a five factor model captures the major facets of human personality across cultures (Heine and Buchtel 2009): a) neuroticism; b) extroversion/introversion; c) agreeableness; d) openness; and e) conscientiousness (Goldberg 1993; McCrae and Costa 2008). We are administering the 60 item version of the Costa and McRae Neuroticism/Extroversion/Openness Five Factor Inventory (NEO-FFI), which has shown excellent reliability and validity (McCrae and Costa 2004). This measure was available as part of the Penn Computerized Cognitive Battery (Gur et al. 2001a; Gur et al. 2010).
> 
> 1. [Heine and Buchtel 2009](http://www.ncbi.nlm.nih.gov/pubmed/19035827)
> 2. [Goldberg 1993](http://www.ncbi.nlm.nih.gov/pubmed/8427480); [McCrae and Costa 2008](http://www.amazon.com/gp/search?index=books&linkCode=qs&keywords=1609180593)
> 3. [McCrae and Costa 2004](http://www.sciencedirect.com/science/article/pii/S0191886903001181)
> 4. [McCrae and Costa 2004](http://www.sciencedirect.com/science/article/pii/S0191886903001181)
> 



      | Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NEO-FFI Agreeableness (NEOFAC\_A) | NEOFAC\_A | Open | ^[0-9]+$ | =,NOT =,<,> | NEO-FFI Personality Agreeableness |
| NEO-FFI Openness to Experience (NEOFAC\_O) | NEOFAC\_O | Open | ^[0-9]+$ | =,NOT =,<,> | NEO-FFI Personality Openness |
| NEO-FFI Conscientiousness (NEOFAC\_C) | NEOFAC\_C | Open | ^[0-9]+$ | =,NOT =,<,> | NEO-FFI Personality Conscientiousness |
| NEO-FFI Neuroticism (NEOFAC\_N) | NEOFAC\_N | Open | ^[0-9]+$ | =,NOT =,<,> | NEO-FFI Personality Neuroticism |
| NEO-FFI Extraversion (NEOFAC\_E) | NEOFAC\_E | Open | ^[0-9]+$ | =,NOT =,<,> | NEO-FFI Personality Extroversion |

  


  


### Category: Psychiatric and Life Function

#### Restricted Instrument: Life Function (Achenbach Adult Self-Report, Syndrome Scales and DSM-Oriented Scale)


> The NIH toolbox contains self-report measures of a number of important domains of experience, including positive and negative affect, stress, anxiety, depression and social support. To obtain additional self-report information on an even broader variety of domains, we also administer the Achenbach Adult Self-Report for Ages 18-59 (Achenbach 2009). Specifically, we administer the 123 items from Section VIII. These can be used to generate the ASR Syndrome Scales and the ASR DSM-Oriented Scales.
> 
> 



| Display Name | Column Header | Access | Validation | Comparators   | Description |
| --- | --- | --- | --- | --- | --- |
| ASR Anxious/Depressed Raw Score (ASR\_Anxd\_Raw) | ASR\_Anxd\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[12][0-9]|3[0-6])$ | =,NOT =,<,> | ASR Anxious/Depressed Raw Score |
| ASR Anxious/Depressed Gender and Age Adjusted Percentile (ASR\_Anxd\_Pct) | ASR\_Anxd\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Anxious/Depressed Gender and Age Adjusted Percentile |
| ASR Withdrawn Raw Score (ASR\_Witd\_Raw) | ASR\_Witd\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-8])$ | =,NOT =,<,> | ASR Withdrawn Raw Score |
| ASR Withdrawn Gender and Age Adjusted Percentile (ASR\_Witd\_Pct) | ASR\_Witd\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Withdrawn Gender and Age Adjusted Percentile |
| ASR Somatic Complaints Raw Score (ASR\_Soma\_Raw) | ASR\_Soma\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-8])$ | =,NOT =,<,> | ASR Somatic Complaints Raw Score |
| ASR Somatic Complaints Gender and Age Adjusted Percentile (ASR\_Soma\_Pct) | ASR\_Soma\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Somatic Complaints Gender and Age Adjusted Percentile |
| ASR Thought Problems Raw Score (ASR\_Thot\_Raw) | ASR\_Thot\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-9]|20)$ | =,NOT =,<,> | ASR Thought Problems Raw Score |
| ASR Thought Problems Gender and Age Adjusted Percentile (ASR\_Thot\_Pct) | ASR\_Thot\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Thought Problems Gender and Age Adjusted Percentile |
| ASR Attention Problems Raw Score (ASR\_Attn\_Raw) | ASR\_Attn\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[12][0-9]|30)$ | =,NOT =,<,> | ASR Attention Problems Raw Score |
| ASR Attention Problems Gender and Age Adjusted Percentile (ASR\_Attn\_Pct) | ASR\_Attn\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Attention Problems Gender and Age Adjusted Percentile |
| ASR Aggressive Behavior Raw Score (ASR\_Aggr\_Raw) | ASR\_Aggr\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[12][0-9]|30)$ | =,NOT =,<,> | ASR Aggressive Behavior Raw Score |
| ASR Aggressive Behavior Gender and Age Adjusted Percentile (ASR\_Aggr\_Pct) | ASR\_Aggr\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Aggressive Behavior Gender and Age Adjusted Percentile |
| ASR Rule Breaking Behavior Raw Score (ASR\_Rule\_Raw) | ASR\_Rule\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-9]|2[0-8])$ | =,NOT =,<,> | ASR Rule Breaking Behavior Raw Score |
| ASR Rule Breaking Behavior Gender and Age Adjusted Percentile (ASR\_Rule\_Pct) | ASR\_Rule\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Rule Breaking Behavior Gender and Age Adjusted Percentile |
| ASR Intrusive Raw Score (ASR\_Intr\_Raw) | ASR\_Intr\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-2])$ | =,NOT =,<,> | ASR Intrusive Gender and Age Adjusted Percentile |
| ASR Intrusive Gender and Age Adjusted Percentile (ASR\_Intr\_Pct) | ASR\_Intr\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR Intrusive Gender and Age Adjusted Percentile |
| ASR Other Problems Raw Score (ASR\_Oth\_Raw) | ASR\_Oth\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[1-3][0-9]|4[0-2])$ | =,NOT =,<,> | ASR Other Raw Score |
| ASR Critical Items Raw Score (ASR\_Crit\_Raw) | ASR\_Crit\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[12][0-9]|3[0-4])$ | =,NOT =,<,> | ASR Critical Items Raw Score |
| ASR Internalizing Raw Score (ASR\_Intn\_Raw) | ASR\_Intn\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[1-6][0-9]|7[0-8])$ | =,NOT =,<,> | ASR Internalizing Raw Score |
| ASR Internalizing Gender and Age Adjusted T-score (ASR\_Intn\_T) | ASR\_Intn\_T | **Tier 1 Restricted** | ^0\*([3-9][0-9]|100)$ | =,NOT =,<,> | ASR Internalizing Gender and Age Adjusted T-score |
|  ASR Externalizing Raw Score (ASR\_Extn\_Raw) | ASR\_Extn\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[1-6][0-9]|70)$ | =,NOT =,<,> | ASR Externalizing Raw Score |
| ASR Externalizing Gender and Age Adjusted T-score (ASR\_Computed\_Externalizing\_Adjusted\_T) (ASR\_Extn\_T) | ASR\_Extn\_T | **Tier 1 Restricted** | ^0\*([3-9][0-9]|100)$ | =,NOT =,<,> | ASR Externalizing Gender and Age Adjusted T-score |
| ASR Sum of Thought, Attention, and Other Problems Raw Score (ASR\_TAO\_Sum) | ASR\_TAO\_Sum | **Tier 1 Restricted** | ^0\*([0-9]|[1-7][0-9]|8[0-4])$ | =,NOT =,<,> | ASR Sum of Thought, Attention, and Other Raw Score |
| ASR Total Problems Raw Score (ASR\_Totp\_Raw) | ASR\_Totp\_Raw | **Tier 1 Restricted** | ^0\*([0-9]{1,2}|1[0-9]{2}|2[0-3][0-9]|240)$ | =,NOT =,<,> | ASR Total Raw Score |
| ASR Total Problems Gender and Age Adjusted T-score (ASR\_Totp\_T) | ASR\_Totp\_T | **Tier 1 Restricted** | ^0\*(2[5-9]|[3-9][0-9]|100)$ | =,NOT =,<,> | ASR Total Gender and Age Adjusted T-score |
| ASR DSM Depressive Problems Raw Score (DSM\_Depr\_Raw) | DSM\_Depr\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-9]|2[0-8])$ | =,NOT =,<,> | ASR DSM Depressive Problems Raw Score |
| ASR DSM Depressive Problems Gender and Age Adjusted Percentile (DSM\_Depr\_Pct) | DSM\_Depr\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR DSM Depressive Problems Gender and Age Adjusted Percentile |
| ASR DSM Anxiety Problems Raw Score (DSM\_Anxi\_Raw) | DSM\_Anxi\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-4])$ | =,NOT =,<,> | ASR DSM Anxiety Problems Raw Score |
| ASR DSM Anxiety Problems Gender and Age Adjusted Percentile (DSM\_Anxi\_Pct) | DSM\_Anxi\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR DSM Anxiety Problems Gender and Age Adjusted Percentile |
| ASR DSM Somatic Problems Raw Score (DSM\_Somp\_Raw) | DSM\_Somp\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-8])$ | =,NOT =,<,> | ASR DSM Somatic Problems Raw Score |
| ASR DSM Somatic Problems Gender and Age Adjusted Percentile (DSM\_Somp\_Pct) | DSM\_Somp\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR DSM Somatic Problems Gender and Age Adjusted Percentile |
| ASR DSM Avoidant Personality Problems Raw Score (DSM\_Avoid\_Raw) | DSM\_Avoid\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-4])$ | =,NOT =,<,> | ASR DSM Avoidant Personality Problems Raw Score |
| ASR DSM Avoidant Personality Problems Gender and Age Adjusted Percentile (DSM\_Avoid\_Pct) | DSM\_Avoid\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR DSM Avoidant Personality Problems Gender and Age Adjusted Percentile |
| ASR DSM AD/H Problems Raw Score (DSM\_Adh\_Raw) | DSM\_Adh\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-9]|2[0-6])$ | =,NOT =,<,> | ASR DSM AD/H Problems Raw Score |
| ASR DSM AD/H Problems Gender and Age Adjusted Percentile (DSM\_Adh\_Pct) | DSM\_Adh\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR DSM AD/H Problems Gender and Age Adjusted Percentile |
| ASR DSM Inattention Problems Raw Score (DSM\_Inat\_Raw) | DSM\_Inat\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-4])$ | =,NOT =,<,> | ASR DSM Inattention Problems Raw Score |
| ASR DSM Hyperactivity Problems Raw Score (DSM\_Hype\_Raw) | DSM\_Hype\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|1[0-2])$ | =,NOT =,<,> | ASR DSM Hyperactivity Problems Raw Score |
| ASR DSM Antisocial Personality Problems Raw Score (DSM\_Antis\_Raw) | DSM\_Antis\_Raw | **Tier 1 Restricted** | ^0\*([0-9]|[1-3][0-9]|40)$ | =,NOT =,<,> | ASR DSM Antisocial Personality Problems Raw Score |
| ASR DSM Antisocial Personality Problems Gender and Age Adjusted Percentile (DSM\_Antis\_Pct)  | DSM\_Antis\_Pct | **Tier 1 Restricted** | ^0\*([5-9][0-9]|100)$ | =,NOT =,<,> | ASR DSM Antisocial Personality Problems Gender and Age Adjusted Percentile |

#### Restricted Instrument: Psychiatric History



| Display Name | Column Header | Access | Validation | Comparators   | Description |
| --- | --- | --- | --- | --- | --- |
| Childhood Conduct Problems | SSAGA\_ChildhoodConduct | **Tier 1 Restricted** | ^[0-9]+$ | =,NOT = |  |
| Panic Disorder | SSAGA\_PanicDisorder | **Tier 1 Restricted** | ^[0-9]+$ |  | Non-diagnostic screen available to exclude possible cases of panic disorder |
| Agoraphobia | SSAGA\_Agoraphobia | **Tier 1 Restricted** | ^[0-9]+$ |  | Non-diagnostic screen available to exclude possible cases of agoraphobia |
| Major Depressive Episode | SSAGA\_Depressive\_Ep | **Tier 1 Restricted** | ^[0-9]+$ |  | Has the participant experienced a diagnosed DSMIV Major Depressive Episode over his/her lifetime? |
| Number Depressive Symptoms | SSAGA\_Depressive\_Sx | **Tier 1 Restricted** | ^[0-9]+$ |  | Number of depressive symptoms over lifetime that meet DSMIV criterion for major depression. |

### 

  


### Category: Sensory

#### Instrument: Audition (Words in Noise)



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Words-In-Noise Age 6+: Computed Score | Noise\_Comp | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<, | This automated audiometric test measures hearing thresholds at six different frequencies (.5, 1, 2, 4, 6 and 8 kHz), separately in the left and right ears. On each trial, the participant’s task is to detect whether a pure tone was presented via headphones by answering yes (tone heard) or no (tone not heard). This test takes approximately nine minutes to administer and is recommended for ages 6-85. Based on the participant’s responses, the computer software automatically scores each trial at each of the frequencies for left and right ears, determining the hearing threshold (in decibels)—that is, the level below which the participant cannot hear the tone.To provide a unifying score for Toolbox users, a single hearing metric is provided that is commonly used: a Pure Tone Average (PTA). This is calculated by averaging the threshold scores of 1, 2 and 4 kHz frequencies. Scores for each ear are calculated, with the PTA from the better ear reported as the primary score (i.e., the ear with the lower PTA). |

#### Instrument: Olfaction (Odor Identification Test)



        | Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Odor Identification Age 3+ Unadjusted Scale Score | Odor\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| NIH Toolbox Odor Identification Age 3+ Age-Adjusted Scale Score | Odor\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Pain (Pain Intensity and Interference Surveys)



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Pain Intensity Survey Age 18+: Raw ScoreExcluded currently due to glich in the Toolbox data download | PainIntens\_RawScore |  |  |  | This measure consists of a single item measuring immediate (i.e., acute) pain in adults. It asks a participant to rate level of pain experienced “over the last seven days.” It takes less than one minute to administer and is recommended for ages 18-85.Scoring Process: The single item is simply scored on a 0-10 scale, with 0 representing no pain, and 10 representing the “worst imaginable pain.” No derived scores are available. |
| NIH Toolbox Pain Interference Survey Age 18+: T-score | PainInterf\_Tscore | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> | This brief self-report scale measures the degree to which pain interferes with other activities in life in adults. Pain interference items were developed as part of the NIH PROMIS. This measure is administered as a CAT and takes approximately three minutes. It is recommended for ages 18-85. Each item administered has a 5-point scale with options ranging from “not at all” to “very much” on questions about how much pain interferes with aspects of one’s life. The survey is scored, and while no Toolbox norms are available for this measure, the scores are converted to general T-scores based on the PROMIS sample to whom this test was given. |

#### Instrument: Taste (Taste Intensity Test)



        | Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| NIH Toolbox Regional Taste Intensity Age 12+ Unadjusted Scale Score | Taste\_Unadj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| NIH Toolbox Regional Taste Intensity Age 12+ Age-Adjusted Scale Score | Taste\_AgeAdj | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Vision (EVA Scores and Farnsworth Test)



| Display Name | Column Header | Access | Enumerated Values | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- | --- |
| Color Vision Category | Color\_Vision | **Tier 1 Restricted** | NormalTritianProtanDeutran |  | =,NOT = |  |
| Eye Used For Color Vision Test | Eye | **Tier 1 Restricted** | Both (B)Right (R)Left (L) |  | =,NOT = |  |
| EVA score - Numerator | EVA\_Num | **Tier 1 Restricted** | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |  |
| EVA score - Denominator | EVA\_Denom | **Tier 1 Restricted** | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |  |
| Eyeglass correction | Correction | **Tier 1 Restricted** |  | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Contrast Sensitivity (Mars Contrast Sensitivity)


> Contrast sensitivity is measured using the Mars Contrast Sensitivity Test (Arditi et al. 2005), a brief, valid and reliable measure that improves upon the traditional Pelli-Robson measure (Dougherty et al. 2005; Haymes et al. 2006; Thayaparan et al. 2007).
> 
> 



        | Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Mars Contrast Sensitivity Score | Mars\_Log\_Score | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |
| Errors on Mars | Mars\_Errs | Open | ^[0-9]+$ | =,NOT =,<,> |  |
| Mars Final Contrast Sensitivity Score | Mars\_Final | Open | ^[-+]?[0-9]\*[.]?[0-9]+$ | =,NOT =,<,> |  |

### Category: Substance Use

#### Instrument: Breathalyzer and Drug Test Results



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Any breathalyzer over .05 | Breathalyzer\_Over\_05 | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Any breathalyzer over .08 | Breathalyzer\_Over\_08 | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Positive test for Cocaine | Cocaine | **Tier 2 Restricted** |  | =,NOT = |  |
| Positive test for THC | THC | **Tier 2 Restricted** |  | =,NOT = |  |
| Positive test for Opiates | Opiates | **Tier 2 Restricted** |  | =,NOT = |  |
| Positive test for Amphetamines | Amphetamines | **Tier 2 Restricted** |  | =,NOT = |  |
| Positive test for MethAmphetamine | MethAmphetamine | **Tier 2 Restricted** |  | =,NOT = |  |
| Positive test for Oxycontin | Oxycontin | **Tier 2 Restricted** |  | =,NOT = |  |

#### Instrument: Alcohol Use 7-Day Retrospective



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Total drinks in past 7 days | Total\_Drinks\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Number days drank in past 7 days | Num\_Days\_Drank\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday drinks/day in past 7 days | Avg\_Weekday\_Drinks\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend drinks/day in past 7 days | Avg\_Weekend\_Drinks\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total drinks in past 7 days (Beer/Wine Coolers) | Total\_Beer\_Wine\_Cooler\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday drinks/day in past 7 days (Beer/Wine Coolers) | Avg\_Weekday\_Beer\_Wine\_Cooler\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend drinks/day in past 7 days (Beer/Wine Coolers) | Avg\_Weekend\_Beer\_Wine\_Cooler\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total drinks in past 7 days (Malt Liquor) | Total\_Malt\_Liquor\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday drinks/day in past 7 days (Malt Liquor) | Avg\_Weekday\_Malt\_Liquor\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend drinks/day in past 7 days (Malt Liquor) | Avg\_Weekend\_Malt\_Liquor\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total drinks in past 7 days (Wine) | Total\_Wine\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday drinks/day in past 7 days (Wine) | Avg\_Weekday\_Wine\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend drinks/day in past 7 days (Wine) | Avg\_Weekend\_Wine\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total drinks in past 7 days (Hard Liquor) | Total\_Hard\_Liquor\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday drinks/day in past 7 days (Hard Liquor) | Avg\_Weekday\_Hard\_Liquor\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend drinks/day in past 7 days (Hard Liquor) | Avg\_Weekend\_Hard\_Liquor\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total drinks in past 7 days (Other Alcohol) | Total\_Other\_Alc\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday drinks/day in past 7 days (Other Alcohol) | Avg\_Weekday\_Other\_Alc\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend drinks/day in past 7 days (Other Alcohol) | Avg\_Weekend\_Other\_Alc\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Alcohol Use and Dependence



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Number of DSM4 Alcohol Dependence Criteria Endorsed | SSAGA\_Alc\_D4\_Dp\_Sx | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Number of DSM4 ALC Dependence Criteria Met: If participant is male: 0, 1, 2, 3+ = 3; If female: 0, 1, 2+ = 2 |
| DSM4 Alcohol Abuse Criteria Met | SSAGA\_Alc\_D4\_Ab\_Dx | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant meets DSM4 criteria for Alcohol Abuse |
| DSM4 Alcohol Abuse number of symptoms | SSAGA\_Alc\_D4\_Ab\_Sx | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Number of symptoms participant has of DSM4 Alcohol Abuse  |
| DSM4 Alcohol Dependence Criteria Met | SSAGA\_Alc\_D4\_Dp\_Dx | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant meets DSM4 criteria for DSM4 Alcohol Dependence   |
| Drinks per drinking day in past 12 months | SSAGA\_Alc\_12\_Drinks\_Per\_Day | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Drinks consumed per drinking day in past 12 months: 0, 1, 2, 3, 4, 5-6 = 5, 7+ = 6 |
| Frequency of any alcohol use in past 12 months | SSAGA\_Alc\_12\_Frq | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Frequency of any alcohol use in past 12 months:  4-7 days/week (1 if male, 2 if female), 3 days/week = 2, 2 days/week = 3, 1 day/week = 4, 1-3 days month = 5, 1-11 days/year = 6, never in past 12 months = 7 |
| Frequency of drinking 5+ drinks in past 12 months | SSAGA\_Alc\_12\_Frq\_5plus | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Frequency of drinking 5+ drinks in past 12 months: 3+ days/week = 1 if male, 2 if female;  1-2 days/week = 2; 1-3 days/month = 3; 1-11 days/year = 4; never = 5 |
| Frequency drunk in past 12 months | SSAGA\_Alc\_12\_Frq\_Drk | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Frequency drunk in past 12 months: 1-7 days/week = 1 if male, 2 if female, 1-3 days/month = 2, 1-11 days/year = 3, never = 4 |
| Max drinks in a single day in past 12 months | SSAGA\_Alc\_12\_Max\_Drinks | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Max drinks consumed in a single day in the past 12 months: 1-2 = 1; 3-4 = 2; 5-6 = 3; 7-8 = 4; 9-10 = 5; 11-12 = 6 if male, 5 if female; 13+ = 7, 5 if female |
| Age at first alcohol use | SSAGA\_Alc\_Age\_1st\_Use | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Age at first alcohol use: <15 = 1, 15-16 = 2, 17-18 = 3, 19-20 = 4, 21+ = 5 |
| Drinks per day in heaviest 12-month  period | SSAGA\_Alc\_Hvy\_Drinks\_Per\_Day | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Drinks per day in heaviest 12-month drinking period of participant's lifetime: 0 or 1 = 1, 2, 3, 4, 5-6 = 5, 7+ = 6 |
| Frequency of any alcohol use, heaviest 12-month period | SSAGA\_Alc\_Hvy\_Frq | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Frequency of any alcohol use in heaviest 12-month drinking period of participant's lifetime:  4-7 days/week  = 1, 3 days/week = 2, 2 days/week = 3, 1 day/week = 4, 1-3 days/month = 5, 1-11 days/year or never = 6 |
| Frequency of drinking 5+ drinks,  heaviest 12-month period | SSAGA\_Alc\_Hvy\_Frq\_5plus | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Frequency of drinking 5+ drinks during heaviest 12-month drinking period of participant's lifetime: 3+ days/week = 1, 1-2 days/week = 2, 1-3 days/month = 3, 1-11 days year = 4, never = 5 |
| Frequency drunk in heaviest 12-month period | SSAGA\_Alc\_Hvy\_Frq\_Drk | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Frequency drunk in heaviest 12-month drinking period of participant's lifetime: 1-7 days/week = 1, 1-3 days/month = 2, 1-11 days/year = 3, never = 4 |
| Lifetime max drinks in single day | SSAGA\_Alc\_Hvy\_Max\_Drinks | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Lifetime max drinks consumed in single day: <=3 = 1; 4-6 = 2; 7-9 = 3; 10-12 = 4; 13-15 = 5; 16-20 = 6; 21+ = 7 if male, 6 if female |

#### Instrument: Tobacco Use 7-Day Retrospective



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Total times used/smoked ANY TOBACCO in past 7 days | Total\_Any\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Times used/smoked ANY TOBACCO TODAY | Times\_Used\_Any\_Tobacco\_Today | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Number days smoked/used ANY TOBACCO in past 7 days | Num\_Days\_Used\_Any\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekday ANY TOBACCO per day in past 7 days | Avg\_Weekday\_Any\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg total weekend ANY TOBACCO per day in past 7 days | Avg\_Weekend\_Any\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total # CIGARETTES in past 7 days | Total\_Cigarettes\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekday CIGARETTES per day in past 7 days | Avg\_Weekday\_Cigarettes\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekend CIGARETTES per day in past 7 days | Avg\_Weekend\_Cigarettes\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total # CIGARS in past 7 days | Total\_Cigars\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekday CIGARS per day in past 7 days | Avg\_Weekday\_Cigars\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekend CIGARS per day in past 7 days | Avg\_Weekend\_Cigars\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Total # PIPES in past 7 days | Total\_Pipes\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekday PIPES per day in past 7 days | Avg\_Weekday\_Pipes\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekend PIPES per day in past 7 days | Avg\_Weekend\_Pipes\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Times used CHEW in past 7 days | Total\_Chew\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekday times used CHEW per day in past 7 days | Avg\_Weekday\_Chew\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekend times used CHEW per day in past 7 days | Avg\_Weekend\_Chew\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Times used SNUFF in past 7 days | Total\_Snuff\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekday times used SNUFF per day in past 7 days | Avg\_Weekday\_Snuff\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekend times used SNUFF per day in past 7 days | Avg\_Weekend\_Snuff\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Times used OTHER TOBACCO in past 7 days | Total\_Other\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekday times used OTHER TOBACCO per day in past 7 days | Avg\_Weekday\_Other\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |
| Avg weekend times used OTHER TOBACCO per day in past 7 days | Avg\_Weekend\_Other\_Tobacco\_7days | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> |  |

#### Instrument: Tobacco Use and Dependence



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Fagerstrom FTND score | SSAGA\_FTND\_Score | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Fagerstrom FTND score: 4+ indicative of dependence; >6 recoded as 6) |
| Fagerstrom HSI score: HSI measure of tobacco dependence | SSAGA\_HSI\_Score | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Fagerstrom HSI score: HSI measure of tobacco dependence  (>4 recoded as 4) |
| For regular smokers, age first smoked a cigarette (even a puff) | SSAGA\_TB\_Age\_1st\_Cig | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | For those who were/are regular smokers, age first smoked a cigarette (even a puff), (<=14, 15-17, 18-20, >=21) |
| DSM tobacco dependence - difficulty quitting | SSAGA\_TB\_DSM\_Difficulty\_Quitting | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant meets DSM criteria for tobacco dependence - difficulty quitting |
| DSM tobacco dependence - tolerance | SSAGA\_TB\_DSM\_Tolerance | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant meets DSM criteria for tobacco dependence - tolerance |
| DSM tobacco dependence - withdrawal | SSAGA\_TB\_DSM\_Withdrawal | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Participant meets DSM criteria for tobacco dependence - withdrawal |
| Cigarettes per day during heaviest period | SSAGA\_TB\_Hvy\_CPD | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | For those who were/are regular smokers, Cigarettes per day during heaviest period of use (1-5 = 5; 6-10 = 10; 11-15 = 15; 16-20 = 20; >20 = 30) |
| Most cigarettes smoked in a day | SSAGA\_TB\_Max\_Cigs | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | For those who were/are regular smokers, Most cigarettes smoked in a day (5, 10, 15, 20, >=30) |
| Cigarettes per day when smoking regularly | SSAGA\_TB\_Reg\_CPD | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | For those who were/are regular smokers, Cigarettes per day when smoking regularly (1-5 = 5; 6-10 = 10; 11-15 = 15; 16-20 = 20; >20 = 30) |
| Smoking history | SSAGA\_TB\_Smoking\_History | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Smoking history: never smoked (0), experimented 1-19 times (1), smoked 20+ cigarettes over lifetime, but was never a regular smoker (2), was/is a regular smoker (3) |
| Whether age last smoked is current age | SSAGA\_TB\_Still\_Smoking | **Tier 2 Restricted** |  | = | For those who were/are regular smokers, Is the participant still smoking? |
| Years since respondent smoked last cigarette | SSAGA\_TB\_Yrs\_Since\_Quit | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | For those who were/are regular smokers, Years since respondent smoked last cigarette (0; 1; 2 or more) |
| Years smoked | SSAGA\_TB\_Yrs\_Smoked | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | For those who were/are regular smokers, Years smoked (1-5 years = 5; 6-10 = 10; 11-15 = 15; 16+ = 18) |

#### Instrument: Illicit Drug Use



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Times used illicit drugs | SSAGA\_Times\_Used\_Illicits | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | ???Is this just a sum of the below? |
| Times used cocaine | SSAGA\_Times\_Used\_Cocaine | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Times used cocaine: never used = 0, 1-2 = 1, 3-5 = 1, 6-10 = 5, >10 = 5 |
| Times used hallucinogens | SSAGA\_Times\_Used\_Hallucinogens | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Times used hallucinogens: never used = 0, 1-2 = 1, 3-5 = 1, 6-10 = 5, >10 = 5 |
| Times used opiates | SSAGA\_Times\_Used\_Opiates | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Times used opiates: never used = 0, 1-2 = 1, 3-5 = 1, 6-10 = 5, >10 = 5 |
| Times used sedatives | SSAGA\_Times\_Used\_Sedatives | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Times used sedatives: never used = 0, 1-2 = 1, 3-5 = 1, 6-10 = 5, >10 = 5 |
| Times used stimulants | SSAGA\_Times\_Used\_Stimulants | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Times used stimulants: never used = 0, 1-2 = 1, 3-5 = 1, 6-10 = 5, >10 = 5 |

#### Instrument: Marijuana Use and Dependence



| Display Name | Column Header | Access | Validation | Comparators  | Description |
| --- | --- | --- | --- | --- | --- |
| Ever used marijuana? | SSAGA\_Mj\_Use | **Tier 2 Restricted** |  | = | Ever used marijuana: no = 0; yes = 1 |
| DSM Marijuana Dependence | SSAGA\_Mj\_Ab\_Dep | **Tier 2 Restricted** |  | = | Participant meets DSM criteria for Marijuana Dependence |
| Age at first marijuana use | SSAGA\_Mj\_Age\_1st\_Use | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Age at first marijuana use: <=14 = 1; 15-17 = 2; 18-20 = 3; >=21 = 4 |
| Times used marijuana | SSAGA\_Mj\_Times\_Used | **Tier 2 Restricted** | ^[0-9]+$ | =,NOT =,<,> | Times used marijuana: never used = 0; 1-5 = 1; 6-10 = 2; 11-25 = 3; 26-50 = 3; 51-100 = 3; 101-999 = 4; 1000-2000 = 5; >2000 = 5 |

  


  




### Attachments

- [HCP_S1200_DataDictionary_Oct_30_2023.csv](./assets/HCP_S1200_DataDictionary_Oct_30_2023.csv)
- [HCP_S1200_DataDictionary_Oct_30_2023.xlsx](./assets/HCP_S1200_DataDictionary_Oct_30_2023.xlsx)
- [HCP_S1200_DataDictionary_Aug_22_2023.xlsx](./assets/HCP_S1200_DataDictionary_Aug_22_2023.xlsx)
- [HCP_S1200_DataDictionary_Aug_22_2023.csv](./assets/HCP_S1200_DataDictionary_Aug_22_2023.csv)
- [HCP_S1200_DataDictionary_April_20_2018.csv](./assets/HCP_S1200_DataDictionary_April_20_2018.csv)
- [HCP_S1200_DataDictionary_April_20_2018.xlsx](./assets/HCP_S1200_DataDictionary_April_20_2018.xlsx)
- [HCP_S1200_DataDictionary_April_11_2018.xlsx](./assets/HCP_S1200_DataDictionary_April_11_2018.xlsx)
- [HCP_S1200_DataDictionary_April_11_2018.csv](./assets/HCP_S1200_DataDictionary_April_11_2018.csv)
- [HCP_S1200_DataDictionary_Sept_18_2017.xls](./assets/HCP_S1200_DataDictionary_Sept_18_2017.xls)
- [HCP_S1200_DataDictionary_Sept2017.xls](./assets/HCP_S1200_DataDictionary_Sept2017.xls)
- [HCP_S1200_DataDictionary_Aug2017.xls](./assets/HCP_S1200_DataDictionary_Aug2017.xls)
