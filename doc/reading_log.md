# 2016-01-29 Bengio et al., 2003.
*A Neural Probabilistic Language Model* by Yoshua Bengio, Réjean Ducharme, Pascal Vincent, and Christian Jauvin. All from Université de Montréal.
http://www.jmlr.org/papers/volume3/bengio03a/bengio03a.pdf

## My summary of the abstract before reading the paper
It is difficult to know how likely a sentence is because of the curse of dimensionality: it might be very unlikely that a sentence will repeat in a corpus of text, and a test sentence might not be in the training data. N-gram models, a previous approach, makes a Markov assumption in order to overcome the curse of dimensionality. This paper, on the other hand, **learns a distributed representation for words** [I'm not sure yet what they mean by a *distributed representation*, but I will find out soon enough]. At the same time, it learns the probability distribution (i.e. a statistical language model) of sequences of words as a function of the distributed representations for words. It uses a neural network to represent this probability distribution (hence the title of the paper).

The advantages of the proposed approach are that it:

* Generalizes well because even if a sentence hasn't been seen before, it will be given a high probability score if the words it contains have a "nearby representation" to words in a training sentence.
* Significantly improves on state-of-the-art n-gram models of 2003 [I think that the current state of the art uses Recursive or Recurrent Neural Networks?]
* Allows to take advantage of longer contexts, in contrast with n-grams, which only look at n words behind the current one.

The *disadvantage* of the proposed approach is that:

* It is challenging to train the model within a reasonable time [I interpret this to mean it takes weeks or even months to train the model] because the model is large, containing *millions* of parameters.

[Based on reading this abstract, it seems like they will consider sentences as bags of words and learn some form of word vectors that will help them learn the probability distributions. If this is the case, wouldn't there be a problem distinguishing a grammatically correct sentence from one that isn't? Given that they mention that the model beats n-gram, they can't be doing bag of words. But in that case are they using a recurrent net? or how do they make their input the same size every time to fit it in the neural net? Additionally, what do they mean by a *distributed representation*?]

## Distributed Representation
Definition from the U Alberta dictionary of cognitive science (http://www.bcp.psych.ualberta.ca/~mike/Pearl_Street/Dictionary/contents/D/distributed.html):

> A distributed representation is a concept that is central to connectionism. In a connectionist network, a distributed representation occurs when some concept or meaning is represented by the network, but that meaning is represented by a pattern of activity across a number of processing units (Hinton et al, 1986). In other words, the meaning is not locally represented by a single unit that is analogous to a "grandmother cell".

> One advantage of distributed representations is that they provide damage resistance and graceful degradation (Medler et al., 2005). A disadvantage of such representations is that they make the internal structure of a trained network very difficult to interpret (Dawson, 2004).

Basically when this paper says Distributed Representation it just means a word vector that has been learned as part of a neural network.

## Reading Response
The paper uses something that looks like like an n-gram model in the sense that it assumes that the choice of each word in a text is only dependent on the choice of the previous n-1 previous words.

However, instead of just using n-gram counts to calculate the probabilities (these counts get *very* sparse as n increases, even n=4 is too sparse, due to the curse of dimensionality, a curse imposed by a high-dimensionality sorceror in antiquity, in the dark ages of AI), it uses a learned, low-dimensional feature space on the words. By using a low-dimensional word embedding, the authors try to capture semantic meaning so that words that tend to be used in a similar fashion in sentences are treated similarly, even if they aren't *exactly* the same word (the n-gram count technique would be mercyless here).

The authors end up using an n value of up to 5, which is the "longer context" they mentioned in the abstract. Additionally, the authors discover that combining this neural technique with vanilla discrete n-gram probabilities via a weighted average of the language model probabilities, they get better results than using either one independently.

The paper also talks about concerns of speed. Due to the large amount of parameters in the network, the authors mention that training is computationally intensive. The authors describe a way to make the computation in parallel. I believe that nowadays, the computation would be much faster using GPU computing.
