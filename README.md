# ORTEGA-PySpark

ORTEGA-PySpark is a Spark-based geo-computational tools to optimize time geography to movement interaction analysis. It enhances the [ORTEGA Python Package](https://github.com/move-ucsb/ORTEGA) using GeoAnalytics Engine and leveraging Spark-based distributed computing to scale up its anlytical capabilities for larger datasets. Around 2 million GPS tracking data of 84 turkey vultures collected from 2003 to 2023 are used as a case study. 

Citation info:
> Su, R., Liu, Y. & Dodge, S. (2024). [ORTEGA v1.0: an open-source Python package for context-aware interaction analysis using movement data](https://doi.org/10.1186/s40462-024-00460-2). *Movement Ecology* 12, 20.
>
> Bildstein KL, Barber D, Bechard MJ, Graña Grilli M, Therrien J. (2021). Data from: [Study "Vultures Acopian Center USA GPS" (2003-2021)](https://doi.org/10.1186/s40462-021-00274-6). [Movebank Data Repository](https://doi.org/10.5441/001/1.f3qt46r2) 
> 
> Liu, Y., Battersby S., & Dodge, S. (under review). Scaling up time-geographic computation for movement interaction analysis.

## Data

The dataset associated with this project is too large for direct inclusion in this GitHub repository. Please download the data from [Movebank Data Repository](https://doi.org/10.5441/001/1.f3qt46r2) to replicate the analysis. Unzip the folder and all the contents and store in your directory as follows. 

```         
ORTEGA-PySpark
│   README.md
│   LICENSE
└───Code
    │   Create_PPA.ipynb
    │   Interaction_Analysis.ipynb
    │   Performace_Evaluation.ipynb
    |   Configurations.md
    │       
└───Result_parquet
    │   concurrent_events_All.parquet
    │   concurrent_intersect_PPAs_All.parquet
    │   delay_1d/1w/2w/3w/4w_events_All.parquet
    │   delay_1d/1w/2w/3w/4w_intersect_PPAs_All.parquet
    |   metadata sheet.xlsx
```

## Getting Started

1. **Clone the Repository**: Clone or download this repository to your local computer.
2. **Date Setup**: Download the vulture tracking data from the above link and place it in the `Data` directory.
3. **Generate PPAs**: Open the jupyter notebook file `Create_PPA.ipynb` in the `Code` directory to view and generate PPAs from tracking data. Ensure you have installed all necessary libraries.
4. **Run the Interaction Analysis**: Open the jupyter notebook file `Interaction_Analysis.ipynb` in the `Code` directory to run the concurrent and delayed interaction analysis. The descriptions of the output columns for "events" and "intersect_PPAs" parquet are shown in [metadata sheet](https://github.com/move-ucsb/ORTEGA-PySpark/blob/main/Result_parquet/metadata%20sheet.xlsx). 

## License
ORTEGA-PySpark is licensed under the MIT license. See the [LICENSE](https://github.com/move-ucsb/ORTEGA-PySpark/blob/main/LICENSE) file for details.
