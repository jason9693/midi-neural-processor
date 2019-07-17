# Midi Neural Processor

* Repository for midi-based machine learning model's {pre/post} processing.
* You can use this processor in any machine learnig library like tensorflow, pytorch, etc...

* This processor's algorithm is based on [PerformanceRNN](https://magenta.tensorflow.org/performance-rnn) & [Music Transformer (Polyphonic Music)](https://arxiv.org/abs/1809.04281) Model's preprocessing algorithm suggested by Google Magenta.



## Simple Useage

### Download

```bash
$ git clone https://github.com/jason9693/midi-processor.git
```

### Encoding & Load midi file

* You can load & encode your midi file just one line
* encode_midi() is a role of pre-processing.

```python
from processor import encode_midi
encoded = encode_midi('bin/ADIG04.mid') ## 'bin/AIDG04.mid' is midi file path.
## output: [int, int, int, int, ... ].
## int range is range(0,388). 388 = NOTE_ON + NOTE_OFF + TIME_SHIFT + VELOCITY 
```

### Decoding

* decode_midi is convert integer array to midi form.
* you can gave method to ***file_path*** as a second args in that if you want to save midi as .mid file. 
* all elements in integer array should be range(0,388). 

```python
from processor import decode_midi
decode_midi(encoded, 'bin/test.mid') ## 'bin/test.mid' is midi file path.
```



## Comming Soon

1. Pedal Control
2. Midi Converter to .tfrecords



## License

Project is published under the MIT licence. Feel free to clone and modify repo as you want, but don't forget to add reference to authors :)

 