# cybersyn_sec_filing_llamaindex-snowflake-streamlit
Check out my blog [SEC 10-K Filings Analysis for Life Science Companies Leveraging Snowflake Marketplace, LlamaIndex, and Streamlit](https://medium.com/snowflake/sec-10-k-filings-analysis-for-life-science-companies-leveraging-snowflake-marketplace-llamaindex-f8ef99f18abd?sk=5ae1795acbffe3af4d7414c4a827ab85) for details.

## Application Setup

```
conda create --name py38_env --override-channels -c https://repo.anaconda.com/pkgs/snowflake python=3.8 numpy pandas
conda activate py38_env
pip install -r requirements.txt
```

Please note, the version incompatibility error is expected.  There is a known issue with ```snowflake-sqlalchem``` library.  Until that issue is resolved, we continue with our workaround from the ```utils.py``` file.  When we trigger the following ```streamlit run``` command to start our app, the workaround will take effect, thus allowing us to open our app in Streamlit for structured data analysis and unstructured data queries.

Be sure to change the snowflake_url to point to the actual Snowflake connection details before you run the app.
```
snowflake_uri = "snowflake://<username>:<password>@<org-account>/<database_name>/<schema_name>?warehouse=<warehouse_name>&role=<role_name>"
```

Also add `.env` file at the project root and replace placeholder with your API key:
```
OPENAI_API_KEY=<YOUR-API-KEY>
```

Now run the app by kicking off this command:
```
streamlit run secfilings.py
```

