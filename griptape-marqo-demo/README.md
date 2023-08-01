# Griptape Chat Demo

The demo uses [Gradio](https://www.gradio.app/) for the frontend and [Griptape](https://github.com/griptape-ai/griptape) and [Marqo](https://github.com/marqo-ai/marqo) for the backend.

## Get the code
```shell
git pull git@github.com:griptape-ai/griptape-chat.git
cd griptape-chat
```

To know more, refer to the Marqo getting started guide [here](https://github.com/marqo-ai/marqo).

## Setting up the runtime environment
Create file called .env in the root of this project directory and add the following content:
 ```shell
 OPENAI_API_KEY=your key here
 ```

*optional: if you want to run this on a port other than the default gradio port of 7860 you  can add 
GRADIO_PORT=<your port here> to the .env file as well*

### OpenAI API Key
We'll need to obtain our OpenAI API key. Follow the steps below to do so:

1. Head to [OpenAi's official website](https://platform.openai.com/) and either create or login to your account.
Once you are logged in, click on the "Personal" text on the top right of your browser and then click on 
"View API keys" from the context menu that appears.

1. Click on "+ Create new secret key" and give it a name.
1. Copy the key and paste it in the .env file in the root directory of this project. Replacing "your key here" 


## Running the Demo

### Run Marqo Locally
1. Marqo requires docker. To install Docker go to the Docker Official website. Ensure that docker has at least 8GB memory and 50GB storage.

2. Use docker to run Marqo (Mac users with M-series chips will need to [go here](https://github.com/marqo-ai/marqo#m-series-mac-users)): 

```shell

docker rm -f marqo
docker pull marqoai/marqo:latest
docker run --name marqo -it --privileged -p 8882:8882 --add-host host.docker.internal:host-gateway marqoai/marqo:latest
```

### via poetry
```shell
poetry install
poetry run python app.py
```