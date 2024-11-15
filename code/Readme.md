# Code Navigation

## Variables
The study spans a pre-study and a fianl study and tests various statistical methods. Variables are defined to specify the survey data and method used to generate results.

| Variable       | Description                                               | Values                                                                   |
|----------------|-----------------------------------------------------------|--------------------------------------------------------------------------|
| `focus_on`     | Specify data slice to study (either main study or pre-study) | `B1` or `B2`                                                            |
| `method`       | Indicates which bucketing strategy is being tested        | `buckets`, `q_buckets` (equal/quantile cut) or `gmm`, `k_gmm` (GMM/KMeans) |
| `bucket_num`   | Number of buckets for methods that do not compute it automatically | `(int)` to be specified when using equal/quantile cut only |

<br><br>
## Notebook Structure: `EmpiricalAnalysis.ipynb`

The `EmpiricalAnalysis.ipynb` notebook is organized into several key sections, each focusing on a different aspect of the analysis for Liquid Democracy vs. Direct Democracy. Below is an outline of the notebook structure and what each section covers:

### 1. Settings
   - This section sets up the environment, importing necessary libraries and defining functions for the analysis.

### 2. Data Processing
   - In this section, data is loaded, cleaned, and preprocessed to prepare it for analysis.

### 3. High-level Statistics
   - Presents summary statistics and initial observations from the dataset, offering an overview of participant demographics, voting behavior, and delegation patterns.
   - Figures 18 and 20  (with focus_on = 'B2'), Table 3 and 14

### 4. Compute Expertise
   - Calculates the expertise scores for each participant, which are used in later analyses to evaluate the relationship between expertise and delegation behavior.

### 5. Delegation and Expertise Plots
   - Generates visualizations that examine the connections between delegation choices and participant expertise levels, highlighting patterns in delegation dynamics.
   - Figures 19, 21, 22 (with focus_on = 'B2')

### 6. Estimating $q$ and $\varphi$
   - **Bucketing:** This sub-section explores various bucketing strategies for grouping participants based on expertise and voting patterns.
      - **Gaussian Mixture:** Applies Gaussian Mixture Modeling to identify clusters in participant expertise.
      - **K-means Clustering:** Uses K-means clustering as an alternative approach for grouping participants.
      - **Equal Cut:** Divides participants into buckets of equal size for comparative analysis.
      - **Quantile Cut:** Creates buckets based on quantiles to study distributional effects.

   - **Compute Phi:** Calculates the $\varphi$ parameter, representing a key variable in assessing delegation accuracy and expertise alignment.
      - Table 2/Figure2 (with focus_on = 'B2', `method='k_gmm')
      - Table 9/Figure 12 (with focus_on = 'B2', method = "buckets" and bucket_num = 3)
      - Table 10/Figure 13 (with focus_on = 'B2', method = "buckets" and bucket_num = 5)
      - Table 11/Figure 14 (with focus_on = 'B2', method = "buckets" and bucket_num = 7)
      - Table 12/Figure 15 (with focus_on = 'B2', method = "buckets" and bucket_num = 10)
      - Table 14/Figure 16 (with focus_on = 'B2', method = "q_buckets" and bucket_num = 7)
      - Table 13/Figure 24 (with focus_on = 'B1' and method = "k_gmm")


   - **Compute q:** Determines the $q$ parameter, used to evaluate the relationship between direct and delegated voting patterns.

### 7. Liquid v. Direct
   - This section compares the outcomes between Liquid Democracy and Direct Democracy systems, analyzing differences in decision quality, representation accuracy, and expertise impact.
   - Figure 17 (with focus_on = 'B2')

### 8. Plot Delegation Graphs
   - This code plots delegation graphs shown across the manuscript.
   - Figure 1, 5, 6, 7, 8 (with focus_on = 'B2') and 23 (with focus_on = 'B1')

<br><br>
## Notebook Structure: `R_notebook_LiquidDemocracy.Rmd`

The `R_notebook_LiquidDemocracy.Rmd` notebook is organized into several sections, each focusing on a different aspect of the analysis, specifically related to Liquid Democracy. Below is an outline of the notebook structure and what each section covers:

### 1. Estimate Q
   - This section estimates the $q$ function and measures its statistical relation with the expertise levels $p_i$.
   - Result 6.3.2 
   - Tables 5 and 6 (with focus_on = 'B2')
   - Table 17 (with focus_on = 'B1')
   - Table 7

### 2. Estimate Phi
   - In this section, the $\varphi$ function is estimated, providing insights into the relationship between expertise and delegation patterns.
   - Figure 10 (3)


### 3. Estimate Competence Increase
   - This section evaluates the increase in competence due to delegation.
   - Figure 10 (1)

### 4. Estimate Gender Impact
   - This section investigates the impact of gender on voting behavior and delegation.
   - Figure 9, 10 (4/5)



