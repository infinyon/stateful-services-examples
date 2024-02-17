# Overview

Simple example of using the OpenAI API to generate text.  It counds the number of attempts by model. The input is a model followed by sentence. 

For example, the following input:

```
hello world
```

use default gpt-3.5-turbo model to generate text.

But the following input:

```
gpt-4 hello world
```

use gpt-4 model to generate text.

# Set up

You must have account at [OpenApi](https://platform.openai.com/docs/overview) and setup an API key.  You can then set the API key in the environment variable `OPENAI_API_KEY`.

# Running

Assume you have an OpenAI API key in the environment variable `OPENAI_API_KEY`

```bash
$ ssdk generate
$ ssdk build
SSDK run -e OPENAI_API_KEY=$OPENAI_API_KEY
```

## Inputing text

```
$ fluvio produce sentence
gpt-4 tell me a story about boy and wolf
```

## Reading output

```
$ fluvio consume output
{"model":"gpt-4","output":"Once upon a time, there was a boy who cried wolf...", "total_attempts": 1}
```
