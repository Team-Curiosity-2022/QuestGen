This repo is a clone of https://github.com/ramsrigouthamg/Questgen.ai

# Questgen AI   <br>

## Try advanced question generation models for free:  https://questgen.ai/  


Questgen AI is an opensource NLP library focused on developing easy to use Question generation algorithms.<br>
It is on a quest build the world's most advanced question generation AI leveraging on state-of-the-art transformer models like T5, BERT and OpenAI GPT-2 etc.

## Google Colab Demo
Demo using T5 Transformer --> [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1XxycxY4exkwr8LL6SaUxwtA-osD0JFfc?usp=sharing)

Demo using GPT-2 --> [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1XxycxY4exkwr8LL6SaUxwtA-osD0JFfc?usp=sharing)

## 1. Installation

### 1.1 Libraries
```
pip install git+https://github.com/ramsrigouthamg/Questgen.ai
pip install git+https://github.com/boudinfl/pke.git@69337af9f9e72a25af6d7991eaa9869f1322dd72

python -m nltk.downloader universal_tagset
python -m spacy download en 
```
### 1.2 Download and extract zip of Sense2vec wordvectors that are used for generation of multiple choices.
```
wget https://github.com/explosion/sense2vec/releases/download/v1.0.0/s2v_reddit_2015_md.tar.gz
tar -xvf  s2v_reddit_2015_md.tar.gz
```

## 2. Running the code

### 2.1 Generate Simple Questions

```
qg = main.QGen()
payload = {
            "input_text": "Recently I went on a walk around campus that I really enjoyed. It was exciting because I had never been on this part of campus and I got to see lots of new places. It was fun to see a new side of campus!"
        }
output = qg.predict_shortq(payload)
pprint (output)
```


<details>
<summary>Show Output</summary>

 ```
 {'questions': [{'Answer': 'cricketer',
                'Question': "What is Sachin Ramesh Tendulkar's career?",
                'context': 'Sachin Ramesh Tendulkar is a former international '
                           'cricketer from India and a former captain of the '
                           'Indian national team.',
                'id': 1},
               {'Answer': 'india',
                'Question': 'Where is Sachin Ramesh Tendulkar from?',
                'context': 'Sachin Ramesh Tendulkar is a former international '
                           'cricketer from India and a former captain of the '
                           'Indian national team.',
                'id': 2},
               {'Answer': 'batsmen',
                'Question': 'What is the best cricketer?',
                'context': 'He is widely regarded as one of the greatest '
                           'batsmen in the history of cricket.',
                'id': 3}]
 }
 ```
</details>



### NLP models used

For maintaining meaningfulness in Questions, Questgen uses Three T5 models. One for Boolean Question generation, one for MCQs, FAQs, Paraphrasing and one for answer generation.

### Online Demo website.
https://questgen.ai/
