# awesome-bert-japanese

日本語の学習済み BERT は文から単語への分かち書き，単語からサブワードへの分割の処理にいくつかの選択肢が存在します．
また，単語をサブワードに分割する際に利用する語彙についても構築方法に数種類のバリエーションがあります．

本リポジトリでは，公開されている学習済み BERT モデルについて，
分かち書き・サブワード分割・語彙構築アルゴリズムそれぞれどのアルゴリズムが採用されているかを表にまとめています．

A list of pre-trained BERT models for Japanese.
Japanese is a complicated language; which doesn't have any word boundaries and has many kind of characters.
Therefore, it requires word segmentation before tokenizing word into subwords.
I summarize pretrained BERT models for Japanese by `word segmentation algorithm`, `subword tokenization algorithm`, and `algorithm for constructing vocabulary used in subword tokenization`.


## Model


| Model                      | Sentence -> Words                                | Word -> Subword                           | Algorithm for constructing vocabulary used in subword tokenization     |
| :------------------------- | :----------------                                | :---------------------------------------- | :--------------------------------------------------------------------- |
| Google (Multilingual BERT) | Whitespace                                       | WordPiece                                 | BPE?                                                                   |
| Kikuta                     | --                                               | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Hotto Link Inc.            | --                                               | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Kyoto University           | Juman++                                          | WordPiece                                 | subword-nmt (BPE)                                                      |
| Stockmark Inc.             | MeCab (mecab-ipadic-neologd)                     | --                                        | --                                                                     |
| Tohoku University (a)      | MeCab (mecab-ipadic)                             | WordPiece                                 | Sentencepiece (model_type=bpe)                                         |
| Tohoku University (b)      | MeCab (mecab-ipadic)                             | Character                                 | Sentencepiece (model_type=character)                                   |
| NICT (a)                   | MeCab (mecab-jumandic)                           | WordPiece                                 | subword-nmt (BPE)                                                      |
| NICT (b)                   | MeCab (mecab-jumandic)                           | ---                                       | ---                                                                    |
| akirakubo (a)              | MeCab (unidic-cwj) for Wikipedia and Aozora bunko written in `新仮名` + MeCab (unidic_qkana) for Aozora bunko written in `旧仮名`               | WordPiece                                 | subword-nmt (BPE)                                                      |
| akirakubo (b)              | SudachiPy + MeCab (unidic\_qkana)                | WordPiece                                 | subword-nmt (BPE)                                                      |
| The University of Tokyo    | MeCab (mecab-ipadic-neologd + user dic (J-MeDic) | WordPiece                                 | ? (BPE)                                                                |
| Laboro.AI Inc.             | --                                               | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |



* NICT: National Institute of Information and Communications Technology
* without word segmentation: 文を単語に分割せず直接サブワードへ分割する
* for models by Tohoku University, MeCab+mecab-ipadic-neologd is used for sentence segmentation (thanks @ikuyamada san!)


## Reference

- Google (Multilingual BERT) (2018/11): https://github.com/google-research/bert/blob/master/multilingual.md
- Kikuta (2019/01): https://yoheikikuta.github.io/bert-japanese/
- Hotto Link Inc. (2019/03): https://www.hottolink.co.jp/blog/20190311_101674/
- Kyoto University (2019/03): [http://nlp.ist.i.kyoto-u.ac.jp/bert](http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT%E6%97%A5%E6%9C%AC%E8%AA%9EPretrained%E3%83%A2%E3%83%87%E3%83%AB)
- Stockmark Inc. (2019/04): https://qiita.com/mkt3/items/3c1278339ff1bcc0187f
- Tohoku University (2019/12): https://github.com/cl-tohoku/bert-japanese
- NICT (2020/03): https://alaginrc.nict.go.jp/nict-bert/index.html
- akirakubo (2020/03): https://github.com/akirakubo/bert-japanese-aozora
- The University of Tokyo (2020/03): https://ai-health.m.u-tokyo.ac.jp/uth-ber
- Laboro.AI Inc. (2020/04): https://laboro.ai/column/laboro-bert/
