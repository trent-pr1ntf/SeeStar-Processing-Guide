# SeeStar Processing Guide
A beginners guide to processing images from the SeeStar. 

## Introduction
You may have noticed that the SeeStar application itself already produces great images! The SeeStar app does a lot of the heavy astrophotography heavy lifting for you, which is excellent. There is no need to take flats [link] or darks [link], as the SeeStar does this for you, if it's set up properly (those are turned on by default, more on that later). The app also stacks [link] your images for you, producing a ready-to-go image right away. There is no need to do any kind of "stretching" [link] to the image. 

You may notice, however, that your pictures don't look quite like some found online. The nebulas seem to pop out of the picture, the galaxies aren't drowned out by stars, and the darks appear, well, darker. You may see a comment of someone creating an image with 12 hours of data, but the sun isn't set for more than 10 hours this time of year. Sure, some people out there are spending thousands of dollars of equipment to get some of those shots, but your SeeStar is more than capable of producing great pictures with a little post-processing help. 

Trying to wrap your head around where to start, however, may be a bit overwhelming. There are some people out there that just get everything done in Photoshop [link], which is quite impressive technically. There's also a great piece of software called "Pixinsight" [link] designed specifically for astrophotography. It's a powerfull tool, but it has a steep learning curve, and it does cost money. Then there's Siril [link]. It's a free and open source astrophotography tool that I like to use. It's also powerful, coming with it's own steep learning curve. Each time I use it, I feel like I'm still learning something new. That's the software we'll be using in this guide. 

Like I said, it will be kind of an uphill climb at first, but hopefully I'll guide you to a great start. This article, albeit a bit technical, is meant for folks who just want to take the next step with their SeeStar data. The workflow I will be going into is one that I have landed on after months of trial and error. I've learned a lot, but it's not set in stone. What works for me tonight, will probably change in the next week. There are also new updates being pushed out by Siril, and the folks who publish scripts for it all the time. I hope this guide will get you kickstarted, and eventually you'll learn your way around the software, and you'll land on your own workflow. 

I'll try my best to make it simple, while also keeping the details in so you have little nuggets to go on if you want to learn more. This isn't going to be Astrophotography 101, but I still want to teach what these things are doing and why. If you get lost, refer to the glossary, or simply Google something to learn more. This isn't meant to be the only piece of literature to read. 

Well, now that we have created our universe, let's bake our apple pie. 

## SeeStar Settings
Before we get started with the software, let's dive into some settings in the SeeStar application itself that we'll need to set to get some better images. 

[Insert narrative and screenshots for enhacncing images, it takes darks]

The SeeStar also takes built in flats [link]. [Insert narrative and screenshots of flat taking]

Let's pause talking about about software for just a moment, and let's talk about mount modes. When your SeeStar gets delivered to your door, and you set it up for the first time, you are likely using Altitude/Azimuith (Alt/Az) [link] mode. [Insert narrative on how Alt/Az tracks, and using a leveling head to help]
[Insert screenshots of leveling]

Using Alt/Az mode usually limits you to 10 second exposures [link], just by the nature of how it tracks. Any longer, and you tend to get star trails in your pictures, and you generally can't use images with star trails. If you want longer exposure times, you'll need to upgrade to equatorial (EQ) [link] mounting. [Narratives and links to EQ wedges]. Since the EQ method doesn't make tiny corrections to track objects, instead moving with the rotation of the Earth, you can take longer exposures. Personally, I have found that 30 Second exposures work best. Almost all of my images don't have star trails. Some people make 60 Second exposures work, but your experience may vary.
[Insert images of polar aligning]

Remember, we're looking for as much light [link] data as possible, with the least ammount of noise [link]. One 30 Second exposure gets you a good amount of light, but with less noise than 3 10 Second exposures. I'm not saying you *need* to use EQ mode to have better picutres, but it does help. If all you have at your disposal is the ability to use Alt/Az mode, you can still come up with some great photos, it just make take more integration time [link], or total combined exposure time. 

To change your exposure time, while in Stargazing mode, click the three dots in the upper right (...), and select "30s" under Enhance EXP.
![Image](https://github.com/trent-pr1ntf/SeeStar-Processing-Guide/blob/e504c0a2fd0677782ff61414bdfb8741ec2fb55f/images/ExposureTime-1.png)
![Image](https://github.com/trent-pr1ntf/SeeStar-Processing-Guide/blob/e504c0a2fd0677782ff61414bdfb8741ec2fb55f/images/ExposureTime-2.png)

[Narrative and screenshots of saving each frame, and need for long integration times]
![Image](https://github.com/trent-pr1ntf/SeeStar-Processing-Guide/blob/b5130e2e15f07206eac02c8353b0ac2d9ffd9e90/images/SaveFrames-1.png)
![Image](https://github.com/trent-pr1ntf/SeeStar-Processing-Guide/blob/b5130e2e15f07206eac02c8353b0ac2d9ffd9e90/images/SaveFrames-2.png)

[Narrative about planning, reiterarting need for long integration times]

[Narrative about mosaic mode]

## Processing Software Installation
Now that we've looked at the SeeStar application itself, let's talk about the processing software we're going to use. You don't really need a top of the line computer to use this softwarem, but the higher the specifications, the faster the processing. If you have a computer with something like a gaming graphics card, you can also leverage that for faster processing times. Just remember, for this guide, you will need to use a computer. You can't use a phone with this specific process, although, there are apps for phones that can give you some good results. 

I personally use a Mac, but this software will also work with Windows, and most flavors of Linux-based operating systems. I'll try to keep the operating system specific stuff "OS agnostic," but generally the software will function the same no matter the operating system. (Sorry BSD fans, although Siril is ported to a few BSD's, this process won't work out on them)

The main piece of software I'll talk about in this guide is Siril [link]. This is the main application we'll use for all of the processing. We'll also talk about three other pieces of software that will require to be installed for our workflow, you can think of them as "plugins" or "extensions." They integrate with the Siril user interface directly. Lastly, we'll talk about an optional piece of software if you want to watermark your images, or do some touch-ups to our images. 

So, let's start with Siril. You can find it's download page [here](https://siril.org/download/). For this guide, I'll be talking about Siril 1.4.1, which is the latest version as of this writing. I'll try to keep up with any major changes as they come. Select the version for your operating system, and download then install. 

Next, let's install one of the important "plugin" peices of software, GraXpert [link]. This software can be used stand-alone to remove background gradients [link], and to denoise [link]. We'll go into what those are in a bit, but for now, just get GraXpert installed, we're not going to use it in stand-alone mode, instead we're going to tell Siril where it is, so we can use it directly from Siril. (We'll also go over that in a bit as well). Simply go to their homepage [here](https://graxpert.com/), download the right version for you opearting system, and install it. 

After that, we'll want to install Startnet++ [link]. It's used to remove background stars from your image to better edit the nebula or galaxy you are wanting to process. It's also a useful way to "tone down" the stars, so the nebula or galaxy is the main focus of the image. Some people may even choose to keep the stars removed, it just depends on personal taste. Just as with GraXpert, Starnet++ can be used stand-alone, but we won't be using it like that. Head over to there download page [here](https://www.starnetastro.com/download/), then scroll down to the bottom of the page to install the "Command Line Tool (v2.0.0)." Note that this doesn't have it's own installer like the others. I like to move the folder to where my operating system stores it's programs/applications to keep it simple, but you can place it where you'd like, just remember you put it. We'll need that path later. 

[Insert Cosmic Clarity install]

[Insert GIMP install]

## Setting Up Siril

## Setting Up Your Working Directory

## Workflow
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
- Histogram Stretch to darken darks
- Veralux Vectra if needed for tweaking colors
- Save starless
- Veralux Recomposition
  - Starmask linear
  - Starless stretched
  - Stretch in stars to taste
- Denoise if needed again
- Sharpen stellar data
- Save processed
  - Save as JPEG/TIFF
- Watermarking in GIMP

## Glossary

## Frequently asked questions

## Contributing

## Thank yous/Links
