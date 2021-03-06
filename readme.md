# Translate API
A simple web API to translate. There is power by Google Translate.

# API

```json
Get Request:

/?w=word[&f=auto&t=zh]

Response:
{
    "word": "word",
    "text": "字",
    "candidate": [
        "字",
        "词",
        "单词",
        "话",
        "言",
        "言辞",
        "笔墨",
        "约言",
        "字",
        "词",
        "单词"
    ]
}
```

## Parameter
|key|description|
|--|--|
|w|The word want to translate|
|f|The source language. Default is recognized automatically. (Optional)|
|t|The target language. Default is Chinese. (Optional)|

> Note: If there is no source language, the language will be recognized automatically. When there is about 50% Chinese, the source language will be changed to Chinese.

## Response
|key|description|
|--|--|
|word|The word want to translate|
|text|The most match result|
|candidate|Other translate result|

## Language Code
You can check it in [here](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) (ISO 639-1).

## Example

```json
GET /?w=word&t=ja

{
    "word": "word",
    "text": "ワード",
    "candidate": [
        "ワード",
        "単語",
        "語",
        "言葉",
        "語句",
        "伝言",
        "一言半句",
        "口舌"
    ]
}

GET /?w=中文&f=zh&t=ko

{
    "word": "中文",
    "text": "중국어",
    "candidate": [
        "중국어"
    ]
}

GET /?w=中文

{
    "word": "中文",
    "text": "Chinese",
    "candidate": [
        "Chinese"
    ]
}
```