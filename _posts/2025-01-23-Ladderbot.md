---
layout: post
title: "Ladderbot"
date: 2025-01-23
---

# Ladderbot and personal software

A few years ago I had seen a hackernews post for a site called 12footladder or something like that. Well that site eventually got banned and shutdown by vercel. 

Before that banning, I realized I had the small skillset to develop a sort of "toy like" implementation of the feature "to look over the paywall" and do it as a slack bot. This was also at the same time that Github's Copilot was kicked off so I had the confidence to connect all the pieces together and have Copilot be the glue that helps me solidify all the concepts together and fill in some of the gaps when didn't know how to implement something.

![old Dale-2 generated image of a person on a ladder in a garden looking over the wall of the garden](assets/images/posts/2025-01-23-ladderbot/ladderbot.png)

The original for Ladderbot idea was to have use slack's message API that can recognize up to 5 URLs and fire a webhook send Ladderbot the URL and Ladderbot reply with the archive.today short link. 

A few hours of fussing and unable to get around "looks like a bot we don't serve your kind" responses from archive, I realized that arcive.today has a search route for a posted URL. 

It felt a little clunky, but I didn't care, I was able to use the message from Slack containing the URL, and give the user a response in a thread with a link to the archive.today search result if one exists. From there it's up to the user to click on the link and "peer over the paywall" if an archive exists. 

What's been really fun about this small piece of personal software is that it's been very stable. So far it has 22 commits. The first is on November 21, 2022. The next 21 commits are all on November 23, 2022 as I was locked in on getting it working in our slack group. It's now been 792 days since my last commit and I have made a small improvement that was mostly cause I realized there was one small problem with the experience.

![my last two commits, January 23, 2025, and November 23, 2022](assets/images/posts/2025-01-23-ladderbot/commit-gap.png)

If a URL was posted from a shared link like an app or email, it is almost always guaranteed to have URL parameters. Those URL parameters could throw off the search on archive.today, making it appear as if the article was not archived yet. Manually removing the parameters and searching usually worked but a week ago I realized that I could just do that on the server/api side and not have to remind my friends that they "should" remove the parameters from links that they wanted share. 

A lot of my "now" projects are similar in nature to Ladderbot. Small, contained, and personal software solutions that I can build with the help of AI and launch to myself and my friends. We live in a pretty awesome future. 