# Wiki-Dialogue Dataset

## Overview 

Wiki-Dialogue  provides a total of 71K training pairs, where each pair represents a knowledge grounded conversational turn realizing one of 9 different possible dialogue acts that are highly useful in dialogue because they enable a system to engage in interesting mixed initiative conversations. The dialogue acts are: inform, confirm, give_opinion, recommend, request, request attribute, request explanation, suggest, and verify attribute. These are the same set of dialogue acts used in the ViGGo corpus (https://huggingface.co/datasets/GEM/viggo)

Each training pair consists of the dialogue act (DA) with its knowledge-grounding (KG) along with a natural language generation (NLG) realization of that DA-KG specification. The knowledge for each DA is specified by  a set of relational triples and the NLG realization is a highly-ranked output from an LLM or NLG engine that realizes an utterance whose DA was specified in the input and whose content completely covers the set of relational triples. 

The relational triples which provide the *content* for each dialogue act, cover seven different domains, namely
Movies (Movies, Movie Actors), Music (Songs, Albums, Musicians), Sports (Athlete, Sports Team), TV (TV Shows, TV Actors), Board Games (Board Games), Animals (Wild Animals, Cats, Dogs), and Art (Paintings and Painters). 
For each domain, multiple entity types are covered, so for example for the Music domain, an output utterance can consist of content related to Songs, Albums, or Musicians, where each entity type functions as the head of all the relational triples that the utterance realizes, e.g. (albums genre genre-type). 

The relational triples are  extracted primarily from WikiDATA, except for the Animals domain where the relational triples were extracted from API Ninjas. 
## Citation and Paper 
Creation of Dataset is described in these papers. 




Paper Link for Wiki-Dialogue:  https://aclanthology.org/2024.sigdial-1.7.pdf
```bibtex
@inproceedings{vazquez-risco-etal-2024-knowledge,
    title = "Knowledge-Grounded Dialogue Act Transfer using Prompt-Based Learning for Controllable Open-Domain {NLG}",
    author = "Vazquez Risco, Alain  and
      Ramirez, Angela Maria  and
      Pullabhotla, Neha  and
      Qiang, Nan  and
      Zhang, Haoran  and
      Walker, Marilyn  and
      Torres, Maria Ines",
    editor = "Kawahara, Tatsuya  and
      Demberg, Vera  and
      Ultes, Stefan  and
      Inoue, Koji  and
      Mehri, Shikib  and
      Howcroft, David  and
      Komatani, Kazunori",
    booktitle = "Proceedings of the 25th Annual Meeting of the Special Interest Group on Discourse and Dialogue",
    month = sep,
    year = "2024",
    address = "Kyoto, Japan",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.sigdial-1.7/",
    doi = "10.18653/v1/2024.sigdial-1.7",
    pages = "78--91",
    abstract = "Open domain spoken dialogue systems need to controllably generate many different dialogue acts (DAs) to allow Natural Language Generation (NLG) to create interesting and engaging conversational interactions with users. We aim to create an NLG engine that can produce a variety of DAs that make substantive knowledge-grounded contributions to a conversation. Training such an NLG typically requires dialogue corpora that are labelled for DAs, which are expensive to produce and vulnerable to quality issues. Here, we present a prompt-based learning approach to transfer DAs from one domain, video games, to 7 new domains. For each novel domain, we first crawl WikiData to create Meaning Representations that systematically vary both the number of attributes and hops on the WikiData Knowledge Graph. The proposed method involves a self-training step to create prompt examples for each domain followed by an overgeneration and ranking step. The result is a novel, high-quality dataset, Wiki-Dialogue, of 71K knowledge-grounded utterances, covering 9 DAs and the Art, Movies, Music, Sports, TV, Animal, and Boardgames domains, whose combined DA and semantic accuracy is 89{\%}. We assess the corpus quality using both automatic and human evaluations and find it high. The corpus is found to be safe, lexically rich, and large in vocabulary, when compared to similar datasets."
}
```

Paper Link for Methodology: https://aclanthology.org/2023.sigdial-1.32.pdf
```bibtex
@inproceedings{ramirez-etal-2023-controllable,
    title = "Controllable Generation of Dialogue Acts for Dialogue Systems via Few-Shot Response Generation and Ranking",
    author = "Ramirez, Angela  and
      Agarwal, Kartik  and
      Juraska, Juraj  and
      Garg, Utkarsh  and
      Walker, Marilyn",
    editor = "Stoyanchev, Svetlana  and
      Joty, Shafiq  and
      Schlangen, David  and
      Dusek, Ondrej  and
      Kennington, Casey  and
      Alikhani, Malihe",
    booktitle = "Proceedings of the 24th Annual Meeting of the Special Interest Group on Discourse and Dialogue",
    month = sep,
    year = "2023",
    address = "Prague, Czechia",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.sigdial-1.32/",
    doi = "10.18653/v1/2023.sigdial-1.32",
    pages = "355--369",
    abstract = "Dialogue systems need to produce responses that realize multiple types of dialogue acts (DAs) with high semantic fidelity. In the past, natural language generators (NLGs) for dialogue were trained on large parallel corpora that map from a domain-specific DA and its semantic attributes to an output utterance. Recent work shows that pretrained language models (LLMs) offer new possibilities for controllable NLG using prompt-based learning. Here we develop a novel few-shot overgenerate-and-rank approach that achieves the controlled generation of DAs. We compare eight few-shot prompt styles that include a novel method of generating from textual pseudo-references using a textual style transfer approach. We develop six automatic ranking functions that identify outputs with both the correct DA and high semantic accuracy at generation time. We test our approach on three domains and four LLMs. To our knowledge, this is the first work on NLG for dialogue that automatically ranks outputs using both DA and attribute accuracy. For completeness, we compare our results to fine-tuned few-shot models trained with 5 to 100 instances per DA. Our results show that several prompt settings achieve perfect DA accuracy, and near perfect semantic accuracy (99.81{\%}) and perform better than few-shot fine-tuning."
}
```

## Characteristics of Wiki-Dialogue

### Hops and Shapes of the Data
Hops are..
Shapes are .. WebNLG 
#### Movies

|              |                 |       Movies        |                     |                     |     Movie Actor     |                     |
|--------------|-----------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| DA           | Slots           | Mandatory Slots     | Hops                | Slots               | Mandatory Slots     | Hops                |
| inform       | 3-9             | name, genres        | 1-3                 | 3-8                 | name                | 1-3                 |
| confirm      | 2-3             | name                | 1                   | 2-3                 | name                | 1                   |
| give_opinion | 3-5             | name, review score  | 1-3                 | 3-5                 | name, rating        | 1-3                 |
| recommend    | 2-3             | name, review score  | 1-2                 | 2-3                 | name, rating        | 1-2                 |
| request      | 1-2             | specifier           | 1                   | 1-2                 | specifier           | 1                   |
| request attribute | 1          | -                   | 1                   | 1                   | -                   | 1                   |
| request explanation | 2-3      | review score        | 1-2                 | 2-3                 | name, rating        | 1-2                 |
| suggest      | 2-3             | name                | 1-2                 | 2-3                 | name                | 1-2                 |
| verify attribute | 3-4         | name, review score  | 1-2                 | 3-4                 | name, rating        | 1-2                 |
 

#### Music  
|              |                 |       Albums        |                     |                     |     Musician       |                     |                     |     Songs          |                     | 
|--------------|-----------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| DA           | Slots           | Mandatory Slots     | Hops                | Slots               | Mandatory Slots     | Hops                | Slots               | Mandatory Slots     | Hops                |
| inform       | 3-8             | name, genres        | 1                   | 3-8                 | name, genres        | 1-3                 | 3-8                 | name, genres        | 1-3                 |
| confirm      | 2-3             | name                | 1                   | 2-3                 | name                | 1                   | 2-3                 | name                | 1                   |
| give_opinion | 3-5             | name, rating        | 1                   | 3-5                 | name, rating        | 1-3                 | 3-5                 | name, rating        | 1-3                 |
| recommend    | 2-3             | name                | 1                   | 2-3                 | name                | 1-2                 | 2-3                 | name, rating        | 1-2                 |
| request      | 1-2             | specifier           | 1                   | 1-2                 | specifier           | 1                   | 1-2                 | specifier           | 1                   |
| request attribute | 1         | -                   | 1                   | 1                   | -                   | 1                   | 1                   | -                   | 1                   |
| request explanation | 2-3     | rating              | 1                   | 2-3                 | name, rating        | 1-2                 | 2-3                 | rating              | 1-2                 |
| suggest      | 2-3             | name                | 1                   | 2-3                 | name                | 1-2                 | 2-3                 | name                | 1-2                 |
| verify attribute | 3-4         | name, rating        | 1                   | 3-4                 | name, rating        | 1-2                 | 3-4                 | name, rating        | 1-2                 |


#### Sports

| DA           |           | Athlete       |           |           | Sports Team    |           |
|--------------|-----------|---------------|-----------|-----------|----------------|-----------|
|              | Slots     | Mandatory Slots | Hops     | Slots     | Mandatory Slots | Hops     |
| inform       | 3-8       | name, sport     | 1-3      | 3-8       | name, sport     | 1-3      |
| confirm      | 3-4       | name, sport     | 1        | 3-4       | name, sport     | 1        |
| give_opinion | 3-5       | name, rating, sport | 1-3  | 3-5       | name, rating, sport | 1-3  |
| recommend    | 3-4       | name, sport     | 1-2      | 3-4       | name, rating    | 1-2      |
| request      | 1-2       | specifier       | 1        | 1-2       | specifier       | 1        |
| request attribute | 1    | -               | 1        | 1         | -               | 1        |
| request explanation | 2-3 | name, rating  | 1-2      | 2-3       | rating          | 1-2      |
| suggest      | 2-3       | name            | 1-2      | 2-3       | name            | 1-2      |
| verify attribute | 3-4  | name, rating     | 1-2      | 3-4       | name, rating    | 1-2      |


#### TV

| DA           |           | TV Actor       |           |           | TV Show         |           |
|--------------|-----------|----------------|-----------|-----------|-----------------|-----------|
|              | Slots     | Mandatory Slots | Hops     | Slots     | Mandatory Slots | Hops     |
| inform       | 3-8       | name            | 1-3      | 3-8       | name, genres     | 1-3      |
| confirm      | 2-3       | name            | 1        | 2-3       | name             | 1        |
| give_opinion | 3-5       | name, rating    | 1-3      | 3-5       | name, rating     | 1-3      |
| recommend    | 2-3       | name, rating    | 1-2      | 2-3       | name, rating     | 1-2      |
| request      | 1-2       | specifier       | 1        | 1-2       | specifier        | 1        |
| request attribute | 1    | -               | 1        | 1         | -                | 1        |
| request explanation | 2-3 | name, rating  | 1-2      | 2-3       | name, rating     | 1-2      |
| suggest      | 2-3       | name            | 1-2      | 2-3       | name             | 1-2      |
| verify attribute | 3-4  | name, rating     | 1-2      | 3-4       | name, rating     | 1-2      |


#### Board Games

| DA           |           | Board Games     |           |
|--------------|-----------|-----------------|-----------|
|              | Slots     | Mandatory Slots | Hops     |
| inform       | 3-8       | name, genres     | 1-3      |
| confirm      | 2-3       | name             | 1        |
| give_opinion | 3-5       | name, average rating | 1-3  |
| recommend    | 2-3       | name             | 1-2      |
| request      | 1-2       | specifier        | 1        |
| request attribute | 1    | -                | 1        |
| request explanation | 2-3 | genres, average rating | 1-2 |
| suggest      | 2-3       | name             | 1-2      |
| verify attribute | 3-4  | name, average rating | 1-2  |


#### Animals

| DA           |           | Cats            |           |           | Dogs            |           |           | Wild Animals     |           |
|--------------|-----------|-----------------|-----------|-----------|-----------------|-----------|-----------|------------------|-----------|
|              | Slots     | Mandatory Slots | Hops     | Slots     | Mandatory Slots | Hops     | Slots      | Mandatory Slots | Hops     |
| inform       | 3-8       | name             | 1        | 3-8       | name             | 1-3      | 3-8        | name             | 1-3      |
| confirm      | 2-3       | name             | 1        | 2-3       | name             | 1        | 2-3        | name             | 1        |
| give_opinion | 3-5       | name, rating     | 1        | 3-5       | name, rating     | 1-3      | 3-5        | name, popularity | 1-3      |
| recommend    | 2-3       | name             | 1        | 2-3       | name, rating     | 1-2      | 2-3        | name, popularity | 1-2      |
| request      | 1-2       | specifier        | 1        | 1-2       | specifier        | 1        | 1-2        | specifier        | 1        |
| request attribute | 1    | -                | 1        | 1         | -                | 1        | 1          | -                | 1        |
| request explanation | 2-3 | rating          | 1        | 2-3       | rating           | 1        | 2-3        | popularity        | 1        |
| suggest      | 2-3       | name             | 1        | 2-3       | name             | 1        | 2-3        | name             | 1        |
| verify attribute | 3-4  | name, rating     | 1        | 3-4       | name, rating     | 1        | 3-4        | name, popularity | 1        |


#### Art

| DA           |           | Paintings       |           |           | Painters        |           |
|--------------|-----------|-----------------|-----------|-----------|-----------------|-----------|
|              | Slots     | Mandatory Slots | Hops     | Slots     | Mandatory Slots | Hops     |
| inform       | 3-7       | name, creator    | 1        | 3-7       | name, notable works | 1     |
| confirm      | 3-4       | name, creator    | 1        | 2-3       | name               | 1     |
| give_opinion | 3-4       | name, rating     | 1        | 3-4       | name, rating        | 1     |
| recommend    | 3-4       | name, creator    | 1        | 2-3       | name               | 1     |
| request      | 1-2       | specifier        | 1        | 1-2       | specifier          | 1     |
| request attribute | 1    | -                | 1        | 1         | -                  | 1     |
| request explanation | 2-3 | rating          | 1        | 2-3       | rating             | 1     |
| suggest      | 2-3       | name             | 1        | 2-3       | name               | 1     |
| verify attribute | 3-4  | name, rating     | 1        | 3-4       | name, rating       | 1     |

