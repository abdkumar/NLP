# Abstractive Text Summarization

Abstractive summarizers are so-called because they do not select sentences from the originally given text passage to create the summary. Instead, they produce a paraphrasing of the main contents of the given text, using a vocabulary set different from the original document. This is very similar to what we as humans do, to summarize. We create a semantic representation of the document in our brains. We then pick words from our general vocabulary (the words we commonly use) that fit in the semantics, to create a short summary that represents all the points of the actual document. As you may notice, developing this kind of summarizer may be difficult as they would need the Natural Language Generation. Let’s look at the most used approach to the problem.

![image](https://user-images.githubusercontent.com/29776259/171652750-dbab8315-ad5a-488d-ae3f-484cc6bceef5.png)
<br> Reference: https://huggingface.co/

## Dataset
The dataset consists of 4515 examples and contains Author_name, Headlines, Url of Article, Short text, Complete Article. I gathered the summarized news from Inshorts and only scraped the news articles from Hindu, Indian times and Guardian. Time period ranges from febrauary to august 2017.

Kaggle link: https://www.kaggle.com/datasets/sunnysai12345/news-summary

## Packages
- transformers
```pip install transformers```
- [torch](https://pytorch.org/)
- pytorch-lightning
```pip install pytorch-lightning```

## Modelling
- [Hugging Face](https://huggingface.co/), a company that first built a chat app for bored teens provides open-source NLP technologies, and last year, it raised $15 million to build a definitive NLP library. From its chat app to this day, Hugging Face has been able to swiftly develop language processing expertise. The company’s aim is to advance NLP and democratize it for use by everyone.
- Transfer learning, where a model is first pre-trained on a data-rich task before being fine-tuned on a downstream task, has emerged as a powerful technique in natural language processing (NLP). The effectiveness of transfer learning has given rise to a diversity of approaches, methodology, and practice.
- Finetuned the [Google's T5](https://huggingface.co/t5-base) model (transformer architecture) for news summarization task.
- [PyTorch Lighting](https://www.pytorchlightning.ai/) is a lightweight PyTorch wrapper for high-performance AI research that aims to abstract Deep Learning boilerplate while providing you full control and flexibility over your code. With Lightning, you scale your models not the boilerplate.
- Prepared train and test datasets using pytorch-lightning functionalities
- ROUGE, or Recall-Oriented Understudy for Gisting Evaluation, is a set of metrics and a software package used for evaluating automatic summarization and machine translation software in natural language processing. The metrics compare an automatically produced summary or translation against a reference or a set of references (human-produced) summary or translation.
- Check sample predictions ```sample_100_predictions.csv```

## Results
- Text -
```Two years is a long hiatus from limited overs cricket and a fit-again Mohammed Shami is ready to come out all guns blazing in the upcoming Champions Trophy in England from June 1.Shami last played for India in an ODI, back in 2015 World Cup and it will be a fresh start in the 50-over cricket."Two years is a long time to be out of ODI squad. In these two years, I have focussed on my strength and fitness. I have also worked on my weaknesses. I have got leaner. I am hopeful that I can perform well in the upcoming Champions Trophy. I want to give my best shot," Shami said after being named in the Champions Trophy squad.Shami who plays for Delhi Daredevils in the Indian Premier League, feels that IPL games will be great match practice in the tune up to the marquee event."IPL is a good platform for me wherein I will be getting 8-10 matches before going to the international tournament."Delhi Daredevils captain Zaheer Khan's presence has been of great help as his insights has helped Shami become a better bowler.```<br><br>
- Original Summary - 
```Pacer Mohammed Shami, who has returned to the Indian team after being included in the 15-member squad for the Champions Trophy, has said that the Indian bowling attack is one of the best in the world. Speaking about his two-year absence from the Indian team, Shami said, "In these two years, I have focussed on my strength and fitness."``` <br><br>
- Model Predicted Summary - 
```A fit-again Mohammed Shami has said that two years is a long hiatus from limited overs cricket. Shami last played for India in an ODI, back in 2015 World Cup and it will be a fresh start in the 50-over cricket. "I am hopeful that I can perform well in the upcoming Champions Trophy. I want to give my best shot," he added.```


