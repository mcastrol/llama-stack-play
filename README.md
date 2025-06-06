# llama-stack-play


## Setup
1) create virtual environment 

```
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Using conda


```
conda create --name llama-stack-play python=3.11.8
conda activate llama-stack-play
pip install -r requirements.txt
```

conda create --name llama-stack-play-3127 python=3.12.7



2) Build ollama template

```
INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack build --template ollama --image-type venv
```

Using conda
```
INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack build --template ollama --image-type conda
```

## Startup client/server local mode


1) Open a terminal an start ollama model 

``` 
ollama run llama3.2:3b-instruct-fp16 --keepalive 360m ``
```

2) Run server template in a new terminal 

```
INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack run .venv/lib/python3.12/site-packages/llama_stack/templates/ollama/run.yaml --image-type venv
```

or

```
INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack run /home/mcastrol/.llama/distributions/ollama/ollama-run.yaml --image-type=conda 

INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack build --template ollama --image-type conda
```

Commands

llama stack build --list-templates


3) Test client  connection in a new terminal (activate virtual environment)

Activate virtual environment

```
source .venv/bin/activate
conda activate llama-stack-play
```

```
llama-stack-client models list
```



