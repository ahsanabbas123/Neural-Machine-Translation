# NMT by Jointly Learning to Align and Translate [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1z52fsTHv3VXPXkYKn_efQYX72U1cOs19)
Allievates the information compression problem by allowing the decoder to "look back" at the input sentence by creating context vectors that are weighted sums of the encoder hidden states. The weights for this weighted sum are calculated via an attention mechanism, where the decoder learns to pay attention to the most relevant words in the input sentence.     
Based on the paper [Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)

## Dataset  
The [data](https://download.pytorch.org/tutorial/data.zip) for this project is a set of many thousands of English to French translation pairs.

## Architecture
A Sequence to Sequence network, or seq2seq network, or Encoder Decoder network, is a model consisting of two RNNs called the encoder and decoder. The encoder reads an input sequence and outputs a single vector, and the decoder reads that vector to produce an output sequence. 

<p align="center">
<img src="https://pytorch.org/tutorials/_images/seq2seq.png" width="500">
<img src="https://i.imgur.com/1152PYf.png" width="250">
</p>  

Attention allows the decoder network to “focus” on a different part of the encoder’s outputs for every step of the decoder’s own outputs. First we calculate a set of attention weights. These will be multiplied by the encoder output vectors to create a weighted combination. The result (called attn_applied in the code) should contain information about that specific part of the input sequence, and thus help the decoder choose the right output words.

 

