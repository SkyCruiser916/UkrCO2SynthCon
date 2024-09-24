# **Impact of Carbon Taxation on Ukraine's CO2 Emissions: A Synthetic Control Approach**

This project explores the impact of carbon taxation on Ukraine's CO2 emissions using the **Synthetic Control Method (SCM)**. We utilize a combination of datasets, including CO2 per capita emissions, industrial CO2 emissions, and electricity consumption to assess the effectiveness of Ukraine's carbon tax policy implemented in 2011.

## **Table of Contents**
1. [Project Overview](#project-overview)
2. [Installation](#installation)
3. [Data Sources](#data-sources)
4. [Notebook Structure](#notebook-structure)
5. [Methodology](#methodology)
6. [How to Use](#how-to-use)
7. [Results](#results)
8. [Contributing](#contributing)

## **Project Overview**
Ukraine introduced a carbon tax in 2011, but its impact on reducing CO2 emissions remains unclear. Using the Synthetic Control Method, this project constructs a synthetic Ukraine from a pool of similar countries that did not implement carbon pricing during the study period (1995-2018). The aim is to estimate Ukraine’s CO2 emissions in the absence of the carbon tax and compare it with observed data post-2011.

## **Installation**

To get started with this project, you'll need to install the required packages and dependencies. Follow the steps below:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/SkyCruiser916/UkrCO2SynthCon.git
    cd your_repo_name
    ```

2. **Set up a Python virtual environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Download the dataset and change path:**

    Download the necessary CSV files from the `datasets` folder in this repository and save them to a local folder on your system.  You can find the files under:
    - `datasets/`

5. **Launch Jupyter Notebook:**

    ```bash
    jupyter notebook
    ```

6. **Open and run the notebook:**

    Once Jupyter opens, navigate to `ukrsynthcon`, change paths in the 'countries'
   dictionary to your local path and execute the cells.

## **Data Sources**
This project uses data from several sources:
- **International Energy Agency (IEA)**: CO2 emissions per capita, CO2 emissions by industry.
- **World Bank**: Energy intensity, renewable energy consumption, GDP per capita.

The combined dataset allows for a comprehensive analysis of Ukraine's CO2 emissions in relation to its carbon tax.

## **Notebook Structure**
The main analysis is conducted in `Project_notebook_final.ipynb`. The notebook is structured as follows:

1. **Data Import and Preprocessing**: 
   - Data from various sources (IEA, World Bank) are imported and cleaned.
   - Missing values are handled, and necessary columns are renamed for clarity.
   
2. **Synthetic Control Method Application**: 
   - SCM is used to create a synthetic Ukraine that mirrors Ukraine's CO2 emissions prior to the carbon tax.
   - Post-tax emissions are compared with the synthetic control group.

3. **Visualization of Results**: 
   - Graphs and plots are generated to visualize the differences between actual and synthetic CO2 emissions.
   
4. **Analysis and Interpretation**: 
   - Detailed discussion of the impact of the carbon tax based on the SCM results.

## **Methodology**
This project employs the **Augmented Synthetic Control Method (ASCM)**, an extension of the SCM, to account for potential biases and improve the accuracy of the counterfactual estimate. The methodology includes:
- **Data Preprocessing**: Cleaning and organizing data into a format suitable for analysis.
- **SCM Construction**: Selecting a pool of countries and generating synthetic control units based on pre-treatment characteristics (e.g., CO2 emissions, energy consumption).
- **Augmented SCM**: Utilizing ridge-regularized regression to account for imperfect pre-treatment fit.

The goal is to estimate the causal impact of Ukraine’s carbon tax by comparing post-2011 emissions with the synthetic control group.

## **How to Use**

### Running the Notebook
To run the analysis:
1. Follow the **installation** steps above.
2. Download the required datasets from the `datasets` folder and ensure they are accessible from the notebook.
3. Open the notebook: `Project_notebook_final.ipynb`.
4. Run each cell in order.

### Files:
- **`ukrsynthcon.ipynb`**: The main analysis notebook.
- **`ukrsynthcon_report.pdf`**: The accompanying report detailing the methodology and results of the study.
- **`datasets/`**: A folder containing all the project datasets (CO2 emissions, energy consumption, etc.) used for the analysis.

## **Results**
The analysis reveals that the **Average Treatment Effect on the Treated (ATT)** of Ukraine’s carbon tax is estimated to be **-0.0137 tons of CO2 per capita**, indicating a small negative effect on CO2 emissions. However, this result is not statistically significant, as the standard error of the estimate is **0.1005**. 

### Key Insights:
- The negative ATT suggests a small reduction in CO2 emissions per capita following the implementation of the carbon tax. 
- Given the large standard error relative to the ATT, this reduction is **not statistically significant**, meaning we cannot confidently attribute any observed changes in emissions solely to the carbon tax policy.
- This aligns with findings from other studies that show **low taxation rates** are generally insufficient to create a meaningful impact on emissions reduction.

### Conclusion:
The **lack of significant results** highlights the potential need for a higher carbon tax rate or supplementary policies to achieve measurable reductions in CO2 emissions. Further research could focus on examining the impact across different sectors or regions within Ukraine to better understand the specific dynamics at play.

## **Contributing**
If you have suggestions or want to contribute, feel free to open an issue or submit a pull request. Contributions are welcome!
