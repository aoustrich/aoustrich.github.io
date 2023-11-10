---
layout: post
title: 3 Life Lessons from the Creator of Numpy and Scipy
date: 2023-10-30 15:53:00-0400
description: Life Lessons from Travis Oliphant
categories: learnings
tags: links
giscus_comments: true
related_posts: true
thumbnail: assets/img/learning.jpg
---
<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/networkGraph.jpg" title="Learning from Data Science" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Earlier this month, BYU’s <a href="https://acme.byu.edu/">ACME</a> program celebrated the 10 year anniversary of its creation. Part of the festivities included an hour long lecture by one of the most influential Data Scientists of all time: <a href="https://www.linkedin.com/in/teoliphant/">Travis Oliphant</a>. Oliphant is the main creator of the popular Python packages numpy and scipy, the co-founder of Anaconda, and CEO of both <a href="https://quansight.com/">Quantsight</a> and <a href="https://www.openteams.com/">OpenTeams</a> (he’s also a former BYU Professor). 

He told us why he wrote these packages and started these companies to inspire us to go do our part to make the world a better place. I expected to learn a lot about python and data science from this lecture (and I definitely did), but I never thought I’d learn so much about life.

## Life Lesson 1: Communication is Critical
This might not be the most ground-breaking principle, but the stories Oliphant shared gave me a new perspective. 

Everyone in the room seemed to chuckle in agreement when he said “Debugging is twice as hard as writing code,” maybe because as students it was nice to hear such an accomplished professional admit to having trouble writing code sometimes. He told us that it took him 4 months to write numpy and 14 months to “fix it.” (Maybe debugging is 3.5x as hard as writing?) 

With all the projects he’s worked on whether they’ve been academic, open-source, or professional over the last 25+ years of his career, Travis Oliphant has had his fair share of complications caused by misunderstandings and poorly communicated expectations. 

Who hasn’t?

Writing code is a precise endeavor. Just the other day the python script I wrote to automate some processes at work through a few api calls worked perfectly on my own laptop, but created errors when I ran the code online. After frantically comparing my code to the documentation I realized I was passing a string as an argument instead of a list of strings. 

It made me wonder how often I think I’m being explicit with my words locally but my meaning is not properly conveyed globally. Whether it’s understanding project specifications or agreeing on the optimal order of steps to take, it’s easy for true meaning to get lost in our attempts to explain what we want or understand what others want. 

It’s at least twice as hard to “debug” what we say or hear than it is to speak or understand effectively. Communication is more than just saying words. 

> ##### Key Takeaway
>
> Speak simply and clearly so others understand what you mean. 
> Listen simply and clearly so you understand what others mean.
{: .block-tip }

-------

## Life Lesson 2: Innovation Comes Unexpectedly

Despite being open source projects with dozens of contributors actively working on numpy and scipy, they had trouble getting widespread use of the packages. Experienced software developers and university professors could write the code, but didn’t know how to handle the "<a href="https://a16z.com/books/the-cold-start-problem/">Cold Start Problem</a>.” 

Almost randomly, Oliphant came across a windows installer for scipy that made the distribution of these packages much easier. This innovation eventually lead him to co-found one of the most popular Python and R distributions: <a href="https://www.anaconda.com/">Anaconda</a>. 

Wanna know the best part? The windows installer that *actually* changed the way we code today was written by a kid in high school.

This wasn’t the only student that unexpectedly shaped the future of data science. During the creation of scipy and numpy, Travis Oliphant planned a brand new BYU class on processing medical scans and images. (Un)fortunately, though, the one student who registered later dropped the class and left a big hole in Oliphant’s schedule which was promptly filled with open source projects. 

This happened to be right around the time Oliphant was being evaluated for tenure which was eventually denied because he was more focused on building numpy and scipy than his other projects at the university. 

If the new class he created wasn’t a “failure” and he had “succeeded” by earning his tenure, we may have never gotten numpy or scipy.

> ##### Key Takeaway
>
> Be meek and ready to learn from all people and all circumstances. 
> Success and Failure are often matters of perspective.
{: .block-tip }

-------

## Life Lesson 3: “Earnestly Try to Do Good”

One of the more unorthodox invitations Travis Oliphant gave us was to become interested in things other than math and coding. My initial reaction to this was something along the lines of “But shouldn’t I be focused on developing my math and coding skills if I want to be a Data Scientist?” 

But as he explained how his interests in music, economics, and business gave him creative breaks from working on python packages, I realized how much I’ve enjoyed some of my general education and elective classes at BYU (“<a href="https://catalog.byu.edu/courses/01567-001">Economic Principles and Problems</a>” and “Beginning Bowling” are some of my favorites).

Travis Oliphant never planned to be a pioneering data scientist or python developer. His interests in Electrical Engineering and medical imaging led him to numpy and scipy. 

Having worked open source projects for decades, his admonition to contribute was inspirational and sums up my intentions with this site. 

<blockquote>
One of the best ways you can contribute to open source projects is by writing about what you learn.
</blockquote>

> ##### Key Takeaway
>
> “Dont sit around waiting for someone to solve something. Do it.”
{: .block-tip }

-------

## Conclusion

By prioritizing effective communication, embracing unforeseen innovation, and doing our best to "do good," we pave the way for a more responsible and impactful data-driven future.

This was a great lecture and I'm so glad to be part of a community of Leaders and Learners. 

One of the best things about researching for this post was that I found Quantsight’s <a href="https://quansight.com/about-us/#:~:text=DIRECTOR%0AQUANSIGHT%20LABS-,Our%20Values,-DO%2DERS">values</a> and realized that not only does Travis Oliphant live those values, but he invited us to do the same.