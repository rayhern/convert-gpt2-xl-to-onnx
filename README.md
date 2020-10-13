# Convert GPT2-XL to ONNX
This will help you convert a GPT2-XL model to an optimized onnx model fp 16.

Before I made this there were no inference examples on the internet. This took me more than 2 weeks to write in my spare time. For the beam, top_k, and top_p methods of generation I took the functions from huggingface transformers. I still had to slightly modify some code though to get it working. Let me know if you have any isses with this.

Here is an example on how to use the Gpt2 ONNX model using my inference class included in the notebook:
```
# Instatiate our GPT2 ONNX model for reuse.
onnx_model = GPT2ONNXModel(
  'gpt2-final/gpt2_fp16.onnx', 
  'gpt2-xl', 
  device='cuda', 
  verbose=False,
)

# Generate some text with open ONNX session.
generated = onnx_model.generate(
  'George Washington was', 
  temperature=1.0, 
  top_k=50, 
  top_p=0.92,
  max_length=100,
  min_length=5,
  num_return_sequences=3,
  repetition_penalty=1.0,
  do_sample=True
)
print(generated)```
