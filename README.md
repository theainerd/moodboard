# moodboard
Sentiment Analysis for Fashion products 

## Project Structure 

```
News Analysis/
│
├── data/                                      # Input Files
├── cleaned_data/                              # Cleaned Data   
├── notebook/                                   # Ipython Notebooks
│   └── 01 BERT_for_sentiment_analysis.ipynb (GPU)
|   └── 02 DataExtraction.ipynb (CPU)
├── docs/
|   └── 01 Documentation_Sentiment_Analysis.pdf                                              
├── MLOps/                                     # All model deployment related files
└── README.md
└── requirements.txt
```

## Model Building

All the work has been done on google colab and can be easily run on CPU for data cleaning tasks and GPU for model building.

- First we need to clean and prepare data for model building. Run `DataExtraction.ipynb` to extract cleaned data. 
- Run `BERT_for_sentiment_analysis.ipynb` for model building. 

## Model Deployment

We have used Pytorch Serve to serve our model. All the details to run our model is in `ModelDeployment.ipynb`

## Predictions

After deploying our model we can make predictions by doing a POST request to our API endpoint (in our case 8085).

```bash
!curl http://127.0.0.1:8085/predictions/my_tc -T sample_text.txt
```
