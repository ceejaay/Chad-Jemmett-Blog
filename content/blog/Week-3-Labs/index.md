---
title: Week Three of Labs
date: '2019-01-25T22:40:32.169Z'
---



###Individual Accomplishments

[Time Planner Whiteboard problem](https://www.youtube.com/watch?v=sSoHwSHUkHQ)

##### Our Team's graph.
![Team Graph](graph_image.png)

This week I did a lot of work by myself. I had to be out-of-town for part of this week. So I spent part of the weekend trying to get ahead. Working solo on a large-ish code project is difficult.  I didn't want to disturb my teammates while they were taking time off. So I had to decipher some of the code myself. Working on a team you only see bits of the codebase. So there's lots of parts that you don't see. So it can be difficult to understand what's going on where.
  I had to learn a bit of bootstrap this week. I have never used bootstrap before so it took me a while to figure out what all the abreviations meant. Like every other project I've worked in the last few months, I've had to read a lot of documentation. I spent part of my time solo reading up on how bootstrap works and what you need to do to format things a certain way.
  Working as a developer a lot of your work will eventually get overwritten. For my work, it was overwritten the first day my teammates came back to work on Tuesday. All my hard work, gone in a single merge. I kid, I understand that so much work gets refactored.


Github Handle: [ceejaay](https://github.com/ceejaay)

###Tasks Pulled 

##### Front End
  [Styling the email creation/editing page](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/59)
  [Emotion list](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/61)
  [Format the version buttons](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/62)
  [Bug fix on state in the app ](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/58)

##### Back End
  [Bug fix in the API response](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/60)


Of all of these pull requests, the one we'll discuss today is this one:

  The most interesting thing I worked on was the crunching of the Watson tone score. The IBM Watson API sends back a score for every sentence you send it. That score has a name, and a numerical score. The name is like 'angry' or 'joyful'. The score is a number. 0.5908, for example. This score requires interpretation. 0.5 doesn't mean the tone is %50 angry. The Watson score is a scale from about 0.5, which is just barely registering on the emotion scale, to 0.75. Which is 'Strong likelihood of emotion.' So we can't just convert the number to a percent and call it a day. 
  The scale is about 25 points. With 50 being low, and 75 being high. So the formula we have to use is this: We get the number from Watson. Then we strip out the decimals. We do that by multiplying by 100. Then we divide that number by 75. Which is the top number. The result is a percentage we can use to interpret the score.
  I found this pretty interesting to work out. Now, I'm not sure if Watson is supposed to be interpreted this way. But I think it will work for our purposes. Overall the formula is pretty simple. But it took me a while to get there. I went through several versions of work before I arrived at the percentage formula. At first, I thought we'd do a range of points. Setting up a switch block and having a variety of cases to return a number in which to interpret. It's best to keep things simple. So I was able to work out the percentage. 

###Development Journal Entry.

The thing that I learned putting together a large project like this is communication. I feel like I could have been more involed in the communication process on this app. When I started this week, I felt like there were things I could have done by myself. And there were, but that stuff was overwritten pretty quickly when the team came back to work on Tuesday. At this stage of the process, we had a lot of decisions to make. It really was a bad idea for me to work in too much isolation from the group. There are advantages to working in a remote team. But the tradeoff it you have to really communicate more than you think you need to.


