# Data Description
---

### `data.csv`: Raw data collected on voting preferences and participant 

  | Column          | Description                                                                                                            |
  |-----------------|------------------------------------------------------------------------------------------------------------------------|
  | `ID`            | Participant ID                                                                                                         |
  | `DelID`         | ID of the person who received direct delegation from the participant (ID of delegatee or `NaN` if participant voted directly) |
  | `GuruID`        | ID of the person representing the participant through transitive delegation (ID of delegatee or participant’s ID if no delegation occurred) |
  | `Answer`        | Binary variable indicating whether the participant was correct (`1` for correct, `0` for incorrect)                   |
  | `AverageExpertise` | Expertise score of the participant for this task                                                                   |
  | `Weight`        | Number of people the participant represents for this task                                                             |
  | `CodeQuestion`  | Question ID                                                                                                           |
  | `CodeExclu`     | Task ID                                                                                                               |
  | `ExpNum`        | Experiment ID  

<br><br>

### `anova.csv`: Contains the data to perform an ANOVA analyses for gender correlations. 
  | Column     | Description                           |
  |------------|---------------------------------------|
  | ...  | same as in data.csv            |
  | `ProbaDel`  | Average number of times participant delegate across all tasks             |
  | `gender`        | categorical variable for gender                                |
| `IRTExpertise`        | Participant's expertise for a given task|
| `Normalized_IRT_1`        | Normalized IRTExpertise|


<br><br>

### `phi_w_gmm.csv`: Estimated $\varphi$ for each pair of expertise.
  | Column     | Description                           |
  |------------|---------------------------------------|
  | ...  | same as in data.csv            |
  | `pi`  | Expertise of the delegator |
  | `pj`  | Expertise of the person receiving delegations    
  | `Weight`        | Estimated $\varphi(p_i, p_j)$|

  <br><br>

### `LDvDD_means.csv`: Aggregated means data comparing Liquid Democracy (LD) and Direct Democracy (DD) results per task.
  | Column     | Description                           |
  |------------|---------------------------------------|
  | ...  | same as in data.csv            |
  | `Estimate`  | LD or DD estimate for a given task and experiment |
  | `Cat`  | `0` if DD estimate, `1` if LD estimate | 


  <br><br>

### `LDvDD.csv`: Aggregated means data comparing Liquid Democracy (LD) and Direct Democracy (DD) results per questions.
  | Column     | Description                           |
  |------------|---------------------------------------|
  | ...  | same as in data.csv            |
  | `Estimate`  | LD or DD estimate for a given question and experiment |
  | `Cat`  | `0` if DD estimate, `1` if LD estimate | 



  <br><br>

### `R_paper.csv`: Final dataset used for the main study analyses in R. (`R_paper_pre_study.csv` for pre-study.)                  
  | Column     | Description                           |
  |------------|---------------------------------------|
  | ...  | same as in anova.csv            |
  | `Labels_GMM`  | Bucket assigment with GMM |
  | `Labels_Kmeans`  | Bucket assignment with k-means |   
  | `Buckets`  | Bucket assignment with equal cut or quantile cut |