# blindvisaidgpt
An interactive aid for blind people using microsoft/visual-chatgpt
#### (Originally motivated as a potential [Deep Hack](https://hasgeek.com/generativeAI/deep-hackathon/?utm_campaign=webshare) submission)

```
The ultimate aim is to have a WiFi enabled camera mounted on a glass for visually impaired people, to give them 
an idea what they could possibly see in their visual-field, and to provide an interactive interface on top 
of it so that they could ask questions about what they’re being told lies in front of them.
```


### Demo


https://user-images.githubusercontent.com/31207633/227807355-202886ab-3b41-41c3-be99-8be486ae9489.mp4



<br>

## Quick Start
### (akin to setting up microsoft/visual-chatgpt)

```
# clone the repo
git clone git@github.com:justanotherlad/blindvisaidgpt.git

# Go to directory
cd blindvisaidgpt

# create a new environment
conda create -n visgpt python=3.8

# activate the new environment
conda activate visgpt

#  prepare the basic environments
pip install -r requirements.txt

# prepare your private OpenAI key (for Linux)
export OPENAI_API_KEY={Your_Private_Openai_Key}

# prepare your private OpenAI key (for Windows)
set OPENAI_API_KEY={Your_Private_Openai_Key}

# Start blindvisaidgpt !
# You can specify the GPU/CPU assignment by "--load", the parameter indicates which 
# Visual Foundation Model to use and where it will be loaded to
# The model and device are separated by underline '_', the different models are separated by comma ','
# The available Visual Foundation Models can be found in the following table
# For example, if you want to load ImageCaptioning to cpu and VisualQuestionAnswering to cuda:0
# You can use: "ImageCaptioning_cpu,VisualQuestionAnswering_cuda:0"

# Advice for CPU Users (current default)
python visual_chatgpt.py --load ImageCaptioning_cpu,VisualQuestionAnswering_cpu

# Advice for 1 Tesla T4 15GB  (Google Colab)  --(feature yet to be tried)                       
python visual_chatgpt.py --load "ImageCaptioning_cuda:0,VisualQuestionAnswering_cuda:0"
                                
# Advice for 4 Tesla V100 32GB  --(feature yet to be tried)                        
python visual_chatgpt.py --load "ImageCaptioning_cuda:0,ImageEditing_cuda:0,
    Text2Image_cuda:1,Image2Canny_cpu,CannyText2Image_cuda:1,
    Image2Depth_cpu,DepthText2Image_cuda:1,VisualQuestionAnswering_cuda:2,
    InstructPix2Pix_cuda:2,Image2Scribble_cpu,ScribbleText2Image_cuda:2,
    Image2Seg_cpu,SegText2Image_cuda:2,Image2Pose_cpu,PoseText2Image_cuda:2,
    Image2Hed_cpu,HedText2Image_cuda:3,Image2Normal_cpu,
    NormalText2Image_cuda:3,Image2Line_cpu,LineText2Image_cuda:3"
                             
```
