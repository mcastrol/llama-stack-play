# llama-stack-play


## Setup
1) create virtual environment 

```
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2) Build ollama template

```
INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack build --template ollama --image-type venv


## Startup client/server local mode


1) Open a terminal an start ollama model 

``` 
ollama run llama3.2:3b-instruct-fp16 --keepalive 360m ``
```

2) Run server template in a new terminal 

```
INFERENCE_MODEL="llama3.2:3b-instruct-fp16" llama stack run .venv/lib/python3.12/site-packages/llama_stack/templates/ollama/run.yaml --image-type venv
```

3) Test client  connection in a new terminal (activate virtual environment)

```
llama-stack-client models list
```



