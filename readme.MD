### Chinese word vectors

This project uses Word2vec and GloVe tools to train word vectors for Chinese using data from wikipedia dump.

### Steps

1. Download wikipedia dump from: https://dumps.wikimedia.org/zhwiki/latest/zhwiki-latest-pages-articles.xml.bz2

2. Extract Chinese words from the downloaded xml files, using process_wiki.py. This step would take about 11 minutes(from 14:54:17 to 15:05:53) in my computer to finish iterating over Wikipedia corpus of 253646 documents (articles) with 56758668 positions (total 2724783 articles, 68096009 positions before pruning articles shorter than 50 words).

3. We want to get both Traditional version and Simplified version texts. Firstly, Traditional Chinese should be translated to Simplified Chinese, we use [opencc](https://github.com/BYVoid/OpenCC) package.

    ```
    opencc -i wiki.zh.text -o wiki.zh.text.simplified -c zht2zhs.ini
    ```
    Then, simplified Chinese should be translated to traditional Chinese:
    ```
    opencc -i wiki.zh.text -o wiki.zh.text.traditional -c zhs2zht.ini
    ```
    
4. Tokenization, split the sentence into words. Two tokennization mechanism are used: 

    * one character as a words all the time, 因为汉语中单个字往往也能表示许多信息
    
    * using Jieba packages to separate sentence，考虑到常用分词工具来分词，使用词汇可提供更多信息
    
5. 



### Contact

* [Yunchao He] (https://plus.google.com/+YunchaoHe)
* yunchaohe@gmail.com
* [YZU](http://www.yzu.edu.tw/) at Taiwan
* [Weibo](http://weibo.com/heyunchao)
* [Facebook](https://www.facebook.com/yunchao.h)
* [Twitter](https://twitter.com/candlewill)