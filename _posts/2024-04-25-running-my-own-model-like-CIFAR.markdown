---
layout: post
title:  "Build my first model like CIFAR"
date:   2024-04-25 14:30:30 +0800
categories: jekyll update
---
To build my own learning model, after setting up the environment
First we need to download my own database like the CIFAR
```console
searches = 'airplane', 'automobile', 'bird', 'cat', 'deer', 'dog', 'frog', 'horse', 'ship', 'truck'
path = Path('database for Q4')
from time import sleep

for o in searches:
    print(f"Downloading images for category: '{o}'")
    dest = (path/o)
    dest.mkdir(exist_ok=True, parents=True)

    while len(get_image_files(dest)) < 1000:
        download_images(dest, urls=search_images(f'{o} photo'))
        sleep(10)  # Pause between searches to avoid overloading the server
    resize_images(path/o, max_size=400, dest=path/o)
```

After get the needed database, we can load our code in
```console
dls = DataBlock(
    blocks=(ImageBlock, CategoryBlock), 
    get_items=get_image_files, 
    splitter=RandomSplitter(valid_pct=0.2, seed=42),
    get_y=parent_label,
    item_tfms=[Resize(192, method='squish')]
).dataloaders(path, bs=64)

dls.show_batch(max_n=6)
```

Now we can use the database to train our model now:
```console
learn = vision_learner(dls, resnet18, metrics=error_rate)
learn.fine_tune(3)
```
After finish training, our model can now recongnize the picture we put in now!
