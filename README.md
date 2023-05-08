# ner-evaluation

This is my new repo for NER evaluation. The old and now-unused repo is [here](https://github.com/JinnyViboonlarp/annotation-evaluation).

## Using this service

```bash
$ python evaluate.py [path-to-gold-file] [path-to-model-prediction-file] ([optional-path-for-output-file])
```
for example,
```bash
$ python evaluate.py gold-file-examples/gold-ann-example.ann test-file-examples/test-mmif-example.mmif result-examples/result-example.txt
```
