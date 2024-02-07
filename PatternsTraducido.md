[](#welcome)**Welcome**,
========================

This wiki is where we will learn how to edit the background moving theme and use your own images. It will be a fun and informative experience, especially if you are bored of the same old themes. At least i hope. 😀

[](#what-you-will-learn)What You Will Learn:
--------------------------------------------

In this tutorial, you will learn how to take a pattern image with a 1:1 scale, which can fully and seamlessly duplicate and create a giant wallpaper. You will then zoom in to a corner and move to the opposite corner before returning to the original position. The back and forth movement will continue until the frame limit is reached, which is 64000 frames (7.5~ minutes).

[](#what-is-a-animated-background-theme)What is a animated background theme?
----------------------------------------------------------------------------

First, let's talk about the basics of creating a moving background theme. A moving background theme is essentially a image file that is looped continuously in the background of your Nintendo Switch home menu. The image is usually made up of a repeating pattern or image that is scaled and moved to create a sense of motion.

[](#requirements)Requirements:
------------------------------

To create your own moving background theme, you'll need a few things:

1.  A pattern or image that can be seamlessly repeated and scaled.
2.  An editing software that allows you to edit images.
3.  [Switch Theme Injector](https://github.com/exelix11/SwitchThemeInjector)
4.  Knowledge on how to edit a JSON.

[](#example)Example:
====================

Let's start with the first step, which is finding a pattern or image that can be seamlessly repeated and scaled. One easy way to do this is to use a program like Adobe Photoshop or GIMP to create a repeating pattern. In this example i will use Photoshop. If you go to Pattern Preview you can basically check what you will get. ![1](https://user-images.githubusercontent.com/93286561/222496034-8ad8d9f6-cbec-4dd3-99ff-18c770157341.jpg) ![2](https://user-images.githubusercontent.com/93286561/222496353-e69c804c-39a6-465c-95f5-bf308e841b18.jpg)

After that, you'll need to resize the image with the size of 1280x720 which is necessary since the nxtheme requires an image that is 1280x720. The image will be deformed, but that is okay. In the animation, we can change the scale of the X position, giving it a 1:1 aspect ratio again.

![3](https://user-images.githubusercontent.com/93286561/222497174-49542687-a230-417d-a4bc-d44139292d78.jpg)

Once you have your pattern, you'll need to export it as JPG, dont export it as PNG because we dont want transparency.

After that, you can use this JSONs template that I use on my theme Patterns.

[Patterns. JSONs Vertical & 1x1](https://github.com/zzzribas/Patterns/tree/main/JSON%20TEMPLATE%20FOR%20ANIMATION)

If you want to use your own JSON theme, you need to change the blyt/BgNml.bflyt pane in the main menu JSON to the one bellow:

`{ "FileName": "blyt/BgNml.bflyt", "Patches": [ { "PaneName": "P_Bg_00", "Position": { "X": 5000.0, "Y": 60000.0 } } ], "AddGroups": [ { "GroupName": "G_ZBG", "Panes": [ "exelixBG" ] } ], "Materials": [ { "MaterialName": "P_Custm", "Refs": [ { "Name": "White1x1A128^s", "WrapS": 5, "WrapT": 5 }, ], "Transforms": [ { "Name": "White1x1A128^s", "ScaleX": 10, "ScaleY": 10 } ] } ] }`

![4](https://user-images.githubusercontent.com/93286561/222501806-a8d6af91-1a4b-453f-bec6-405b9b89b4bf.jpg)

**Change to:**

![5](https://user-images.githubusercontent.com/93286561/222501842-1bb1c548-400b-40d2-8960-e2c86fc292df.jpg)

This code tells how the Background will behave in the menu.

*   The position, as I said before, since we are zoomed, needs to be in the corner.
*   The wrapT and wrapS to 5 mean that the image will duplicate and create a pattern.
*   The scale is the number of repetitions the pattern will make. The bigger the number, the smaller the bg will be.

Only do this **AFTER ALL YOUR EDITS ARE DONE IN THE SWITCH LAYOUT EDITOR**, the Switch theme injector isn't ready for moving themes and will replace this pane with the default Diff. So it's really important to change the blyt/BgNml.bflyt after you DIFF and are ready to.

Next, animations. If you use my JSON the animation is already set, but let me explain what everything does. This BLFAN RdtBase\_Enter.BFLAN is main BLFAN for the animated background, is the one that the Switch calls when entering the first time into menu.

For this tutorial lets ignore everthing else besides these 4 entrys in the FLPA. We are using the Switch Layout Theme Editor. The first entry corresponds to the X position of the wallpaper. Its animationTarget 0.

![6](https://user-images.githubusercontent.com/93286561/222505972-a3559480-524a-4dfc-8187-9c0df5720927.jpg)

As you can see we are moving the X value from -1800 to 1800 back and foward, that means the image is going from one coordinate to another every 8000 frames.

The same for the Y Value. Its animationTarget 1.

![7](https://user-images.githubusercontent.com/93286561/222506868-9285aa8d-be8b-4cf3-ab22-8ccaf9f186e5.jpg)

Next two are Scale of X and Y of the image. Here is where we can change the image from 1280x720 to 720x720, this value must stay the same for best results.

![8](https://user-images.githubusercontent.com/93286561/222507258-fa7c05da-04d3-4e75-8fc9-ce5652daee85.jpg)

![9](https://user-images.githubusercontent.com/93286561/222507268-2e710866-555f-4a7c-91c1-f0c32096d186.jpg)

Now, we need to replicate all of this to all these BFLANS:

*   RdtBase\_GameOut.bflan
*   RdtBase\_GameOutHideCnt.bflan
*   RdtBase\_StarterEnter.bflan
*   RdtBase\_Enter.bflan
*   RdtBase\_SystemAppletOut.bflan

**If all this is a bit confusing to you i recommend you to use my JSON and make small changes to these values from there instead of starting everything from the beginning.**

That should be it. You'll need to use the Switch theme injector to create your new theme, using your image and the edited JSON.

[](#final-thoughts)Final Thoughts
=================================

By following these steps, you can create a fully customized moving background theme for your Nintendo Switch. It may take some time to get everything set up, but the end result is a unique and personalized theme that you can enjoy every time you use your Switch.

That's all! If you have any questions, feel free to ask anytime. I hope this tutorial helped you create a moving theme for your Switch. Have fun and be creative!

Result:

![IMG_3654_1](https://user-images.githubusercontent.com/93286561/222519069-6857b0df-0938-4f78-9e85-5a111598056c.gif)
