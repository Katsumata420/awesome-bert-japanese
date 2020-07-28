# awesome-bert-japanese

日本語の学習済み BERT は文から単語への分かち書き，単語からサブワードへの分割の処理にいくつかの選択肢が存在します．
また，単語をサブワードに分割する際に利用する語彙についても構築方法に数種類のバリエーションがあります．

本リポジトリでは，公開されている学習済み BERT モデルについて，
分かち書き・サブワード分割・語彙構築アルゴリズムそれぞれどのアルゴリズムが採用されているかを表にまとめています．

A list of pre-trained BERT models for Japanese.
Japanese is a complicated language; which doesn't have any word boundaries and has many kind of characters.


## Model


| Model                      | Sentence -> Words | Word -> Subword                           | Algorithm for constructing vocabulary used in subword tokenization     |
| :------------------------- | :---------------- | :---------------------------------------- | :--------------------------------------------------------------------- |
| Google (Multilingual BERT) | Whitespace        | WordPiece                                 | BPE?                                                                   |
| Kikuta                     | --                | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Hotto Link Inc.            | --                | Sentencepiece (without word segmentation) | Sentencepiece (model_type=unigram)                                     |
| Kyoto University           | Juman++           | WordPiece                                 | subword-nmt (BPE)                                                      |
| Stockmark Inc.             | MeCab             | --                                        | --                                                                     |
| Tohoku University (a)      | MeCab             | WordPiece                                 | Sentencepiece (model_type=bpe)                                         |
| Tohoku University (b)      | MeCab             | Character                                 | Sentencepiece (model_type=character)                                   |
| NICT (a)                   | MeCab             | WordPiece                                 | subword-nmt (BPE)                                                      |
| NICT (b)                   | MeCab             | ---                                       | ---                                                                    |
| The University of Tokyo    | MeCab             | WordPiece                                 | ? (BPE)                                                                |

* NICT: National Institute of Information and Communications Technology
* without word segmentation: 文を単語に分割せず直接サブワードへ分割する


## Reference

- Google (Multilingual BERT) (2018/11): https://github.com/google-research/bert/blob/master/multilingual.md
- Kikuta (2019/01): https://yoheikikuta.github.io/bert-japanese/
- Hotto Link Inc. (2019/03): https://www.hottolink.co.jp/blog/20190311_101674/
- Kyoto University (2019/03): [http://nlp.ist.i.kyoto-u.ac.jp/bert](http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT%E6%97%A5%E6%9C%AC%E8%AA%9EPretrained%E3%83%A2%E3%83%87%E3%83%AB)
- Stockmark Inc. (2019/04): https://qiita.com/mkt3/items/3c1278339ff1bcc0187f
- Tohoku University (2019/12): https://github.com/cl-tohoku/bert-japanese
- NICT (2020/03): https://alaginrc.nict.go.jp/nict-bert/index.html
- The University of Tokyo (2020/03): https://ai-health.m.u-tokyo.ac.jp/uth-ber
