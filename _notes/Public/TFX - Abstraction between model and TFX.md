---
title: TFX - Enable Disable Cache For Each Components
date: 26/08/2023
feed: show
---
### Issues
- When developing model using python script or notebook and want to integrate with TFX, I found that TFX template (taxi) is make developer hard to interchangeable between TFX training code and Python training code
#### Goals
- Make "Model to TFX" process easier for update
- Make TFX training model script and Python/Jupyter notebook training script interchangeable
#### Ideas
- Design abstraction layer to separate between TFX area and Python Model area
- Try to use dependency injection instead global variable import

#### Notes
- However i didn't try this idea yet.