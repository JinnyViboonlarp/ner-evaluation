# ner-evaluation

This is my new repo for NER evaluation. The old and now-unused repo is [here](https://github.com/JinnyViboonlarp/annotation-evaluation).

## evaluating a pair of gold-standard file and model prediction file

```bash
$ python evaluate.py [path-to-gold-file] [path-to-model-prediction-file] ([optional-path-for-output-file])
```
for example,
```bash
$ python evaluate.py goldfiles-example/cpb-this-is-example1-transcript.ann testfiles-example/cpb-this-is-example1.json result-example-one-pair.txt
```
the files to be evaluated can be in either mmif format (which means it ends with .mmif or .json) or in .ann format.

## evaluating a folder of gold-standard files and another folder of model prediction files

```bash
$ python evaluate.py [path-to-gold-folder] [path-to-model-prediction-folder] ([optional-path-for-output-file])
```
for example,
```bash
$ python evaluate.py goldfiles-example/ testfiles-example/ result-example.txt
```
Regarding how a file in one folder is paired with a file in another folder: It is assumed that the substring "cpb-substring1-substring2-substring3" (for example, "cpb-aacip-507-1v5bc3tf81") refers to the video that the NER annotation is based on. If a file in a model prediction folder has this kind of substring in its name, and this same substring is found in another file's name in a gold-standard folder, the two files will be matched.

### downloading a gold-standard folder and a model prediction folder from github repos and perform evaluation on them

There is a code that can automatically download a gold-standard folder and a model prediction folder from github repos (into a local folders `goldfiles` and `testfiles` respectively), and then perform NER evaluation on them. 
```bash
$ python download_and_evaluate.py
```
In the file `download_and_evaluate.py`, the gold-standard link is set to 'https://github.com/clamsproject/clams-aapb-annotations/tree/main/golds/ner/2022-jun-namedentity' and the model-prediction link is set to 'https://github.com/JinnyViboonlarp/ner-evaluation/tree/main/testfiles', but the links (and the folders to be downloaded into) could be configured as parameters in the file `download_and_evaluate.py`.
