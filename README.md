# WikiBERT models

BERT models for many languages created from Wikipedia texts.

## Download

http://dl.turkunlp.org/wikibert/

## Pipeline

https://github.com/spyysalo/wiki-bert-pipeline

## Usage with Huggingface's transformers library

The models have been uploaded to huggingface's servers and can be used by specifying `TurkuNLP/wikibert-base-$lang-cased`. See the whole list of models [here](https://huggingface.co/TurkuNLP).

Short example for loading a BERT model without any heads and getting logits out of it:

```
import transformers

# Using Estonian for this example.
# Load tokenizer and model
tokenizer = transformers.BertTokenizer.from_pretrained("TurkuNLP/wikibert-base-et-cased")
model = transformers.BertModel.from_pretrained("TurkuNLP/wikibert-base-et-cased")

# Tokenize, ask for pytorch tensors.
tokens = tokenizer.encode_plus("Kuidas läheb?", return_tensors="pt") # "How are you?"

# Get logits.
logits = model(**tokens)[0]

# Do whatever you want with said logits...

```

For more info on how to use Bert with `transformers`, see [Usage](https://huggingface.co/transformers/usage.html), [Bert model](https://huggingface.co/transformers/model_doc/bert.html#bertmodel) and [BertTokenizer](https://huggingface.co/transformers/model_doc/bert.html#berttokenizer) in the [Huggingface docs](https://huggingface.co/transformers/index.html).
