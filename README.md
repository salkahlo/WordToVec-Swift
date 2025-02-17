Word Embeddings
============

Distributed representations (DR) of words (i.e., word embeddings) are used to capture semantic and syntactic regularities of the language by analyzing distributions of word relations within the textual data. Modeling methods generating DRs rely on the assumption that 'words that occur in similar contexts tend to have similar meanings' (distributional hypothesis) which stems from the nature of language itself. Due to their unsupervised nature, these modeling methods do not require any human judgement input to train, which allows researchers to train very large datasets in relatively low costs.

Traditional representations of words (i.e., one-hot vectors) are based on word-word (W x W) co-occurrence sparse matrices where W is the number of distinct words in the corpus. On the other hand, distributed word representations (DRs) (i.e., word embeddings) are word-context (W x C) dense matrices where C < W and C is the number of context dimensions which are determined by underlying model assumptions. Dense representations are arguably better at capturing generalized information and more resistant to overfitting due to context vectors representing shared properties of words. DRs are real valued vectors where each context can be considered as a continuous feature of a word. Due to their ability to represent abstract features of a word, DRs are considered as reusable across higher level tasks in ease, even if they are trained with totally different datasets.

Prediction based DR models gained much attention after Mikolov et al.’s neural network based SkipGram model in 2013. The secret behind the prediction based models is simple: never build a sparse matrix at all. Prediction based models construct dense matrix representations directly instead of reducing sparse ones to dense ones. These models are trained like any other supervised learning task by giving lots of positive and negative samples without adding any human supervision costs. Aim of these models is to maximize the probability of each context c with the same distributional assumptions on word-context co-occurrences, similar to count based models.

SkipGram is a prediction based distributional semantic model (DSM) consisting of a shallow neural network architecture inspired from neural language modeling (LM) intuitions. It is commonly known for its open-source implementation library word2vec. SkipGram acts like a log-linear classifier maximizing the prediction of the surrounding words of a word within a context (center window). Probabilistic word and sentence prediction by local neighbors of a word has been successfully applied on LM tasks under Markov assumption. SkipGram leverages the same idea by considering the words within the window as positive and negative instances and learning weights (for k contexts) which maximizes word predictions. In the training process, each word vector starts as a random vector, and then iteratively shifts to the neighboring vector.

Video Lectures
============

[<img src=https://github.com/StarlangSoftware/WordToVec/blob/master/video1.jpg width="50%">](https://youtu.be/7zaTW8dH_QMc)[<img src=https://github.com/StarlangSoftware/WordToVec/blob/master/video2.jpg width="50%">](https://youtu.be/4YvBJ_p8HRc)[<img src=https://github.com/StarlangSoftware/WordToVec/blob/master/video3.jpg width="50%">](https://youtu.be/Hh-MM_rSWeo)

For Developers
============
You can also see [Java](https://github.com/olcaytaner/WordToVec), [Python](https://github.com/olcaytaner/WordToVec-Py), [Cython](https://github.com/olcaytaner/WordToVec-Cy), [C#](https://github.com/starlangsoftware/WordToVec-CS), [Js](https://github.com/starlangsoftware/WordToVec-Js), or [C++](https://github.com/olcaytaner/WordToVec-CPP) repository.

## Requirements

* Xcode Editor
* [Git](#git)

### Git

Install the [latest version of Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Download Code

In order to work on code, create a fork from GitHub page. 
Use Git for cloning the code to your local or below line for Ubuntu:

	git clone <your-fork-git-link>

A directory called WordToVec-Swift will be created. Or you can use below link for exploring the code:

	git clone https://github.com/starlangsoftware/WordToVec-Swift.git

## Open project with XCode

To import projects from Git with version control:

* XCode IDE, select Clone an Existing Project.

* In the Import window, paste github URL.

* Click Clone.

Result: The imported project is listed in the Project Explorer view and files are loaded.


## Compile

**From IDE**

After being done with the downloading and opening project, select **Build** option from **Product** menu. After compilation process, user can run WordToVec-Swift.

Detailed Description
============

To initialize artificial neural network:

	init(corpus: Corpus, parameter: WordToVecParameter)

To train neural network:

	func train() -> VectorizedDictionary

# Cite

	@inproceedings{ercan-yildiz-2018-anlamver,
    	title = "{A}nlam{V}er: Semantic Model Evaluation Dataset for {T}urkish - Word Similarity and Relatedness",
    	author = {Ercan, G{\"o}khan  and
      	Y{\i}ld{\i}z, Olcay Taner},
    	booktitle = "Proceedings of the 27th International Conference on Computational Linguistics",
    	month = aug,
    	year = "2018",
    	address = "Santa Fe, New Mexico, USA",
    	publisher = "Association for Computational Linguistics",
    	url = "https://www.aclweb.org/anthology/C18-1323",
    	pages = "3819--3836",
	}
