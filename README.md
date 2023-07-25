# cybersyn_sec_filing_llamaindex-snowflake-streamlit
SEC 10-K Filings Analysis for Life Science Companies Leveraging Snowflake Marketplace, LlamaIndex, OpenAI, and Streamlit

## Application Setup

```
conda create --name py38_env --override-channels -c https://repo.anaconda.com/pkgs/snowflake python=3.8 numpy pandas
conda activate py38_env
pip install -r requirements.txt
```

Please note, the version incompatibility error is expected.  There is a known issue with ```snowflake-sqlalchem``` library.  Until that issue is resolved, we continue with our workaround from the ```utils.py``` file.  When we trigger the following ```streamlit run``` command to start our app, the workaround will take effect, thus allowing us to open our app in Streamlit for structured data analysis and unstructured data queries.

```
streamlit run secfilings.py
```

