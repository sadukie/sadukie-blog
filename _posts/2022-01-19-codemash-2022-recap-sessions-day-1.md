---
title: "CodeMash 2022 Recap - Sessions Day 1"
tags: comferences community
---

These are the sessions that I caught on the first day of sessions at CodeMash 2022.

## Dark UX Patterns

Vitaliy Matiyash took us on an adventure to see many of the dark UX patterns used on the web.

```
Checking out Dark UX Patterns with @VitaliyMatiyash at #CodeMash pic.twitter.com/XTn5MstByC

— Sarah Dutkiewicz (@sadukie) January 13, 2022
```

Do you really think you are the millionth visitor to this site? There are only 100 lucky users who live in the Philippines – could you be one of them? There are the websites that like using modals without an escape. Signing up for a service may be easy, but cancelling may be hard. Don’t forget those websites that want your information or will let you leave feeling bad by clicking links like “I don’t care what my cat eats” and “I am a bad person”. These are some of the many patterns that Vitaliy shows off in his talk. He offers up many of the dark UX patterns that are used on the web as well as solutions to get around them. For example, when working, make use of Focus Mode and Digital Wellbeing settings to help avoid getting caught up in doom scrolling. If you get a chance to catch this session, I recommend it!

## The Four Principles of Web Accessibility

Homer Gaines is one of the folks I follow with regards to accessibility on the web, so I was excited to catch an in-person session. He mentioned that accessibility is an EVERYONE issue, showing the various guidelines and laws from organizations throughout the world. He also pointed out that not all disabilities are visible, with nods to cognitive disabilities and long COVID. Homer also pointed out how lawsuits help to push for accessibility in desktop and mobile environments.

The four principles of web accessibility – remembered by the acronym POUR – are:

- **P**erceivable
- **O**perable
- **U**nderstandable
- **R**obust

Some of the things I took away from this session include:

- Applying empathy, as it applies to the POUR principles

```
Applying Empathy:
– What can I see or not see? (perceivable)
– What can I do and how? (Operable + understandable)
– Does it work with various devices? (Robust)#accessibility #CodeMash @xirclebox pic.twitter.com/lfW2ZCwk2w

— Sarah Dutkiewicz (@sadukie) January 13, 2022
```

- A is the bare minimum, and AAA is the most you can do – sometimes overkill. Achieving AA for accessibility is the sweet spot.
- The number one rule for ARIA is to not use it unless you really know what you’re doing. It is easy to try to take an ARIA-first approach and still have an inaccessible site. He told us a story of a place that took an ARIA-first approach and failed the keyboard test of accessibility.
- Tabindex values are much simpler – 0 to be in the tab ordering and -1 to be removed from the tab ordering. Let the browser handle the ordering.
- Take advantage of semantic markup, as it works well with accessibility.
- The first tool he recommended for accessibility scans is AXE by Deque for automated accessibility testing.

While I don’t spend as much time in the web development realm nowadays, I find it important to keep learning these skills as I never know when I will get back into it.

## Where has Jane Gone?

Of all the talks I looked at during the speaker selection phase, this was one I really wanted to see. While there’s the question of why aren’t there women in tech, we also have the problem of retention. Statistics show that retention of women in tech over 35 years old is a big problem. Karen Linden shared with us many of the pain points she has experienced in her career as well as what others have experienced.

```
Looking forward to this talk about where women in tech have gone. #CodeMash pic.twitter.com/8rWdVFlUMX

— Sarah Dutkiewicz (@sadukie) January 13, 2022
```

From harassment to people taking credit for your ideas to being pushed more towards soft skills and non-technical roles, these are some of the many pain points that we may experience. But with the pains that we’ve experienced, why do we stay? Honestly, we can’t see ourselves doing something else that would feel right for us. Personally, I’ve had a lot of allies who have encouraged me and supported me. I’ve had friends, family, and community members help me build my confidence in who I am. And nowadays… I need to be part of the representation for the 35 and older crowd.

This talk – as well as talking with friends at lunch after the event – got me thinking a lot. From a conference speaker selection perspective, I can tell you that there aren’t a lot of submissions by women to begin with, let alone technical sessions by them. My goal for 2022 is to keep my presentations in the technical realm. Stay tuned for an upcoming post on this year’s conference and user group topics!

## Dungeons, Dragons, and Graph Databases

I was excited to see Guy Royse at CodeMash, and I was even more excited to see that he was talking about graph databases. When I saw his session abstract, I perked up at the mention of Cypher, wondering if Neo4j would be mentioned. However, I learned he was talking about [RedisGraph](https://oss.redis.com/redisgraph/#:~:text=RedisGraph%20is%20the%20first%20queryable%20Property%20Graph%20database,Primary%20features%3A%20Based%20on%20the%20Property%20Graph%20Model), which uses a set of query syntax from the Cypher language. I also learned about the existence of [openCypher](https://opencypher.org/).

I unfortunately didn’t stay long in Guy’s talk, as graph databases and Cypher were familiar topics for me and my low energy indicator was kicking in. So… off to lunch! But rest assured… RedisGraph is on my list of technologies to play with and also present on in the future.

## Implementing an Event Sourcing strategy on Azure

After lunch, I went off to see a talk delivered by Eldert Grootenboer and Olena Borzenko. I wanted to catch as many Azure Cosmos DB talks as I could since it’s a technology I worked with in my past and have returned to. I wanted to see what others were showcasing and how. Olena was presenting remotely, and the demo gremlins behaved. I really appreciated how well Eldert and Olena co-presented the material. They explained the event sourcing pattern and working with materialized views. They also talked about the Azure Cosmos DB change feed and ways to work with it via push, pull, and Azure Functions. It was an information-packed session!

## Putting the FUN back in Fundamentals

In the last post, I mentioned catching one of Matt Williams’ KidzMash sessions. For the last session of the first day of conference talks, I caught his session on putting the fun back in fundamentals, exploring data structures, algorithms, and more. He talked about a variety of algorithms and how they apply with Big O complexity. Some algorithms that made appearances include the galloping search of 1976, interpolation search, and substructure search. Some data structures that made appearances include linked lists, doubly linked lists, ring lists, trees, hashes, cuckoo hashes, peacock hashes, and sets. The concept of memoization also made an appearance. These were topics I found boring early in my career because I didn’t have a good understanding of how to apply them. However, more than 20 years later, I go to sessions like these to reaffirm my understanding and remind myself that topics can make sense with good teachers.

## Conclusion

For the first day of sessions, I made it to many of the ones I wanted to catch. I came out with a lot of takeaways, and I look forward to putting the knowledge to use over the next few weeks. There were more sessions on the second day of sessions, so stay tuned for the next post!