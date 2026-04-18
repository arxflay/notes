
Transformer model transforms input to output using encoders (processing input) and decoders (sending output)

Encoders are stacked by six with same amount of decoders. Each encoders are identical but each have different weights


Encoding process contains two layers (sequential):
1. Self attention layer - layer that helps understand context based on other words from input. All words from input are processed as whole. Output from this layer is send to feed forward layer
2. Feed forward layer - individual words in this layer are processed in parallel manner 

All input (words) is put in self attention layer at the same time, but individual inputs (individual words) are processed by feed forward layer in parallel manner, they don't depend on each after self attention layer processing.

Output from one encoder is passed to another encoder until last encoder

