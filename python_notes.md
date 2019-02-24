# Useful Links
- __[github.io guide](https://guides.github.com/features/pages/)__ - How to get started with github pages.
- __[markdown guide](https://markdown-it.github.io/)__ - Quick examples of markdown language
- __[Yong's Python notebook](https://yongks.github.io/python_book/)__ - Yong's notebook on Python
- __[github markdown guide](https://guides.github.com/features/mastering-markdown/)__ - Guide to mastering markdown

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
