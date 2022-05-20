# DataDistillr Python SDK

[![Total alerts](https://img.shields.io/lgtm/alerts/g/datadistillr/datadistillr-python-sdk.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/datadistillr/datadistillr-python-sdk/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/datadistillr/datadistillr-python-sdk.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/datadistillr/datadistillr-python-sdk/context:python)

This library allows you to programmatically interact with DataDistillr.  It is quite simple to programmatically pull data 
from DataDistillr for use in machine learning. 

### Methods
#### Datadistillr
* `get_dataframe(url, auth_token)`: Pulls your data and returns it in a Pandas DataFrame.
* `get_csv_from_api(url, auth_token, filename)`:  Pulls your data and returns it in a CSV file.
* `get_json_from_api(url, auth_token, filename)`:  Pulls your data and returns it in a JSON file.
* `get_parquet_from_api(url, auth_token, filename)`:  Pulls your data and returns it in a parquet file.
* `get_excel_from_api(url, auth_token, filename)`:  Pulls your data and returns it in an Excel file.
* `get_dict_from_api(url, auth_token, filename)`:  Pulls your data and returns it in a Python dictionary.

#### DatadistillrAccount
* `logout()`:  Logs you out of DataDistillr account.
* `get_projects()`:  Returns all projects in DataDistillr account as a list of Project objects.
* `get_project_token_dict()`: Returns dictionary with project tokens as keys and project names as values.
* `get_project(project_token)`:  Returns project object identified by project_token.
* `get_organizations()`:  Returns list organizations that DataDistillr account has access to.

#### Project
Note: A tab in the DataDistillr user interface is equivalent to a query barrel in API routes and responses. All public functions use the phrasing "tab" while all private functions use "query barrel"
* `get_tab_token_dict()`: Returns dictionary with tab tokens as keys and tab names as values.
* `execute_existing_query(tab_token)`: Executes the most recent query in the tab identified by tab_token.
* `execute_new_query(tab_name, query)`: Creates new tab named tab_name and executes query in new tab.
* `get_data_source_token_dict()`: Returns dictionary with data source tokens as keys and data source names as values. 
* `upload_files(data_source_token, file_paths)`: Uploads files to a data source. file_paths must be a list of absolute file path strings.


### Getting your Endpoint URL and Authorization Token
See https://docs.datadistillr.com/ddr/ for complete documentation on obtaining the URL and Auth Token.

### Usage 
Using the SDK in Python code is quite simple.  See the snippet below:
```python
import datadistillr.Datadistillr as ddr
url = <Your URL From DataDistillr>
auth_token = <AUTH TOKEN>
dataframe = ddr.datadistillr.get_dataframe(url, auth_token)
```