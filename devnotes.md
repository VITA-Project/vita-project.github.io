# General notes

remember the general cmd to create a requrements.txt is:
pip freeze > requirements.txt

# first setup of a baby autogen
pip install autogenstudio

autogenstudio ui

you'll need to generate an OpenAI API key at platform.openai.com
and enter that key in the appropriate location in the web ui

## running with claude: litellm(proxy)
you need to use litellm if you want to use claude or a local LMStudio model.
litellm acts as an adapter in these cases.

pip install litellm

if in codespace, you'll want to spin up another bash terminal (since your first one has autogen running)
and then we need to handle the port forwarding -- looks like with two terminals it properly auto portforwards both

looks like there's a missing dependency in litellm: litellm[proxy]
once you have that, you're set.

## misc lessons learned
autogenstudioui will report listening on 0.0.0.0 
that's not going to work, you'd use localhost (127.0.0.1) instead
the command line for litellm has to point to the exact claude model with date, and type is openAI (since we're using the adapter, we call it what it expects, not what it actually connects to)

for comparison, reference aider (https://github.com/paul-gauthier/aider) which appears to use a similar proxy for claude? (or not, but it's an interesting pair programming tool)

