---
title: "Vibe Coding a BINGO Caller"
description: "What happens when the BINGO caller can't make it to the family reunion? We vibe code one!"
tags: careers family
---

July is a busy month for me - from birthdays and anniversaries to prepping for my family reunion. I come from a very large family, and we all get together once a year to see each other. There are hot dogs, horseshoes, the business meeting, egg toss, kids' games, crafting contests, and BINGO!

We recently found out that our BINGO caller crew won't be able to make it. Today, [Ardalis](https://ardalis.com) asked if I had tried coding with Copilot - which I had in a Microsoft Learn path but not locally.

So this evening, I installed the GitHub Copilot extension in my VS Code and started to code using GPT 4.0.

**Note**: _I dedicate this post to my grandma. She introduced me to BINGO when I was a kid. We had great times at Easter Bunny BINGO. Gone 35 years but not forgotten._

## VibeBingo - the Console App

The first thing I had it do was a proof-of-concept in a .NET 9 console app. I had some very specific requirements:

- I gave it the letters/number range combinations for BINGO.
- A ball could only be called once per round.
- I wanted to be able to opt for multiple rounds.
- I wanted the balls called "letter-number", not "letter-digits".
- I also needed Text-to-Speech, as I'd like to play BINGO rather than be the caller.
- I want a board to show which balls were called.

It did a great job meeting these requirements.

But then I threw it a curveball - while I'm the command-line fiend, I needed a user-friendly Blazor WASM interface as well.

## VibeBingo - the Blazor BINGO Caller

It initially started off with the sample Blazor app.

I had it update the navigation to remove the default links. Eventually, we removed the `NavMenu` component as well as the top header.

I wanted to make sure that my colors of `LemonChiffon` and `DodgerBlue` were captured, and it did a pretty good job of using it.

I appreciated that I could tell it what colors I wanted and what to tweak in the design. The BINGO grid took a bit of getting it right, as it initially started with a bad flex-grid layout with letters next to each other. But I was able to work out the UX kinks.

![Bingo Caller Blazor app in Lemon Chiffon, Dodger Vlue, and green](/assets/images/vibe-coding-bingo/bingo-caller-blazor.jpg)

The Blazor component does support Text-to-Speech as well. However, when we added the dropdown to choose a voice, that caused the app to be unresponsive. So we backed that feature out.

## Additional Features

After the initial requirements, I threw a few more things at it:

- Adding an auto-caller feature with a selectable delay
- Adding Text-to-Speech voice selection to the console app
- Adding a caller mode - with the regular calls, Traditional (BINGO caller phrases), Kid-Friendly, and Pirate modes.
- Tidy up the console with Spectre.Console

For the Traditional caller mode, I fed it a URL with the traditional calls, and it created the dictionary plus all the other logic to make it happen.

This is the VibeBingo console app in action:

<video src="/assets/videos/vibe-coding-bingo/VibeBingo-console-app.mp4" controls style="height:300px;"></video>

You can see the code for this in my [vibe-bingo repo](https://github.com/sadukie/vibe-bingo).

## Conclusion

Having done natural language processing and taken a few courses on prompt engineering, I felt very much in my element with using GitHub Copilot to generate code. It was great that I could use prompts in my own natural language and not have to stretch into other domains. It just felt natural. I see AI as a tool that can be useful. But keep in mind - I've been in dev for a couple decades now, so I have a better grasp of when it's going down the hallucinogenic path and challenging it.

I don't recommend this for those who are just starting out. As I used to tell my students, **you can't use others' code in your own code unless you can explain it.** That rule applied to StackOverflow and blogs back then. It also applies to AI-generated code today.

Would I write my code like this normally? For proofs of concepts and learning tools, I might use this to help me get through that. Again, though, it's because of years of experience and solid debugging skills that I would take it on. Professionally? It depends - as long as it's mostly genericized code.

I'm still nervous about using AI tools with real code. I don't trust them. I don't want to leak someone else's intellectual property. So there's always that nervousness.
But if I'm not near those boundaries, then I'll play where I can.