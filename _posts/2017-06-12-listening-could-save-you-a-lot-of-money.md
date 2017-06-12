---
layout: post
title: "Listening could save you a lot of money"
comments: true
description: "In this post I talk about why you should speak up and why if you are on a higher position
you should listen to your juniors."
keywords: "leadeing, manager, communication"
--- 

Communication is something that most people do not understand. Some
think that more is always better, ignoring the quality. Others think
that small opinions are not worth saying and small decisions are nor
worth sharing, because they are so small no one will care, and most
people think that the job title of the person talking is more
important than what he/she is actually saying.

In this article I'm going to talk about 2 real life situations, that
show the importance communicating. I'm going to use the following job
titles as characters with a reference salary.

- VP: 500$ per hour.
- Manager: 200$ per hour.
- Leader: 175$ per hour.
- Senior: 150$ per hour.
- Junior: 100$ per hour.

So that gives us a base.

## Taking decisions alone

Sometimes changes need to be added on the go, and while for some
people they can be simple and small, they can cause issues in other
parts of the project. This happened to me at least twice with
different teams. The the team in charge of doing the business logic
(backend) noticed that they will need a new field in the near future
for them to be able to accomplish a task, and, since they were working
on a similar issue, they added it, which took them half an hour.

The day after this change was published, the test team noticed that
some pages were not working properly in the user interface (UI). So
they proceed to raise the issue, this whole process took them, at
least 1 hour. Then, the UI team started searching for what was causing
the issue. When they found out, half an hour later, that the issue was
being caused by the backend, they notified the test team. Then a
meeting was called with all the teams in the project (UI, backend and
the manager) to discuss what the issue was (each team is composed of 1
leader, 1 senior and 3 developers), the meeting took half an hour, and
in it they concluded that the change needed to be done, and the UI
team needed to make the required validations, since it was a small
change it only took half an hour to add the extra validation and
another half an hour for the test team to make sure everything was
working properly.

All of this had a cost of:
- Test team: 1.5h (junior) = $150
- UI team:
- 0.5h to find the issue (senior) = $75
- 0.5 * whole team = $262
- 0.5h to fix the issue (junior) = $50
- Backend:
- 0.5h to add the functionality (junior) = $50
- 0.5h whole team = $262
- Management: 0.5h = $100

So the cost of this was $950. If the back end team had notified the UI
team, this could have costed 100$. Most people don't think about how
much their time costs the company, where does the money actually come
from, and how that DOES affect them individually.

## Ignoring the underdogs

At the beginning of my career I was working at a big company, so they
had several leaders, managers and VP's, and one of the things that
most big companies have in common is that they tend to ignore people
in the lower levels.

I was working as a full stack developer and I discovered that they
were doing some very bad things (they were doing queries directly from
Hibernate to the database, and using select * between at least 5 huge
tables while using outer joins. Some queries were taking more than a
minute to run and blocking the database in other cases) so I asked my
direct leader why they were they doing that, his response was that
that's the way things were done there and I should be doing the same.

So I sent an email to my leader's manager, explaining all the issue
that we could have in the future if we keep doing that. He told me
that he knew that, and that I shouldn't be worrying about that and
just "keep up the good work!". That answer left a bad taste in my
mouth... so I decided to send an email to the VP of technology and
explained all the repercussions this actions will do (no
exaggerations,  was pretty sure of the size of the issue)... 3 days
later he called me to his office, he took half an hour to tell me
exactly what my manager told me... so without hope I went back to my
desk, forgot the issue, and just kept doing my best.

A little over 2 months passed and one day we were called for a meeting
in the company auditory. A meeting with all the developers, leaders,
managers and the VP of Technology, 150 people. For more than an hour
the VP told us that the client looked for an expert (a DBA) to look
why he was having so many issues with his databases, and he discovered
that someone (us) was doing some extremely bad things. So he told us
that we were doing a really bad job, that how on earth did we thought
on doing that and for the next month everybody should focus on
changing that... I was between happy and frustrated with his
statement...

So I'm going to ignore all the time not stated in this article, like
meeting with the client and meetings between managers (which I know
happened). This all costed at least the following:

- VP: 1.5h. $750
- 10 Managers. 1h each = $2000
- 20 Leaders. 1h each = $3500
- 20 Seniors. 1h each = $3000
- 100 Juniors. 1h each = $10.000
- **Total: $19.250**

Just in meetings the company wasted $19.250. Which they could have
saved if they paid attention to the new guy saying something is wrong.
And like me, I'm sure there were other guys saying similar things, and
also being ignored... just for the problem to be raised later by an
expert (or worst case scenario: The client).

## Conclusion

So never ignore people and their attempts to communicate, they might
have a valuable input that saves everyone a lot of money. Don't think
that because someone is at a lower position, that person is less than
you, or even knows less than you, less experience doesn't necessarily
means less knowledge. Always try to communicate everything in a clear,
concise and straight to the point way, this will let everybody know
what is going and how to react. Remember that time is money, and, at
work, is not **your** money, is the company's money. Everybody enjoys
a nice bonus or a fun christmas party right?