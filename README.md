# Poe-RNN

In Andrej Karpathy's excellent blog post [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) he describes training an LSTM model on the collected works of Edgar Allen Poe to see what it produces. That sounded like fun so I thought I'd give it a try.

This is a character-level recurrent network, so it has no pre-conceived knowledge of English words and can only output one character at a time. At the beginning of training, all that comes out of the net is random gibberish, but as training progesses, language constructs begin to emerge -- though far from comprehensible. Here is a sample of its output:

> A getting the ebony human archurness of the middle was,jutted a hope, yet I am not only residetion of them, was somewhat jeferous Vane where the undary like the blood-Vilips. On the enormous, M. X. Masonvour in the liviary at all, I could not no building had been great, in a view of rich to which it had scrutinuted on several artisopens, than it may glad at so how-dolitianie its stationed him in the way of yer, and more than all the main delight having giver, instant he suddenly called to find a small wassage and October! I now dissenteed, from his thing, partly, to utter completely corpor, yet fancies are skeppinating in the person that the bland threw the animal other attractions.


### LSTM Model

For this learning task, I used a 3-layer Long Short Term Memory (LSTM) model with a hidden size of 512 nodes at each layer. Since the test dataset is relatively small, overfitting can be an issue, but my main consideration for the model size was keeping the training time reasonable. Larger models would most likely perform better, albeit with diminishing returns. I trained with the Adam optimizer with a learning rate of 5e-3. I used 300-dimensional character embeddings from [this repo](https://github.com/minimaxir/char-embeddings). 

### Running the code

To run the code, clone the repo and type `python LSTM.py` into the command prompt (after installing the necessary packages). Hyperparameters can be found as constants at the top of LSTM.py, and this model can be made to train on any text corpus by specifying it in the `FILENAME` constant. 


