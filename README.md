# KG-NLG-DA Dataset

## Overview 
This is the official repository for the KG-NLG-DA dataset. The dataset contains data and text pairs where the data is a set of triples extracted primarily from WikiDATA, except for the animals domain which triples are extracted from API Ninjas. 


## Hops and Shapes 

Hops are..
Shapes are .. WebNLG 
### Movies

|   |  |  Movies  | | Movie Actor | | 
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | 
| DA  | NUM Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | 
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1 - 3  | 
| confirm  | 2-3 | name   | 1  | name   | 1  |  
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | 
| recommend  | 2-3  | name   | 1  | name, rating   | 1 -2 | 
| request  | 1-2  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  | -   | 1  |  -   | 1  | 
| request explanation | 2-3  | rating  | 1  | rating  | 1  | 
| suggest  | 2-3  | name   | 1  | name   | 1  | 
| verify attribute  | 3-4  | name, rating   | 1  |  name, rating   | 1  |  

### Music  
|   |  |  Album| |  Musician  | |  Athlete | |   Sports Team | |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | ------------- | ------------- | ------------- | ------------- | 
| DA  | NUM Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1 - 3  |  name, genres  |  1 -3  | name, genres  |  1 -3  |
| confirm  | 2-3 | name   | 1  | name   | 1  |  name   | 1  |  name   | 1  |  
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | name, rating   | 1-3  | name, rating   | 1-3  |
| recommend  | 2-3  | name   | 1  | name, rating   | 1 -2 | name, rating   | 1-2 |  name, rating   | 1-2 |
| request  | 1-2  | specifier   | 1  | specifier   | 1  | specifier   | 1  | specifier   | 1  |
| request attribute | 1  | -   | 1  |  -   | 1  |  -   | 1  |  -   | 1  | 
| request explanation | 2-3  | rating  | 1  | rating  | 1  | rating  | 1  | rating  | 1  |
| suggest  | 2-3  | name   | 1  | name   | 1  | name   | 1  | name   | 1  |
| verify attribute  | 3-4  | name, rating   | 1  |  name, rating   | 1  |   name, rating   | 1  | name, rating   | 1  |

### Sports

### TV
|   |  | TV Actor | |  TV Show  | | Board Games| |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | ------------- | ------------- | 
| DA  | NUM Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1 - 3  |  name, genres  |  1 -3  |
| confirm  | 2-3 | name   | 1  | name   | 1  |  name   | 1  | 
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | name, rating   | 1-3  |
| recommend  | 2-3  | name   | 1  | name, rating   | 1 -2 | name, rating   | 1-2 |
| request  | 1-2  | specifier   | 1  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  | -   | 1  |  -   | 1  |  -   | 1  | 
| request explanation | 2-3  | rating  | 1  | rating  | 1  | rating  | 1  |
| suggest  | 2-3  | name   | 1  | name   | 1  | name   | 1  |
| verify attribute  | 3-4  | name, rating   | 1  |  name, rating   | 1  |   name, rating   | 1  |

### Board Games 

|   |  | Board Games| |
| ------------- | ------------- |------------- | ------------- |
| DA  | NUM Slots | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1  | 
| confirm  | 2-3 | name   | 1  |
| give_opinion  | 3-5  | name, rating   | 1  | 
| recommend  | 2-3  | name   | 1  | 
| request  | 1-2  | specifier   | 1  | 
| request attribute | 1  | -   | 1  | 
| request explanation | 2-3  | rating  | 1  | 
| suggest  | 2-3  | name   | 1  | 
| verify attribute  | 3-4  | name, rating   | 1  |  
### Animals
|   |  | Wild Animals | |  Cats | | Dogs| |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | ------------- | ------------- | 
| DA  | NUM Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1 - 3  |  name, genres  |  1 -3  |
| confirm  | 2-3 | name   | 1  | name   | 1  |  name   | 1  | 
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | name, rating   | 1-3  |
| recommend  | 2-3  | name   | 1  | name, rating   | 1 -2 | name, rating   | 1-2 |
| request  | 1-2  | specifier   | 1  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  | -   | 1  |  -   | 1  |  -   | 1  | 
| request explanation | 2-3  | rating  | 1  | rating  | 1  | rating  | 1  |
| suggest  | 2-3  | name   | 1  | name   | 1  | name   | 1  |
| verify attribute  | 3-4  | name, rating   | 1  |  name, rating   | 1  |   name, rating   | 1  | 

### Art
|   |  | Painters | |  Paintings | | | |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | ------------- | ------------- | 
| DA  | NUM Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1 - 3  |  name, genres  |  1 -3  |
| confirm  | 2-3 | name   | 1  | name   | 1  |  name   | 1  | 
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | name, rating   | 1-3  |
| recommend  | 2-3  | name   | 1  | name, rating   | 1 -2 | name, rating   | 1-2 |
| request  | 1-2  | specifier   | 1  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  | -   | 1  |  -   | 1  |  -   | 1  | 
| request explanation | 2-3  | rating  | 1  | rating  | 1  | rating  | 1  |
| suggest  | 2-3  | name   | 1  | name   | 1  | name   | 1  |
| verify attribute  | 3-4  | name, rating   | 1  |  name, rating   | 1  |   name, rating   | 1  | 
