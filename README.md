# convert-gpt2-xl-to-onnx
This will help you convert a GPT2-XL model to an optimized onnx model fp 16.

Before I made this there were no inference examples on the internet. This took me more than 2 weeks to write in my spare time. For the beam, top_k, and top_p methods of generation I took the functions from huggingface transformers. I still had to slightly modify some code though to get it working. Let me know if you have any isses with this.

Here is an example on how to use the Gpt2 ONNX model using my inference class included in the notebook:
