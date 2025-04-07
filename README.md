# Wiki-Dialogue Dataset

## Overview 
The dataset contains data and text pairs where the data is a set of triples extracted primarily from WikiDATA, except for the animals domain which triples are extracted from API Ninjas.

The Wiki-Dialogue dataset contains 71  training examples sets of dialogue acts whose content is specified by  sets of relational triples (intended to be used as input to an NLG engine)  and natural language generation realizations, which are examples of a possible output from an NLG engine realizing an utterance whose dialogue act was specified in the input and whose content completely covers the set of relational triples. 

Wiki-Dialogue  provides a total of 71K training examples, where each example represents a knowledge grounded conversational turn realizing one of 9 different possible dialogue acts that are highly useful in dialogue to enable a system to engage in interesting mixed initiative conversations (inform, confirm, give_opinion, recommend, request, request attribute, request explanation, suggest, and verify attribute). These are the same set of dialogue acts used in the ViGGo corpus (https://huggingface.co/datasets/GEM/viggo)

The relational triples which provide the *content* for each dialogue act, cover seven different domains, namely
Movies (Movies, Movie Actors), Music (Songs, Albums, Musicians), Sports (Athlete, Sports Team), TV (TV Shows, TV Actors), Board Games (Board Games), Animals (Wild Animals, Cats, Dogs), and Art (Paintings and Painters). 
For each domain, multiple entity types are covered, so for example for the Music domain, an output utterance can consist of content related to Songs, Albums, or Musicians, where each entity type functions as the head of all the relational triples that the utterance realizes, e.g. (Album genre genre-type). 

The relational triples are  extracted primarily from WikiDATA, except for the Animals domain where the relational triples were extracted from API Ninjas. 

## Characteristics of Wiki-Dialogue

### Hops and Shapes of the Data
Hops are..
Shapes are .. WebNLG 
#### Movies

|   |  |  Movies  | | Movie Actor | | 
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | 
| DA  | No. Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | 
| inform  | 3-8  | name, genres  |  1-3 |  name  |  1-3  | 
| confirm  | 2-3 | name   | 1  | name   | 1  |  
| give_opinion  | 3-5  | name, rating   | 1-3 | name, rating   | 1-3  | 
| recommend  | 2-3  | name, rating   | 1-2 | name, rating   | 1-2 | 
| request  | 1-2  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  |-  | 1  | -  | 1  | 
| request explanation | 2-3  | rating  | 1-2  | name, rating  | 1-2  | 
| suggest  | 2-3  | name   | 1  | name   | 1-2  | 
| verify attribute  | 3-4  | name, rating   | 1-2 |  name, rating   | 1-2 |  

#### Music  
|   |  |  Albums| |  Musician  | |  Songs | |   
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | ------------- | ------------- | 
| DA  | No. Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops | 
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1-3  |  name, genres  |  1-3  | 
| confirm  | 2-3 | name   | 1  | name   | 1  |  name   | 1  |  name   | 1  |  
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | name, rating   | 1-3  |
| recommend  | 2-3  | name   | 1  | name   | 1 -2 | name, rating   | 1-2 |  
| request  | 1-2  | specifier   | 1  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  |-  | 1  | -  | 1  | -  | 1  |
| request explanation | 2-3  | rating  | 1  | name, rating  | 1-2 | rating  | 1-2  | 
| suggest  | 2-3  | name   | 1  | name   | 1-2 | name   | 1-2 | name   | 1-2 |
| verify attribute  | 3-4  | name, rating   | 1 |  name, rating   | 1-2 |   name, rating   | 1-2 |

#### Sports

|   |  |  Athlete | |   Sports Team | |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | 
| DA  | No. Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | 
| inform  | 3-8  | name, sport  |  1-3  |  name, sport  |  1-3  |  
| confirm  | 2-3 | name, sport   | 1  | name, sport   | 1  |  
| give_opinion  | 3-5  | name, rating, sport   | 1-3  | name, rating, sport   | 1-3  | 
| recommend  | 2-3  | name, sport   | 1-2  | name, rating   | 1-2 | 
| request  | 1-2  | specifier   | 1  | specifier | 1  | 
| request attribute | 1  | -  | 1  | -  | 1  | 
| request explanation | 2-3  | name, rating  | 1-2  | rating  | 1-2  |
| suggest  | 2-3  | name   | 1-2  | name   | 1-2  |
| verify attribute  | 3-4  | name, rating   | 1-2  |  name, rating   | 1-2  |  

#### TV
|   |  | TV Actor | |  TV Show  | | 
| ------------- | ------------- |------------- | ------------- |------------- | ------------- |
| DA  | No. Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | 
| inform  | 3-8  | name  |  1-3 |  name, genres  |  1-3  |  
| confirm  | 2-3 | name   | 1  | name   | 1  |  
| give_opinion  | 3-5  | name, rating   | 1-3  | name, rating   | 1-3  | 
| recommend  | 2-3  | name, rating   | 1-2  | name, rating   | 1-2 | 
| request  | 1-2  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  | -  | 1  | -  | 1  |  
| request explanation | 2-3  | name, rating  | 1-2  | name, rating  | 1-2  | 
| suggest  | 2-3  | name   | 1-2  | name   | 1-2  | 
| verify attribute  | 3-4  | name, rating   | 1-2  |  name, rating   | 1-2  |  

#### Board Games 

|   |  | Board Games| |
| ------------- | ------------- |------------- | ------------- |
| DA  | No. Slots | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1-3  | 
| confirm  | 2-3 | name   | 1  |
| give_opinion  | 3-5  | name, rating   | 1-3  | 
| recommend  | 2-3  | name   | 1-2  | 
| request  | 1-2  | specifier   | 1  | 
| request attribute | 1  |-  | 1  | 
| request explanation | 2-3  | genres, rating  | 1-2  | 
| suggest  | 2-3  | name   | 1-2  | 
| verify attribute  | 3-4  | name, rating   | 1-2  |  
#### Animals
|   |  | Wild Animals | |  Cats | | Dogs| |
| ------------- | ------------- |------------- | ------------- |------------- | ------------- | ------------- | ------------- | 
| DA  | No. Slots | Mandatory Slots | Hops | Mandatory Slots | Hops | Mandatory Slots | Hops |
| inform  | 3-8  | name, genres  |  1  |  name, genres  |  1-3  |  name, genres  |  1 -3  |
| confirm  | 2-3 | name   | 1  | name   | 1  |  name   | 1  | 
| give_opinion  | 3-5  | name, rating   | 1  | name, rating   | 1-3  | name, rating   | 1-3  |
| recommend  | 2-3  | name   | 1  | name, rating   | 1 -2 | name, rating   | 1-2 |
| request  | 1-2  | specifier   | 1  | specifier   | 1  | specifier   | 1  | 
| request attribute | 1  |-  | 1  | -  | 1  | -  | 1  | 
| request explanation | 2-3  | rating  | 1  | rating  | 1  | rating  | 1  |
| suggest  | 2-3  | name   | 1  | name   | 1  | name   | 1  |
| verify attribute  | 3-4  | name, rating   | 1  |  name, rating   | 1  |   name, rating   | 1  | 

#### Art
|   |  | Paintings| |
| ------------- | ------------- |------------- | ------------- |
| DA  | No. Slots | Mandatory Slots | Hops |
| inform  | 3-7  | name, creator  |  1  | 
| confirm  | 3-4 | name, creator   | 1  |
| give_opinion  | 3-4  | name, rating   | 1  | 
| recommend  | 3-4  | name   | 1  | 
| request  | 1-2  | specifier   | 1  | 
| request attribute | 1  | -  | 1  | 
| request explanation | 2-3  | rating  | 1  | 
| suggest  | 2-3  | name   | 1  | 
| verify attribute  | 3-4  | name, rating   | 1  |  

|   |  | Painters | |
| ------------- | ------------- |------------- | ------------- |
| DA  | No. Slots | Mandatory Slots | Hops |
| inform  | 3-7  | name, notable works  |  1  | 
| confirm  | 2-3 | name   | 1  |
| give_opinion  | 3-4  | name, rating   | 1  | 
| recommend  | 2-3  | name   | 1  | 
| request  | 1-2  | specifier   | 1  | 
| request attribute | 1  | -  | 1  | 
| request explanation | 2-3  | rating  | 1  | 
| suggest  | 2-3  | name   | 1  | 
| verify attribute  | 3-4  | name, rating   | 1  |  
