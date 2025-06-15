---
title: Stir Trek 2025 recap
description: "From front-end technologies to .NET-related topics, these are some of the things Sadukie shares from Stir Trek 2025!"
tags: conferences careers
---

On May 2nd, I had the opportunity to attend [Stir Trek](https://stirtrek.com). While [Dante kept telling me "I'm not supposed to be here today"](/2025/05/01/not-supposed-to-be-here), I knew the universe had reasons for playing out like it did. So for that, I'm thankful!

There was a lot of learning to be had, conversations to be had, and people to see. You know how that goes - not all the things got done. But what I wanted to get done managed to happen. So let's recap some of the event!

## Kathryn Grayson Nanz's "I Didn't Know that HTML/CSS could do THAT!"

I've seen Kathryn's talks in many of the conferences that I've done session review for. It's been on my list to catch one of her talks, and when there's a talk about HTML and CSS, I'm in! These are technologies I've been playing with since the mid-90s. That means I'm nearing 30 years of playing in this space. 

I appreciate that Kathryn and Alex Riviere talked about the contents of their sessions and divided and conquered the HTML and CSS adventures. Kathryn also did a great job of explaining CSS specificity as a sidebar. However, CSS specificity isn't just a sidebar - it's a critical foundation for CSS. I've worked with so many people who hadn't heard of it or knew about the browser plugins that calculate it for us nowadays. It was neat to learn about `:where()` and how its specificity is [0,0,0,0]. It'll be nice to write CSS rules where I can be more clear as to why this is important and not give up with `!important`.

I was excited to see things like `accent-color`, `clamp()`, `<dialog>`, `popovers` and the painful `inert` (more on this later). It was also good to see things like `:is()` and `:has()`.

I also wiped tears away at the `rebeccapurple` on one of those slides. It wasn't called out. And while it's a IYKYK (If You Know, You Know) thing, I still want to call it out. Here's [Eric Meyer's thoughts on rebeccapurple](https://meyerweb.com/eric/thoughts/2014/06/19/rebeccapurple/).  I get teary-eyed because I heard [Eric's "Designing for Crisis" talk](https://www.youtube.com/watch?v=qyZq6v3vZqo) at World Usability Day 2014. I appreciated seeing that `rebeccapurple` mention.

This session really woke up my inner CSS/HTML geek.

## Brendan Enrick's "Not Your Mother's or Father's C#"

This is another one of those talks that I've been meaning to catch. I know that Brendan changes it up as C# changes. So I was curious to see what kind of things he'd cover in this particular delivery. I appreciate that he addresses the myths that people have about C# development - it's not just Visual Studio. It's not just Windows. It's not enterprise only. It's not just monoliths.

In this talk, he has a lot of features of C# that he calls out. Every time I see that C# got `params`, I think of Python's `*args` and `**kwargs`. There's still no `**kwargs` equivalent in C#. `params` has to be the last parameter, so it stops at the `*args` equivalent. `**kwargs` is essentially a Dictionary that follows after `*args`, so with the current implementation of C#, that wouldn't work. Nothing comes after `params`.

Then there were mentions of string interpolation - which I also am a huge fan of. He also showed raw strings and interpolation in raw strings. While that can get scary to work with, it was good to see how that could be accomplished. Again, my Python brain was happy to see f-strings and raw strings. The implementations translated well with my brain. The one thing that wasn't called out though is that you have to be careful with string interpolation and timing. Structured loggers - such as Serilog - don't always work well with interpolated strings. So consider that when working with strings and whether you want to use interpolation.

Another concept that Brendan pointed out is Overload Resolution Priority. This one allows you to set the priority for method overloads to make it easier for the compiler to determine which method to use when their specificities match. This caught my attention because I never really thought of [method specificity in C#](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/proposals/csharp-13.0/overload-resolution-priority). It got me thinking, though. 

There were plenty of other features mentioned, and that's why I like this talk. Brendan did what he could to cover as many different features and hidden gems of C# in 45 minutes. I know there were features he didn't have time to show. This is a talk that makes you realize how vast C# is and yet how much room there is for growth as well.

## Jeff Fritz's "Beyond the Basics - Building Reusable Code with Blazor"

The title here is truth in advertising - if you wanted the basics of Blazor, there are plenty of materials out there to learn from. This talk was not about basics of Blazor. This was live coding a weather forecast grid and taking it to a reusable grid component. In this talk, I was able to see the steps happen live. It was great to see the thinking parts, why things get pulled out the way they do, and how to make that happen in Blazor. Jeff talked of `[Parameters]`, `<ItemTemplate>`, and `<Columns>`. He talked of the Blazor cycle and cascading parameters. He also mentioned attribute splatting with `@attributes` and `CaptureUnmatchedValues`. He mentioned that components can be styled with CSS using the CSS isolation concept. He also talked of packaging the component to share it. This was a fantastic talk on creating your own reusable components.

## Jeff Fritz's "Let's Aspireify a Real World App"

In this talk, Fritz showed us [Aspireify](https://aspireify.net), walking through how .NET Aspire works, the features, and showing how he evolves from regions to extension methods. This is a good start for understanding the potential of .NET Aspire. There's a lot that can be done, and Jeff does a great job of pointing that out. I liked how he asked if [Ardalis](https://ardalis.com) was around before he mentioned regions. 😂 I don't think he realized though that I also do not like regions. I get it from a presentation stand point, but it doesn't make me dislike them less.

Aspireify is not a small project. There are a lot of Aspire components. However, he did mention that he has it running for less than $20/month. It isn't as expensive as people thought it might be. He did a good job of pointing out that Azure isn't necessarily as expensive as we may think.

He also talked about deploying Aspire using [the `azd` CLI tool](https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/) with the following steps:

1. `azd init`
2. `azd pipeline config`
3. `azd up`

Another key point he stressed was that if you're using container images, make sure to prune them every now and then. You have a set amount of space for storage for [the different tiers of Azure Container Registry](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-skus), and Azure Container Registry will not remove unused images on its own by default. Something he didn't mention along these lines is the `acr purge` command to help with that. However, note that there is a bit of risk that comes with using it, so [read the docs and understand the risk before using it](https://learn.microsoft.com/en-us/azure/container-registry/container-registry-auto-purge).

## Burton Smith's "Using Web Components to Scale Your UX"

This talk was good insight on web components, custom leements, shadow DOM, and HTML Templates. Burton made points on scenarios where web components make sense and where web components may have issues. He did a great job of explaining the shadow DOM - that's a concept that can easily be misunderstood or just not understood in general.

There were a lot of resources for learning about web components and the tools out there that he uses with them.  These included:

- Libraries to write components
  - FAST
  - lit
- Compilers for web components
  - Stencil
  - Svelte
  - Solid
- Frameworks
  - Angular Element
  - Preact
  - Vue

He talked about how custom elements can integrate with a variety of tools and frameworks - including ASP.NET, React, Angular, Vue, Svelte, Solid, Storybook, and more! He also mentioned the Custom Elements Manifest as well as the Web Components Toolkit.

I wanted to catch this talk to learn more about web components as well as catch a Burton talk. I've always heard rave reviews of his workshops and sessions at conferences, and this one was no different. He has a great stage presence and great presentation.

## Alex Riviere's "Hot New HTML"

Alex is another one of those speakers I hear good things about at other events as well. Did I mention that I like how Alex and Kathryn collaborated behind the scenes to cover some different parts of HTML and CSS? There was some overlap, but it was from a different perspective. Some of the concepts Alex covered included `<summary>/<details>`, `::details`, `<dialog>`, the Anchor API, the Invoker Command API, the Popover API, `attr()`, and styling `<select>` elements.

I liked seeing `<summary>/<details>` on his list. I had just used those in [eShopOnWeb's FAQ](https://nimblepros.github.io/eShopOnWeb/faq.html), so it's good to see it's a newer feature. Alex also mentioned the dreaded `inert`. I mention painful and dreaded with this feature because a lot can go wrong if it's misused. This removes things from the accessibility tree - which I can see as a good thing if we need to reduce the chatter on a screen reader. However, this also means removing things like `click`, `focus`, and even the searchability of `Ctrl+F` in the browser. If controls are meant to be disabled, use `disabled`, not `inert`. There isn't a good enough case to recommend using it - just be aware of the nightmares of it.

I was surprised to see how you can trigger a dialog and close a dialog with minimal code. No more z-index struggles with modals - `<dialog>` gets placed in the top layer of rendering. I also need to look more into the Anchor API and the Popover API to see how they work.

Alex also had a demo of `<marquee>`. 😂 His handwritten font choices as well as his style reminds me of how much I love HTML and CSS and can't create a pretty initial design. Give me functional, and give me the tools to know what I have available in CSS. Let me play. I get the playful yet informative vibes in Alex's talk.

So much to look into!

## Eric Potter's "HTMX: What's the big deal with the little framework?"

This was the last session of the day for me. One of the goals I have for work currently is to learn about HTMX. One of my teammates did a lunch-n-learn on it, and I wanted to see others' perspectives as well. While Eric ran into technical difficulties, he did a great job of covering HTMX, how it works versus how the other options out there work, and mentioned trade-offs of the various tools and platforms. There's a time where HTMX's simplicity makes sense. So it's something for me to consider playing with.

## Conclusion

Overall, the content at Stir Trek 2025 was fantastic! I've got a lot of things to go and explore. The inner front-end geek in me is awake and ready to play! Thanks to all of the organizers for making the event happen, to the volunteers who helped make it seem smooth running, to the speakers who brought awesome content, and to the rest of the attendees who also give the organizers/volunteers/speakers reasons for putting on this conference. To finally experience Stir Trek as an attendee, it has been a blast!
