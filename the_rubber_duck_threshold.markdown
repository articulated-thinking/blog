# The Rubber Duck Threshold
Advice to testing specialists
about pairing with software engineers
on production programming tasks

I work for Pivotal. One of Pivotal's _things_ is pairing a lot. Pair Programming is part of that whole eXtreme Programming business, and Pivotal's development practices have their roots in XP. So I showed up on my first product team at Pivotal and essentially said "hi! I'm a tester!" and they weren't totally sure how to pair with me. So I said "I do charters! You can pair with me on those!" And that worked really well and I highly recommend it and _that_ is a different post.

This post is about pairing with programmers on what they usually pair on: writing code. One mistake I made, starting out at Pivotal, was thinking I couldn't be of value on a pair writing production code. This is something I hear a lot when talking with testers about pairing - sometimes explicitly, in sentiments like "oh, but I don't know how to code," and sometimes implicitly. One example of the implicit case was someone who told me that she had been trying to get her devs into the idea of pairing with her for testing purposes, and they said they wanted to get her to pair with them for programming purposes - and she regarded this as sort of a rebuttal or implausibility, something that needed addressing; she didn't think she'd have anything to add, though she had a clear model of how developers might add to the value of testing.

So let me tell you a story. Say you've got some developers who pair all the time, and it's "engineering nirvana" (this is a _real thing_ that an _actual person_ has said to me when describing the feeling of being part of an effective pair all day). They get to externalize internal abstract thinking along social channels. They're used to verbally explicating their ideas, being forced to clearly communicate what they're thinking. And then, one day, they're working on a personal project, or someone calls in sick, and they are pairless. So they call the expert for these situations:

![Your Competition][duck-image]

They set the duck next to them, they look at it in its weird, sarcastic duck eyes, and they verbally explicate their ideas to it.

So you can picture a programmer talking to a duck, right? She's got her fancy keyboard and her pour-over coffee made just so and her properly configured text editor of choice and she's explaining to a bath toy that "logic doesn't belong in the repo layer." On purpose. Because it helps her. So, can you help that engineer, can _you_ help _her_, more than that duck does?

The bar is not as low as it may at first appear. The duck:

- does not interrupt
- does not ask distracting questions
- does not drift or display inattention
- does not instigate pop-culture riffs/digressions
- does not flog its own ideas
- does not need its hand held
- does not need its feelings/value validated
- is not having a career crisis
- is not having an existential crisis

Intimidating, right? But the duck has important shortcomings and flaws, and its important to remember that while you might not have all these advantages down pat, neither do many programmers, and we manage to make up for it by beating the duck in other dimensions, despite our own shortcomings and flaws. So I have some advice about how you might do that.

The principal non-programming value a pair can provide is in listening well, asking high-quality questions, providing social engagement for abstract ideas, and managing the focus of the pair. This is all at least somewhat independent of being good at syntax, algorithms and implementation patterns, which we can touch on in a bit.

### Humble Questions
Ask humble questions and be up-front about _actually not knowing_, asking from a desire to learn. You might ask why a piece of of the system is designed a particular way, or why a particular approach is more efficient, or any other conversational question that might come up when an engineer is discussing how a system currently works and what they intend to do about it. When you ask such a question, there is a real possibility of it being taken as a rhetorical point. I've said things like "why are we passing a user as an argument here, but getting the user from the framework, here?" and gotten back "ooh, good point." I was not making a point. I was confused about where the "user" object the code was operating with came from. Noticing your confusion and distilling it into a good question is a vital pairing skill. And asking questions when you think there is a correct way, or when you think a pattern has been violated, is also very useful. But you do not want a question from ignorance to be mistaken for a question from disagreement, lest you find your pair suddenly defensive.

Of course, in asking that question, I beat the duck. We refactored the code and made it better. But I wanted to clarify that I was asking because I was confused, and I have since learned to stick something like "I'm probably just missing something, but..." or "I'm just asking so I can get a handle on this pattern" on the front of such questions. The reason I find this important is that it emphasizes the value of competently handled ignorance; not knowing something _out loud_ can be of value in pair programming. Not knowing something _silently_, on the other hand, does cut down on questions and interruptions. But it can also interfere with learning and the improvement of the code.

Explaining things is often part of how people come to understand things better. Giving your pair useful opportunities to articulate system principles and design patterns they otherwise might not've thought about (or to admit that some areas of the code use inconsistent patterns) is valuable.

### Driving and Navigating
When we pair at Pivotal, we talk about "driving" and "navigating." The person typing at any given moment is driving. The other person can navigate. Negotiating who drives and for how long is an important pairing skill. I should note that this isn't the only model of pairing interactions - sometimes someone is both driving and navigating, and their pair is watching for problems or there to listen, or waiting to propose an alternative. So don't think that you have to be driving or navigating to be a good pair. Still, even if you don't know how to code, you may still find it worthwhile to explicitly drive or navigate. And of course, the duck can't do either.

This isn't for everyone, but you can suggest to your pair that they tell you what to type. This is easier to the extent that you've got some grasp on syntax. For instance, I was doing this once and my pair asked me to "just chain that method on there." I had to explain to them that I was _very sorry and was a terrible engineer and all but, given that we knew that going in, pretty please what is this "chain" you speak of?_ In context, it meant "type a period, immediately followed by the method name." But my pair didn't know to say that and I didn't know how to type what they did say, so we had a very educational conversation in addition to getting the code written.

It can be painful to offer to do something which you are excruciatingly bad at _for_ someone who is excruciatingly good at it. "Why would she want me to type for her, she's one of the best typists I've ever seen, and I don't even know which type of bracket she's talking about!" you might think. I have personally found this another case where the stance of humility I described before is helpful. This is another case where slowing down the process can actually be helpful, where forcing the slow and clumsy social articulation of code can help.

But it also might not! Don't be afraid to check in and make sure its working - even in pairs with much more programming parity than I'm assuming here, trading off driving and navigating regularly is important. And if you don't realize value in driving, or if you don't want to be in the painful situation of having a lot of light shown on one of your relative skill disparities, you can navigate.

Navigating means describing what the code should do, more or less. If you drive in the way I just described, your pair telling you what to type is a form of navigation. You probably won't want to tell your pair exactly what to write, though if you find you do, that's fine. More likely, after listening to your pair describe things for a time, you will be able to use similar language to describe problems and solutions. This might end up sounding a little like this, depending on how many of the terms you know:

> You: So we, um, get a list of all the things passed in, right?
> Pair: Yeah.
> You: We should go through each thing in the list and check to see if they have a date, and if they do, put the date in a new thing.
> Pair: <silent typing>
> You: yeah, but, if they don't, we still need to know that, so, we put in an empty entry or something.
> Pair: <mousing at the screen> Okay, so, we've got a map iterator, and the new array is the same length as the old, but only has the date, or, if there isn't a date, a nil.
> You: Will a nil be okay later, if we want to display something like "No date recorded?"
> Pair: yeah, we can do something later, a decorator or presenter or whatever, but we just wanted this method to get the dates, not get them ready to show to a user, right?
> You: Right.

This conversation could go on for a while, and you might or might not decide that nil is right for you, contextually. And maybe you don't know if you should be using `map` or `each` or whatever. Don't worry about it, though if you notice `map` in some places and `each` in others, you might learn something pretty interesting if you ask why that is, especially if you don't understand the distinction.

If you don't feel equipped to undertake this sort of conversation, again, you can be a very light pair, mostly listening and occasionally asking a question. I would caution, though, that not driving or navigating for an extended period makes it easy to become disengaged and drift, and that is not beating the duck. Your inattention can damage your pairs productivity and happiness. If you find yourself drifting, and you still want to be pairing, try suggesting you take a turn explicitly in the driver or navigator seat.

### Reading Code
There is a bare minimum set of code familiarity necessary to take advantage of the advice in this section. It is optional. You can sit down and be a useful pair without prep or code knowledge. You will, however, likely be an even more useful pair if you know even a teensy bit about syntax, design patterns and the language you're working in. You can learn these things in advance, or you can make them an informational objective of your pairing experience. 

Some very basics are:
- Using the names of things. Are there variables and/or constants? What does their declaration syntax look like? What does it look like when they are referenced? How are arguments named and referenced?
- What are discrete pieces of logic called and what do they look like? Functions? Methods? Sub-routines? Something else? (You may or may not have to learn about lambdas, anonymous functions, blocks, etc. Each language is different, though they are also much the same, once you get to know them.)
- Recognizing when something is inside of something else. Where do desecrate pieces of logic begin and end? Iterator loops? Classes (if any)? Other things?

This list is also valuable in setting expectations with your pair about your relationship with programming, so you might consider telling them what you feel you can and can't do. It's alright to come to this with plenty of ignorance in hand, as long as you manage your ignorance well.

Beyond the basics, there are many orthodoxies available out there, and if your pair is an adherent to one of another of them, you might consider reading its sacred texts or watching its revered conference talks. Perhaps your pair is part of the software craftsmanship movement - and if they're pairing, this is more likely to be the case. Perhaps they believe in "Clean Code" or feel that "the dependency inversion principle" is crucial. These phrases have whole systems of thought and practice behind them, articulated as heuristics with names like "design patterns" and "code smells."

I was tempted to provide reading suggestions or video links, here. I may yet do a follow-up and add them. But I think the better advice is to ask your pair - or if you want to do this before you try pairing, your prospective pair - ask them what they go by. I mean, I'm going to go ahead and mention _The Pragmatic Programmer_ and _Clean Code_ as reading suggestions, but I hesitate to recommend using them as a pairing resource unless your pair suggests them. This is because unless your pair _already knows_ about "dependency injection" or whatever when you bring it up, you risk putting yourself in the position of having a claimed preference about implementation without having the skill necessary to carry it through. If your pair already has the knowledge and the preference, discussing where a pattern should or shouldn't be applied is likely to be a nice experience, and may well lead to them better practicing their own ideals than they would have without you. If they don't, though, you might prefer not to be the one telling them about it from the bottom of a substantial programming skill differential.

By all means, look up "code smells" and use them to drive humble questions. The questions are more likely to be useful to the extent that you align your learning resources with your pair's school of thought, at least initially.


### A Few Final Tips
- Pair Programming means shared inputs. Bring a keyboard and mouse and plug them in. Wired hardware can make this simpler. Working on separate computers next to each other is probably not pairing. Ideally, you'll have a mirrored display setup, but you can both look at the same screen, too.
- If you do have mirrored displays, try to avoid pointing with your fingers. Point with the mouse, so that your pair can look at the screen they don't have to sit at a weird angle to see. Also, some people get really sensitive about people poking at their displays, so I would generally advise you avoid touching the screen.
- Conversely, if you pair, someone may point and touch your screen. It's okay to tell them you prefer they not touch the screen, or remind them to point with the mouse.
- People sometimes hand things to each other as a way of negotiating keyboard control. That is, you might hold a hand exerciser or a ball or whatever off so that you don't try and type at the same time. Think of it as a mutex for input. Legos, knotted cord, river stones; all can work.
- Help your pair (and yourself!) by reminding them it might be time to take a walk, play ping pong, or have some water. You can also use pomodoros for this, if you're both the sort of people who forget these things.

Go forth, find programmers, and pair with them.

## Points of Articulation
- Incidentally, XP has been and continues to be a silly name for a seriously useful movement.
- I have assumed throughout this post a zero-to-beginner range of programming/language familiarity on your part, and mid-to-high level capabilities in your pair. Some of these pieces of advice remain just as valid when not navigating that kind of skill differential, but others are pretty specific to this set of assumptions. I don't think it is terribly hard to imagine which are which, but it seemed a worthwhile caveat.
- In both of the disclaimer examples I gave under the **Humble Questions** heading, I used the word "just." That word is lullaby language, but in this case that is its intended effect, setting the listener at ease.
- Reviewing this post reminded me of Ann Leckie's [_Ancillary Justice_][ancillary-justice]. This is as good a time as any to reflect on how much I love good stories about spaceships, artificial intelligence, soldiers, and war. Fun game: why did reading this post remind me of that book? I don't think I've said enough about the book here for people to win that game without having actually read it, though.
- I am pretty sure that was this blog's first book review, so now the assertions on the [About Us][about-us] pages are _less_ packed with lies.

[duck-image]: duck-url "Your competition."
[about-us]: http://articulated-thinking.com/about/about-you/ "Yes, I did choose that phrasing to mitigate another lie."
[ancillary-justice]: http://amzn.com/031624662X
