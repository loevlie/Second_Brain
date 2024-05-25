
# Converting Grounding DINO


Netron output from the onnx file:

![[Pasted image 20240121174621.png]]

## TensorRT Conversion Attempt 1:



trtexec --onnx=grounded.onnx \
        --saveEngine=grounded.trt \
        --explicitBatch \
        --optShapes=img:1x3x800x1200,input_ids:1x10,attention_mask:1x10,position_ids:1x10,token_type_ids:1x10,text_token_mask:1x10x10 \
        --maxShapes=img:1x3x1224x1224,input_ids:1x256,attention_mask:1x256,position_ids:1x256,token_type_ids:1x256,text_token_mask:1x256x256 \
        --minShapes=img:1x3x512x512,input_ids:1x1,attention_mask:1x1,position_ids:1x1,token_type_ids:1x1,text_token_mask:1x1x1 \
        --workspace=1024 \
        --fp16  # Include this flag if your GPU supports FP16


# Links

- https://stackoverflow.com/questions/59280745/inference-with-tensorrt-engine-file-on-python
- https://medium.com/@zergtant/accelerating-model-inference-with-tensorrt-tips-and-best-practices-for-pytorch-users-7cd4c30c97bc
- 