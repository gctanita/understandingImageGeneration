# What is N8N and why use it?

N8N is an open-source workflow automation tool that can be installed and run locally. You have full control over your data, and it comes with a lot of integrations with other applications out of the box.

You can do a lot of stuff with N8N, and it can help you automate flows that would otherwise require a lot of your time. 

At the moment I've created 4 workflows in N8N that I am a bit proud of, and will present in separate posts. 



# My first N8N workflow: A story Creator to Discord
I wanted to create stories on the fly with what ever strange combination went through my head. And it was tedious work to speak with Chat GPT, and then tell him to generate chapter by chapter. I also wanted to see if I can do something decent locally. It's not perfect, it has some flaws, but my baby works :D 

The flow starts with a Chat Trigger Node, that receives the characteristics of the story: the plot, how many chapters and how many words per chapter. Then that input goes to a Basic LLM Chain node, that generates the story chapter, an overview, and the chapter names and chapter overviews. It is connected to an Ollama Model (I used a qwen2.5:7b-instruct-q4_K_M model) and gave the LLM Chain node a Structured Output Parser to put the information in a specific JSON. From there I connected to Discord, sent a message with the title and the plot, then the array of chapters entered a "Split out" node, that gave me control over the nodes. Next I loop over the items in the array, 1 by 1, post the chapter name to Discord, and provide another Basic LLM Chain node with a prompt to generate the story for chapter with name and plot. Initially the output was directly connected to Discord for output, however, a message on Discord has a 2.000 characters limit. To overcome this, I added some custom javascript code, that splits the story in multiple paragraphs, and then combines the paragraphs into chunks of maximum length of 2.000 characters. Each chunk gets sent to Discord. 

And stories get born :D 

