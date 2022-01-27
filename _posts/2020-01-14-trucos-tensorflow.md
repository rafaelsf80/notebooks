---
toc: true
layout: post
title: Trucos de TensorFlow
description: Una lista de trucos y trozos de código sobre TensorFlow
categories: [quickrecipes]
image: images/tensorflow.png
---

## Capa `TextVectorization` 

`TextVectorization` es una capa de preprocesamiento que convierte texto (cadenas de caracteres) en una codificación numérica, que es lo que puede leer una red neuronal. Esta capa realiza varias funciones a la vez: estandarización (eliminar pej espacios), tokenization (dividir el texto en una lista limitada de palabras), y vectorización (convertir esos tokens en números, usando una tabla). Esta capa se conecta en el modelo a una capa de Embeddings ó una capa densa.

```python
import tensorflow as tf
from tensorflow.keras.layers.experimental import preprocessing
data = [
    "En un lugar de la Mancha",
    "de cuyo nombre no quiero acordarme."
]
layer = preprocessing.TextVectorization()
layer.adapt(data)
vectorized_text = layer(data)
print(vectorized_text)
```

```python
    tf.Tensor(
    [[10  3  8  2  9  7]
    [ 2 11  5  6  4 12]], shape=(2, 6), dtype=int64)|
```


# Example Markdown Post

## Basic setup

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-filename.md`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `filename` is whatever file name you choose, to remind yourself what this post is about. `.md` is the file extension for markdown files.

The first line of the file should start with a single hash character, then a space, then your title. This is how you create a "*level 1 heading*" in markdown. Then you can create level 2, 3, etc headings as you wish but repeating the hash character, such as you see in the line `## File names` above.

## Basic formatting

You can use *italics*, **bold**, `code font text`, and create [links](https://www.markdownguide.org/cheat-sheet/). Here's a footnote [^1]. Here's a horizontal rule:

---

## Lists

Here's a list:

- item 1
- item 2

And a numbered list:

1. item 1
1. item 2

## Boxes and stuff

> This is a quotation

{% include alert.html text="You can include alert boxes" %}

...and...

{% include info.html text="You can include info boxes" %}

## Images

![]({{ site.baseurl }}/images/logo.png "fast.ai's logo")

## 

You can format text and code per usual 

General preformatted text:

    # Do a thing
    do_thing()

Python code and output:
TensorFlow tricks





# Prints '2'
print(1+1)
```

    2

Formatting text as shell commands:

```shell
echo "hello world"
./some_script.sh --option "value"
wget https://example.com/cat_photo1.png
```

Formatting text as YAML:

```yaml
key: value
- another_key: "another value"
```


## Tables

| Column 1 | Column 2 |
|-|-|
| A thing | Another thing |


## Tweetcards

{% twitter https://twitter.com/jakevdp/status/1204765621767901185?s=20 %}


## Footnotes



[^1]: This is the footnote.

