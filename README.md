# nncase
Build of open deep learning compiler stack for Kendryte K210 AI accelerator

## Usage

```sh
ncc [-v|--version] { compile { -i|--input-format -t|--target <input file> [--input-prototxt] <output file> [--output-arrays] [--quant-type] [--w-quant-type] [--use-mse-quant-w] [--split-w-to-act] [--dataset] [--dataset-format] [--dump-range-dataset] [--dump-range-dataset-format] [--calibrate-method] [--preprocess] [--swapRB] [--mean] [--std] [--input-range] [--input-shape] [--letterbox-value] [--input-type] [--output-type] [--input-layout] [--output-layout] [--model-layout] [--is-fpga] [--dump-ir] [--dump-asm] [--dump-quant-error] [--dump-import-op-range] [--dump-dir] [--benchmark-only] } } { infer { <model filename> <output path> --dataset [--dataset-format] [--input-layout] } }

OPTIONS, ARGUMENTS:
  -v, --version           show version
                          
  compile                 
                          
  -i, --input-format <input format>
                          input format, e.g. tflite|onnx|caffe
  -t, --target <target>   target architecture, e.g. cpu|k210|k510
  <input file>            input file
  --input-prototxt <input prototxt>
                          input prototxt
  <output file>           output file
  --output-arrays <output arrays>
                          output arrays
  --quant-type <quant type>
                          post trainning quantize type, e.g uint8|int8|int16, default is uint8
  --w-quant-type <w quant type>
                          post trainning weights quantize type, e.g uint8|int8|int16, default is uint8
  --use-mse-quant-w       use min mse algorithm to refine weights quantilization or not, default is 0
  --split-w-to-act        split weights to act or not, default is 0
  --dataset <dataset path>
                          calibration dataset, used in post quantization
  --dataset-format <dataset format>
                          datset format: e.g. image|raw, default is image
  --dump-range-dataset <dataset path>
                          dump import op range dataset
  --dump-range-dataset-format <dataset format>
                          datset format: e.g. image|raw, default is image
  --calibrate-method <calibrate method>
                          calibrate method: e.g. no_clip|l2|kld_m0|kld_m1|kld_m2|cdf, default is no_clip
  --preprocess            enable preprocess, default is 0
  --swapRB                swap red and blue channel, default is 0
  --mean <normalize mean> normalize mean, default is 0. 0. 0.
  --std <normalize std>   normalize std, default is 1. 1. 1.
  --input-range <input range>
                          float range after preprocess
  --input-shape <input shape>
                          shape for input data
  --letterbox-value <letter box value>
                          letter box pad value, default is 0.000000
  --input-type <input type>
                          input type, e.g float32|uint8|default, default is default
  --output-type <output type>
                          output type, e.g float32|uint8, default is float32
  --input-layout <input layout>
                          input layout, e.g NCHW|NHWC, default is NCHW
  --output-layout <output layout>
                          output layout, e.g NCHW|NHWC, default is NCHW
  --model-layout <model layout>
                          model layout, e.g NCHW|NHWC, default is empty
  --is-fpga               use fpga parameters, default is 0
  --dump-ir               dump ir to .dot, default is 0
  --dump-asm              dump assembly, default is 0
  --dump-quant-error      dump quant error, default is 0
  --dump-import-op-range  dump import op range, default is 0
  --dump-dir <dump directory>
                          dump to directory
  --benchmark-only        compile kmodel only for benchmark use, default is 0
                          
  infer                   
                          
  <model filename>        kmodel filename
  <output path>           output path
  --dataset <dataset path>
                          dataset path
  --dataset-format <dataset format>
                          dataset format, e.g. image|raw, default is image
  --input-layout <input layout>
                          input layout, e.g NCHW|NHWC, default is NCHW
```
