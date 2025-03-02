# gpt-2-from-scratch-tf
coded gpt-2-small model from scratch using tensorflow

changes from original model architecture : 
- used flash attention 2 mechanism instead of scaled dot product attention which resulted in faster training and inference
- orignal gpt-2 decode block, the layers are stacked in the following manner : attention layer, layer normalization, skip connection, feed forward network, layer normalization, skip connection then final output. but i have stacked the layers in the following manner : layer normalization, attention layer, skip connection, layer normalization, feed forward network, skip connection and then final output. that latter layer stacking format has become the industry standard and has proved to increase performance
- custom training and inference loop  using tensorflow
- the whole model was train in using 'mini-shakesphere dataset' in Tesla T4 GPU in google colab environment
- different & modern finetuning methods are also discussed
