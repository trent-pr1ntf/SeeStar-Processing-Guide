# SeeStar Processing Guide
A beginners guide to processing images from the SeeStar. 

## Introduction
You may have noticed that the SeeStar application itself already produces great images! The SeeStar app does a lot of the heavy astrophotography heavy lifting for you, which is excellent. There is no need to take flats [link] or darks [link], as the SeeStar does this for you, if it's set up properly (those are turned on by default, more on that later). The app also stacks [link] your images for you, producing a ready-to-go image right away. There is no need to do any kind of "stretching" [link] to the image. 

You may notice, however, that your pictures don't look quite like some found online. The nebulas seem to pop out of the picture, the galaxies aren't drowned out by stars, and the darks appear, well, darker. Sure, some people out there are spending thousands of dollars of equipment to get some of those shots, but your SeeStar is more than capable of producing great pictures with a little post-processing help. 

Trying to wrap your head around where to start, however, may be a bit overwhelming. There are some people out there that just get everything done in Photoshop [link], which is quite impressive technically. There's also a great piece of software called "Pixinsight" [link] designed specifically for astrophotography. It's a powerfull tool, but it has a steep learning curve, and it does cost money. Then there's Siril [link]. It's a free and open source astrophotography tool that I like to use. It's also powerful, coming with it's own steep learning curve. Each time I use it, I feel like I'm still learning something new. That's the software we'll be using in this guide. 

Like I said, it will be kind of an uphill climb at first, but hopefully I'll guide you to a great start. This article, albeit a bit technical, is meant for folks who just want to take the next step with their SeeStar data. The workflow I will be going into is one that I have landed on after months of trial and error. I've learned a lot, but it's not set in stone. What works for me tonight, will probably change in the next week. There are also new updates being pushed out by Siril, and the folks who publish scripts for it all the time. I hope this guide will get you kickstarted, and eventually you'll learn your way around the software, and you'll land on your own workflow. 

I'll try my best to make it simple, while also keeping the details in so you have little nuggets to go on if you want to learn more. This isn't going to be Astrophotography 101, but I still want to teach what these things are doing and why. If you get lost, refer to the glossary, or simply Google something to learn more. This isn't meant to be the only piece of literature to read. 

Well, now that we have created our universe, let's bake our apple pie. 

## SeeStar Settings

## Processing Software Installation

## Setting Up Siril

## Setting Up Your Working Directory

## Workflow

## Outline of planned document
- Introduction
  - Comparing SeeStar Software to Siril
  - Audience
- SeeStar Settings
  - Save frames
  - Exposure times
  - EQ Mounting
  - Planning
  - Mosaics
- Processing Software Installation
  - Siril
  - GraXpert
  - StarNet++
  - Cosmic Clarity
  - GIMP
- Setting up Siril
  - Telling it where GraXpert is installed
  - Telling it where StarNet++ is installed
  - Installing scripts
    - SeeStar Processing
    - DSA SeeStar Mosaic Processing
    - GraXpert
    - AutoBGE
    - Cosmic Clarity Sharpen
        - Tell it where Cosmic Clarity is installed
    - Veralux Stretch
    - Veralux Recomposition
    - GAIA Archive Installation
- Setting up your working directory
  - New directory
  - Create lights directory
  - Connect to SeeStar
    - Wired
    - Wireless
    - Selecting FIT files
  - Transfer files
- Workflow
  - Set home directory
  - Stacking
    - Standard stacking
    - Mosaic stacking
  - Open stacked FIT
  - Autostretch for better viewing
  - Cropping
    - Save cropped for mosaics
  - Background extraction
    - GraXpert
    - AutoBGE
    - Siril built in overview
  - Plate solve
    - Manually solve via search
  - Spectrophotometric color calibration
  - Remove stars
  - Set to linear mode
  - Verlux stretch
    - Set sensor
    - Log D
  - Denoise
  - Sharpen
    - Hardness
    - Non-stellar
  - Save starless
  - Veralux Recomposition
    - Starmask linear
    - Starless stretched
    - Stretch in stars to taste
  - Denoise if needed again
  - Sharpen stellar data
  - Histogram Stretch to darken darks
  - Save processed
    - Save as JPEG/TIFF
  - Watermarking in GIMP
- Glossary
- Frequently asked questions
- Contributing
- Thank yous/Links
