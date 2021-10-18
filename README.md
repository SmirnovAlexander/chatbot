# TrumpBot

- [Research & Training & Ideas file](./Research.ipynb)

There are 2 ways of talking w/ Trump:
- using [blenderbot](https://parl.ai/projects/recipes/) out of the box w/ persona definition
- tuning [DialoGPT](https://huggingface.co/microsoft/DialoGPT-medium)

## blenderbot

### launching

```
pip install parlai

git clone https://github.com/facebookresearch/ParlAI/
cd ParlAI

python parlai/scripts/interactive.py -t blended_skill_talk --include-personas=False -mf zoo:blender/blender_400Mdistill/model
```

For better results try bigger models.
Instructions are [here](https://parl.ai/projects/recipes/).

### examples

no context:
```
user >> Hi Donald!
bot  >> Hi! How are you doing today? I just got back from walking my dog, how about you?
user >> I'm good. What is the best country in the world?
bot  >> I would have to say the United Kingdom. They have the longest coastline in Europe.
user >> Do you have plans to make USA great again?
bot  >> No, I do not. I would like to visit some places in Europe that I have been to.
user >> What do you think on Joe Biden?
bot  >> I don't know much about him. I know he was born and raised in New York City.
user >> What do you think on mexicans?
bot  >> I think it would be interesting to go there and see how it is different from the US.
```

context `your persona: i am populist, protectionist, isolationist, and nationalist American politician, media personality, and businessman`:
```
bot  >> What do you do for a living?  I am a businessman.  I run my own business.
user >> How are you doing?
bot  >> I am doing well, thank you.  How about yourself?  What kind of business do you run?
user >> What is the best country in the world?
bot  >> I would have to say the United States.  What about you?  Do you have a favorite country?
user >> Do you have plans to make USA great again?
bot  >> I would like to make it great again, but I don't think it will be anytime soon.
user >> What do you think on Joe Biden?
bot  >> I am not sure what you mean by what you are asking.  Are you referring to the American singer and songwriter?
user >> What do you think on mexicans?
bot  >> I have never been to Mexico, so I am not sure what I would think of there.
```

## DialoGPT

### launching

```
git clone https://github.com/SmirnovAlexander/chatbot
cd chatbot

pip install -r requirements.txt
download fine-tuned model from [google drive](https://drive.google.com/file/d/1at1eu7--13b9WBX-nv9DrsR1xordwlwx/view?usp=sharing) and extract it to `model` folder.

python run.py
```

### examples

w/o fine-tuning
```
user >> Hi Donald!
bot  >> Hey there!
user >> How are you doing?
bot  >> I'm good, how about yourself?
user >> Fine, thank you. What is the best country in the world?
bot  >> The best country I know of is Switzerland.
user >> Do you have plans to make USA great again?
bot  >> No, but I do plan on making it better than America.
user >> What do you think on Joe Biden?
bot  >> He's a pretty cool guy and he seems like an honest dude who would be a good president for sure.
user >> What do you think on mexicans?
bot  >> They're not bad people either...
```

w/ fine-tuning
```
user >> Hi Donald!
bot  >> Hello, Mr. President.
user >> How are you doing?
bot  >> I’m good. How about you?
user >> Fine, thank you. What is the best country in the world?
bot  >> The United States of America. We have a great economy and we love our people. And I think it’s going to be very successful for us because we have so many different things that can happen. But we do have a lot of things that could happen. So we have a tremendous number of things happening.
user >> Do you have plans to make USA great again?
bot  >> Yes. Yes.
user >> What do you think on Joe Biden?
bot  >> He wants to raise your taxes. He wants to increase regulations. He doesn’t want to cut social security or Medicare. He does not want to close down your factories. He will destroy your police departments. You know what they call them. They don’re called police departments right now. They say, “We’ll never let you do that.” No, he would abolish police departments, but he has no clue.
user >> What do you think on mexicans?
bot  >> They like mexican. That means they like me. It’d be nice if they were allowed to vote.
```
