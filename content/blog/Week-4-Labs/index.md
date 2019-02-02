---
title: Week Four of Labs
date: '2019-02-01T22:40:32.169Z'
---

###Individual Accomplishments
[Sort Top Scores Whiteboard Practice Video](https://www.youtube.com/watch?v=r8pwHPfYmeM&feature=youtu.be)


##### Our Team's graph.
![Team Graph](team_graph.png)

This week I was out of the loop a bit. I missed a meeting where the team went over every part of the app to decided what needed to be done. That wasn't a great meeting to miss. I had some family responsibilities, that's why I missed it. I learned this week it's hard to try to split your time between responsibilities. I tried to do both, but only one got my attention. I had chose to focus on my family responsibilities. Which isn't bad, but I really need to do well on my work here at Lambda School so I can be a better contributor to my family in the future.

I did get some modest participation in. I will have to spend some of the weekend catching up.

Github Handle: [ceejaay](https://github.com/ceejaay)

###Tasks Pulled 

##### Front End
[Fixed some punctuation.](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/147)
[Reduced size of hamburger icon](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/154)
[Fixed overlap of greeting text and hamburger icon](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/155)

##### Back End
[fixed a bug that showed duplicate docs on the page](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/132)

Note: the following are the same PR. We fixed two bugs in one PR.

[Fixed the bug that was caused by the above PR](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/142)

[Solved the app-breaking problem of clicking on a duplicate document](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/142)


Of all of these pull requests, the one we'll discuss today is this one:
[fixed a bug that showed duplicate docs on the page](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/132) and  [Fixed the bug that was caused by the above PR](https://github.com/Lambda-School-Labs/dont-send-that-email/pull/142)

We were faced with a problem. When you saved a version of the email you were working on, it would list another copy of that document in your documents list view. This turned out to be a SQL query problem. The query would look for the email message. Then it would check for all the versions. Then it would return all the versions and it's original email. Our front-end app would render every item in the array returned from the database. I thought the fix was `groupBy` which is a knex function. That worked until we put it into production. In development we use sqlite. In production we use postgresql. Postgresql does not like the `groupBy` function.

The original solution:
![The original solution](original_solution.png)

So we had to fix it. I wasn't able to fix it by myself. I had to do some pair programming. My colleague Jared Cuffe, helped me out with it. Rather, I watched while he figured it out. First we used node to do some test sql queries. We ultimately didn't figure that out. Sql is hard. So we had to come up with another solution. We finally went through the array returned from the database and only picked the latest items in the array. So we would eliminate any version that was an older duplicate. 

Here's the code:
![the solution](the_solution.png)


###Development Journal Entry.
 So far, in my view, this stage of the project is hard. There are a lot of obscure bugs that require deep work to fix. This week, I worked with my teammate Jared Cuffe to fix two bugs. These were bugs that broke the look and feel of the site. As far as I know this is the kind of bug that crops up in the process of a project like this. You can't predict these kinds of problems. Or at least I can't. For me, these bugs were hard. I had to have help on them. At the beginning of this project we start coding in broad strokes. We rough in the backend. We rough in the front end. These things are fairly easy. It's the kind of thing that we spent weeks doing during the first parts of Lambda School. Now, we are learning things they didn't really teach us. For our team, we have to work together to move forward. There's a lot of collaboration on this stage. The bugs are harder. The front-end tweaks are more subtle. The technical problems are clear. On my pull request, it was clear that we had to remove duplicates. But it wasn't clear how to do that. So it required pair programming. We had to come up with a somewhat kludgy solution. But that's ok. The thing works. I think it will keep working. But there will be more obscure bugs that pop up that require refactoring and fixing. That will take the whole team.

