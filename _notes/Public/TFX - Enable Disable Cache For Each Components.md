---
title: TFX - Enable Disable Cache For Each Components
date: 26/08/2023
feed: show
---
### Issues
- When we have some upstream component that take long time for processing (e.g. example_gen) and we just want to debug or modify some script on downstream component (e.g. transform, trainer) so if we have to rerun all pipeline every time when change the transform, trainer code it will not productive because debugging cycle is too big.
### Goals
- Caching each TFX component separately by our control
### Solutions
- Set pipeline arguments "enable_cache = True".
- Set custom_config to component that we don't want to cache e.g. transform, trainer. because we want to debug this component after update preprocessing, training script.
- Every time you update preprocessing, training script and want to debug it you have to update custom config to make argument change for ignore cache.
- Now after we rerun pipeline it will use cache on component above transform instead processing from scratch and debugging cycle should be faster .  
### Notes
- TFX pipeline have argument "enable_cache" that when we set it to True it will use the last result of that component that have same component argument as current running component argument
### Examples
![[tfx_pipline_enable_cache.png]]
![[tfx_compoenet_cache_custom_config.png]]
