# AugBres
      
## About
    full name: Automatic Gui Bug Reproduction based on Screenshots 
    currently only supporing Android applications
   1. constructs GUI model simulating app behavior
   2. takes error screenshots as bug oracle
   3. matches oracle screenshots in GUI model based on CNN (image classification)
   4. performs guided GUI exploration targeting at matched node
  



## Test executor
   we use  [Droidbot](https://github.com/honeynet/droidbot) as the base testing engine for testing Android apps.
   we use  [Gator](https://github.com/cce13st/Gator) as the static analysis tool for inferring GUI model
   - systematically explores app
   - infers GUI model armed with runtime screenshots. One node corresponds to one or more screenshots.
   - performs guided exploration of GUI model at the last phase of AugBres where end point is the target node.
   - generates reproduction traces for GUI bug

## How to define a target node?
   - classify the oracle screenshot into corresponding screen node in GUI model
   - label: node ID
   - training data: runtime screenshot
   - testing data: oracle screenshot
   - learning model: Inception v3
