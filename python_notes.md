# Useful Links
- __[github.io guide](https://guides.github.com/features/pages/)__ - How to get started with github pages.
- __[markdown guide](https://markdown-it.github.io/)__ - Quick examples of markdown language
- __[Yong's Python notebook](https://yongks.github.io/python_book/)__ - Yong's notebook on Python
- __[github markdown guide](https://guides.github.com/features/mastering-markdown/)__ - Guide to mastering markdown

# Installation
## Pylauncher
- __[Pylauncher doc](https://www.python.org/dev/peps/pep-0397/)__
- __[Pylauncher download](https://bitbucket.org/vinay.sajip/pylauncher)__
- __[Simpler Explanation of Pylauncher](https://blog.python.org/2011/07/python-launcher-for-windows_11.html)__

The launcher allows Python scripts (.py and .pyw files) on Windows to specify the version of Python which should be used, allowing simultaneous use of Python 2 and 3.

Windows CMD, key in `py -2 xy123.py` to run python code using version 2.7. Key in `py -3 xy123.py` to run with version 3.7

## Pip 
Key in below in Win CMD to add pip path to environment variables.
    
    setx PATH "%PATH%;C:\python37\Scripts"

Upgrade pip using:
    
    py -3 -m pip install --upgrade pip
    
Without downloading package, install from internet:
    
    py -3 -m pip install requests

# Requests
## Passing parameters in URL
- __[Requests - Passing parameters in URL](http://docs.python-requests.org/en/master/user/quickstart/#passing-parameters-in-urls)__ 

You often want to send some sort of data in the URL’s query string. If you were constructing the URL by hand, this data would be given as key/value pairs in the URL after a question mark, e.g. httpbin.org/get?key=val. Requests allows you to provide these arguments as a dictionary of strings, using the params keyword argument. As an example, if you wanted to pass key1=value1 and key2=value2 to httpbin.org/get, you would use the following code:

    payload = {'key1': 'value1', 'key2': 'value2'}
    r = requests.get('https://httpbin.org/get', params=payload)
    
You can see that the URL has been correctly encoded by printing the URL:

    print(r.url)
    https://httpbin.org/get?key2=value2&key1=value1
    
Note that any dictionary key whose value is None will not be added to the URL’s query string.

You can also pass a list of items as a value:

    payload = {'key1': 'value1', 'key2': ['value2', 'value3']}

    r = requests.get('https://httpbin.org/get', params=payload)
    print(r.url)
    https://httpbin.org/get?key1=value1&key2=value2&key2=value3


# Pandas
## Dataframe summaries
__Data Types__: `df.dtypes`

## to_csv
Below *with open* method opens a `.csv` file with `'a'` to append data to file. Opening the `.csv` file the dataframe will be organized based on its delimiter. This means no need to delimit the file. However somehow it introduces empty rows after each data row.

_with open_ method will automatically 'close'.

    with open('test.csv', 'a') as f:' 
        df3.to_csv(f, header=False, index=False)` 

Below implementation of `to_csv` will create a file with default separator "," between attributes and looks very close to CSV format. 
`df3.to_csv('test1', header=False, index=False)` 

# Time and Date 
## UTC 
Using `import datetime` package:

    today = dt.datetime.utcnow()
    df3['UpdateDate'] = today
    
Using `import pandas as pd` package:

    today = pd.Timestamp.utcnow()
    df3['UpdateDate'] = today
    
# Python Data Formatting
## Rename Single Column
Example below:

    df3.rename(columns={'Last Price': 'LastPrice'}, inplace=True)
    df3.rename(columns={'% Change': 'ChgPct'}, inplace=True)

## Change Column Data Type
    df3['ChgPct'] = df3['ChgPct'].astype(float)

## Test