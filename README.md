# Response Coding
It calculates response ratio of each category for every Target Label. One column per target class is returned.

## Scenario: 
   > Binary classification. Positive class is labelled `1` and Negative class is labelled `0`. 
   > Transformer will output one column for each target class.
   > The ouput will be ordered Lexicographically. Thus the columns will correspond to the 
   > classes `0` and `1` respectively.
#### Code Example:
``` python

    from response_encoding.ResponseEncoder import ResponseCoding
    
    vectorizer = ResponseCoding()

    # For training data
    categories_response_coded = vectorizer.fit_transform(X_train.feature_column, y_train])
    
    # Get for class = 1 (Accepted)
    categories_train = categories_response_coded[1]

                                OR

    vectorizer.fit(X_train.feature_column, y_train)
    categories_response_coded = vectorizer.transform(X_train.feature_column)
    categories_train = categories_response_coded[1]                                         
    
    
    # For testing data
    # Get for class = 1 (Accepted)
    categories_test = vectorizer.transform(X_test.feature_column)[1]
```
### Installation

```sh
$ pip install response_encoding
```
Run the above line in either terminal or in a conda command line.

License
-------
GNU GPL V3

Acknowledgement
---------------
This markdown was created with the help of `dillinger.io`