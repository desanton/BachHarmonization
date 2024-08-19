## Introduction and How to Run

Inspired by the advice I received after creating my "Harmonizer" research-project, I wanted to use machine learning to generate harmonies.
Bach composed chorales with 4-part harmonies consisting of soprano, alto, tenor, and bass voicings.
This project generates the accompanying alto, tenor, and bass voices given the soprano voice. 

To best run the "Bach.ipynb" file, you should install jupyter notebook and conda. 
Using conda, create an environment where you install the following conda libraries
1. numpy
2. tensorflow
3. pretty_midi

Then, while in this conda environment, you can run the "jupyter notebook" command from your command-line interface, and open the "Bach.ipynb" file.
I acquired the chorales JSON file from the following github repository: https://github.com/czhuang/JSB-Chorales-dataset.

They acquired the dataset from http://www-etud.iro.umontreal.ca/~boulanni/icml2012

This project will write MIDI files. You can play these MIDI files using an application such as Garageband. 

## Reflection

The recurrent neural network seems to work quite well here. The loss of the model fit to both the training and cross-validation data was relatively low, and the loss did not differ much. 
The network predicts the correct note about 30% of the time for the CV data. Considering how complex Bach's harmony is, this is quite good.

However, I recognize many areas of improvement here. The neural network does well in terms of predicting notes, but the musical coherency of the network could be improved. The network inherently recognizes patterns between soprano voicings, and the alto, tenor, bass voicings over time, giving it harmonies that sound alright and don't clash awkwardly. However, there must be a way for the network to understand the more intricate relationships between melody and harmony in these chorales. For example, in Bach's chorales I noticed periods of more movement in the harmony followed by periods of less movement. In my RNN, the amount of movement tends to follow the amount of movement in the soprano. In the neural network, the soprano changing notes tends to be the most reliable sign to change notes in the ATB voicings, but in Bach's actual chorales all the voicings move almost independently yet synergistically.

Qualitatively, when I play a ML sequence followed by the actual sequence, the ML sequence can sound Bach-like at times, but the actual sequence conveys much greater intention and direction. A greater sense of "harmonic direction" would be another area of improvement. 

Ultimately, given how complicated Bach's 4-part harmonies are, I am happy with the result even though there are many areas to improve on.

## References

Boulanger-Lewandowski, N., Vincent, P., & Bengio, Y. (2012). Modeling Temporal Dependencies in High-Dimensional Sequences: Application to Polyphonic Music Generation and Transcription. Proceedings of the 29th International Conference on Machine Learning (ICML-12), 1159–1166.
