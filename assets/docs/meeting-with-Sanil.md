

SANIL NAMBIAR
46 minutes 50 seconds46:50
SANIL NAMBIAR 46 minutes 50 seconds
like an external chat op system, right? And...
SANIL NAMBIAR 46 minutes 57 seconds
It's like Mission Control where you sit headless with the system, right? And you can interact with that with INI as well from here. I think you can ask questions also if I'm not mistaken.
SANIL NAMBIAR 47 minutes 12 seconds
Like this state.
SANIL NAMBIAR 47 minutes 16 seconds
OK, sorry, device so INIBTPRTR.
SANIL NAMBIAR 47 minutes 22 seconds
Edge one.
SANIL NAMBIAR 47 minutes 25 seconds
So, you can, so it gives you answers from INI directly, but the more interesting thing is whenever approval is required, it sends a, you know, request like this, which I can approve or reject. Okay, in this one in the other, I have another system.
SANIL NAMBIAR 47 minutes 44 seconds
You know, it's not accessible now, it's on a different VM. I had also implemented, you know, what you had shown that, you know, you have another sort of link here, you know, which says, you know, go to INI.
SANIL NAMBIAR 47 minutes 59 seconds
Okay, so because then the user can click there and it actually takes you to that investigation ID in INI. So that's also because the approval is here, the administrator wants to check in INI first, so they have the option of going to INI also. Now if they approve, then it is not that the, you know, the remediation is going to be executed immediately.
SANIL NAMBIAR 48 minutes 23 seconds
So, in that, in the in one of the demos that I had shown for setting the thresholds in Sev One, you can see the screen now.
JK
Jayakrishna Kaimal
48 minutes 33 seconds48:33
Jayakrishna Kaimal 48 minutes 33 seconds
Yeah.

Divine Antony
48 minutes 33 seconds48:33
Divine Antony 48 minutes 33 seconds
Yes, an Alias.

SANIL NAMBIAR
48 minutes 34 seconds48:34
SANIL NAMBIAR 48 minutes 34 seconds
So here you see that the recommendation has been done. Let me show you that. So the recommendation has been done here, right? So let's see.
SANIL NAMBIAR 48 minutes 54 seconds
Yeah, so here.
SANIL NAMBIAR 48 minutes 58 seconds
The system is telling you that.
SANIL NAMBIAR 49 minutes 1 second
There is a lot of noise in the system and it is asking you to.
SANIL NAMBIAR 49 minutes 6 seconds
Set a new threshold. That's the recommendation. OK, the threshold recommendation is has also been given right here, and so what is going to happen here is that...
SANIL NAMBIAR 49 minutes 18 seconds
I'm going to ask it to set it, right? So I'm going to ask it to set it, right? Okay, you know, use the seven threshold change tool to set it. So as soon as I do that, I get an approval to set it, right? So the user has looked at the recommendation and I'm showing you what the current, you know, setup is. It's only 20 megabits.
SANIL NAMBIAR 49 minutes 39 seconds
what the recommendation is to set it to 60, right, to set it to 60. So if you see here, the recommendation is to actually set it to 61 Mbps. The current recommendation is only 20, so that's what I'm showing you. The current one is only 20 in the threshold policy in SEV1, right? So, and so the next screen that I show.
SANIL NAMBIAR 49 minutes 58 seconds
is actually matter most because as soon as the prompt was sent.
SANIL NAMBIAR 50 minutes 4 seconds
Yeah, so that is 20 MBPS, that's the current one. So this is matter mode. So approval request was sent here, right? So demo 3 use case approval, it is sent here. So if I scroll down all the way, you will see that 7 threshold change, policy 67.
SANIL NAMBIAR 50 minutes 19 seconds
You see, that has already created a change request.
SANIL NAMBIAR 50 minutes 24 seconds
And it is asking the approval to set the policy from 20 megabits to 61 megabits. Okay. And I will approve this change. As soon as I approve this change, a few things happen in the workflow. So you will notice that. So approve.
SANIL NAMBIAR 50 minutes 49 seconds
because you can't like implement the change immediately. You have to set the maintenance window at a future time. But you know, and here I'm showing the flow itself. This could be slightly different depending on the maintenance systems, et cetera. But here it see that, you know, the, I have now planned a maintenance window in future.
SANIL NAMBIAR 51 minutes 9 seconds
In order to implement this change, links the newly created change ticket to that maintenance window.
SANIL NAMBIAR 51 minutes 18 seconds
Right, so if you see the maintenance window, it says, okay, the maintenance window is start time, end time. What actions you can take during the maintenance window when I change this policy, there might be too many alarms or less alarms. You can suppress those alarms, et cetera, that you can, you know, configure here. The user can configure that and then save it.
SANIL NAMBIAR 51 minutes 36 seconds
And once you save it, you know, it has been implemented. So it has been implemented, you know, during that time, right? I'm just showing the demo immediately to set the maintenance window. That might not be the case. The maintenance window might be next week, right? But in the demo I showed you immediately in 10 minutes, you know, just for the sake of the demo. So.
SANIL NAMBIAR 51 minutes 56 seconds
Now I'm showing that the policy has now changed to 61 megabits automatically. Now the changes happened. So if you go to the change request, so the incident request linked in, the initial investigation done by INI, when these thresholds were breached, the incident ID was this one.
SANIL NAMBIAR 52 minutes 17 seconds
After the recommendation was done, I and I created a change request because you cannot change something just because somebody approved without a change request. The change request was created and the approval was sent. Once it was approved, the change request was linked to the maintenance window. That's the change request that you see here. So if I go to this...
SANIL NAMBIAR 52 minutes 37 seconds
incident, you will see the initial original incident, everything is here. And if you scroll down, ILI has already linked this incident to the change request here. So if you go to the change request, you will see that the change request has all the details of the change. So you will see that this is a change request.
SANIL NAMBIAR 52 minutes 57 seconds
And you will see what is the justification, what is the implementation plan, when is the maintenance window to be set, what is the risk and impact analysis, and what is the backward plan. This is how things work in production. So just because somebody approves does not mean that immediately the agent will implement something.
SANIL NAMBIAR 53 minutes 16 seconds
There is a further process, and this is the process that I'm showing. The further processes, change request, look for the right maintenance window upcoming in the next week. Depending on the priority, you implement the change, you know, queue it for that maintenance window. Overnight, in the night, the 1 A.m. when everybody's sleeping, the maintenance window starts.
SANIL NAMBIAR 53 minutes 35 seconds
The night shift will implement this change till morning, they will test and, you know, verify and, you know, change. And if there is a backup required, we roll back the change, all of those things. By the time people come in the morning, everything is set. So that's the process, right, that I was trying to tell you earlier.

Divine Antony
53 minutes 55 seconds53:55
Divine Antony 53 minutes 55 seconds
Thanks, Anil, for sharing this. So now we have the clear picture of how things are happening in different channels when you approach a certain action item, yes.
Divine Antony 55 minutes 10 seconds
Yeah.

SANIL NAMBIAR
55 minutes 14 seconds55:14
SANIL NAMBIAR 55 minutes 14 seconds
They were a Slack native product, which means to say that.
SANIL NAMBIAR 55 minutes 18 seconds
They had a model as an I would say a natural language to SQL, you know, model where.
SANIL NAMBIAR 55 minutes 27 seconds
Everything in their system is Slack native, which means you don't need to go to the UI. You can do pretty much everything in Slack in natural language. That prompt, I mean, it was not even, you know, generative AI at that time. It was pure NL to SQL, you know, you know, changes. Like you ask something, hey, get me this particular report.
SANIL NAMBIAR 55 minutes 49 seconds
that natural language will translate itself to SQL, it will implement that, and then it'll come back, you know, with a graph for you, you know, in Slack, right? So it was pretty cool. So they were already, you know, thinking about headless at that time, is what I would say.
SANIL NAMBIAR 56 minutes 7 seconds
I think I have a really nice demo of that, you know, also somewhere. I don't know whether I have it here. But yeah, they're an interesting company. They were, so now they've added all their, what do you say, they've added more.
SANIL NAMBIAR 56 minutes 26 seconds
You know, AI now, so they are even more slack native and headless.

Drron Sharma
56 minutes 32 seconds56:32
Drron Sharma 56 minutes 32 seconds
Right, selector was one of the first products we considered when we were getting onboarded and that entire process was sort of radically different from how we were tackling things, right? A lot of it, as you said, was on this.

Divine Antony
56 minutes 32 seconds56:32
Divine Antony 56 minutes 32 seconds
No.

SANIL NAMBIAR
56 minutes 42 seconds56:42
SANIL NAMBIAR 56 minutes 42 seconds
Yeah.
SANIL NAMBIAR 56 minutes 46 seconds
So here, you know, yeah, exactly. So if you see, you know, this is their product. It's very, I mean, from a design point of view, it's like very in your face, et cetera. But you know, their Slack native thing starts here. So if you see here, right, they log into their Slack, they launch Slack.
SANIL NAMBIAR 57 minutes 6 seconds
that's a selector as an application there. And so, you know, this Slack, this is how it looks, right? So this is the customer channel. Everything comes here, you know, in their environment. So you can ask for details, like, you know, alerts. It automatically posts there, right? So you can do a select.
SANIL NAMBIAR 57 minutes 26 seconds
query, you know, you can do a lot of, you know, stuff here. Like, for example, see this, it's multimodal, obviously. So it asks for something, it gives you that, and then you can click on that, and you can then go to that site. You know, you can ask for details about latency, and it'll show you that specific, you know, this one. This is how it was, like, I'm talking about, like,
SANIL NAMBIAR 57 minutes 47 seconds
You know, this is an old video, but yeah, I mean, this is how they were right, then you never need to go to this one, you know, you can do everything, you know, from the from the Slack native interface itself. It's pretty cool at that time.
SANIL NAMBIAR 58 minutes 2 seconds
Sure.

Divine Antony
58 minutes 4 seconds58:04
Divine Antony 58 minutes 4 seconds
So, thanks, Hani.
Divine Antony 58 minutes 7 seconds
So yeah, so I think that's pretty much from our side. Drron, Jacob, do you want to add anything here?
Divine Antony 58 minutes 15 seconds
Good.
JK
Jayakrishna Kaimal
58 minutes 17 seconds58:17
Jayakrishna Kaimal 58 minutes 17 seconds
Yeah, we we are good. Excellent. Thanks for your time. Thanks for your feedback.

Divine Antony
58 minutes 17 seconds58:17
Divine Antony 58 minutes 17 seconds
OK, so yeah.
Divine Antony 58 minutes 20 seconds
Yeah.
Divine Antony 58 minutes 23 seconds
Thanks, Hani, for joining.

SANIL NAMBIAR
58 minutes 23 seconds58:23
SANIL NAMBIAR 58 minutes 23 seconds
Yeah, great. Yeah, sorry I had to, I didn't know about your holidays, so you know, enjoy your holidays. Bye. Long weekend. Thank you.

Divine Antony
58 minutes 29 seconds58:29
Divine Antony 58 minutes 29 seconds
No, it is. No, it is.
JK
Jayakrishna Kaimal
58 minutes 33 seconds58:33
Jayakrishna Kaimal 58 minutes 33 seconds
Thank you. Thank you.

SANIL NAMBIAR
58 minutes 33 seconds58:33
SANIL NAMBIAR 58 minutes 33 seconds
Thank you, guys. Cheers. Bye.

Divine Antony
58 minutes 34 seconds58:34
Divine Antony 58 minutes 34 seconds
Thank you. Thank you. Bye.

Jayakrishna Kaimal stopped transcription