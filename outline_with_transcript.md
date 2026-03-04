---
marp: true
---

# Speech to Code

- Kae Sluder (they/them), Frontend Dev. 
- Ex-eLearning designer 
- Intern -> Contractor -> Fulltime
- React, Vue, JavaScript, vitest 

Okay, so I'm going to try something a little bit different here because I want to demo the technology that I'm talking about. 

And this is an experiment. I've rehearsed this several times in one of the phone rooms, but I haven't ever done this live. 

My name's Kae Sluder. I am a recently drafted front-end developer. I'm a new career developer. My background is in e-learning design. I switched to full-time software development about five years ago, and I have been loving it ever since. 

---

# Problem

- Broken hand
- Pain points: capitalization, symbols, punctuation 
- Eg: `for (let i = 0; i <= 30; i++) {Hammer.camelCase(i)}`
- Loss of speed and focus

So the big problem: I'm just going to raise my hand so everybody can see. I broke my hand just after I was asked to move here full-time in October, and one-handed typing has a number of pain points for a programmer. The big ones are:
- capitalization
- symbols
- punctuation
Here's an example of some fake JavaScript code showing hammer case and camel case, and probably the biggest one is the loss of speed and focus if I'm thinking about the keyboard. I'm not thinking about what I'm writing in any language.

--- 

# Speech Recognition

- "Mini AI"
- Talon: precise control, high customizability, low fluency 
- Wispr Flow: high fluency, low control 
- Consistent capitalization, symbols, and punctuation are still a problem 
- Models not trained on programming language

So there are a variety of technologies that I could have used to work around this. In the past, this is unfortunately not by first-hand injury, so I've leaned towards speech recognition. Currently, in 2026, there are kind of like two things for voice coding. Tail on Voice is a semi-open source speech engine. 

Talon is entirely programmable in Python, so it offers very high customization, but the downside of that is you have to do a lot of customization to get it working with your flow. 

A newer product, Wispr Flow, is what I'm using here. It is especially designed for dictating English text to be fed into an AI prompt, as well as email and other things that we have to communicate in. 

---

# English to Code

- Write in English
- AI translation to JavaScript/TypeScript


So after about a month and a half or so of trying to dictate JavaScript anyway, I started moving towards a spec-driven development, AI-supported system. The basic premise there is that you write your algorithms or you write your specifications in plain English, and then you use an AI agent to translate that into JavaScript or TypeScript or any other language that you're working in. 

---

# Low level: Pseudocode Algorithm Description

```text
// Pseudocode example one 
Loop for i from 1 to 30, including 30 
If i is evenly divisible by 15, print "fizzbuzz" 
Else If i is evenly divisible by 5. Print "buzz"
Else if i is evenly divisible by three, print fizz. 
Else print i 
Exit the loop. 
```

This is an example of a very low-level approach to this, which I've tried out and use now and then when I can't get the AI to go down to this level. This is pseudocode; other people might call this semi-literate programming, although that's a complicated term. You describe what you want for the computer to do in English, and then you ask the AI to translate it. This is an example which I dictated myself last week. It's very simple because I only wanted it to be on one screen.
 
---

# High-level: spec/behavior-based development 

1. Spec file
2. Plan file
3. Question & review cycle 
4. Execute plan
5. Review

See also: BMAD, github spec-kit




So now we're getting to the point where everybody is talking about these days: spec-driven development, behavior-based development. 

The basic idea is that you start with a spec file, which is a description of what you want the feature to do. You want to focus on just the what and the when, and not the how. Then you expand that into a plan file, which breaks the development of that down into specific steps. You work through both within a question and review cycle to refine what you're talking about, execute the plan, and then do review of the resulting code. 

---

# Spec File

Detailed description of what exactly you want for the AI to create. 

- Purpose 
- Behaviors ([gherkin](https://cucumber.io/docs/gherkin/))
- Layout
- Data structures
- Rules ("Use tailwind", "Check Makefile for test instructions") 
- Test Cases 
- Jira Ticket Descriptions


So a spec file is a detailed description of exactly what you want for the AI to create. Now, I said earlier to focus on just a what, and I'm going to immediately break that rule. Some of the things that I've experimented with, and there are a lot of frameworks that will give you very specifically formatted spec files for this. This has been like drinking from a fire hose lately. 

But some of the things that you want to put in a spec file are:
- The purpose: Why am I building this feature?
- I like using behavior descriptions. If the user clicks on the button, then you should do this.
- If I have layout hints for something that is visible on the screen, bring those forward.
- Data structures. If you need to work with a specific record, like a user from the Scienable database.
- Rules which define some constraints on what you want the AI to create.
- Test cases.
- If there's a Jira ticket for this, you can put in the Jira ticket descriptions.

---

# Behavior

When, given, then = Action, condition, result.

So this is where my educational background comes in handy. Behavior-driven specs are very:
1. They have to be observable.
2. What you want to do is describe the feature you're creating in terms of an action, condition, and result.

There have been a variety of ways to define this over the last hundred years or so that this has been used in education, and then this has been adapted or maybe reinvented within the software development world.

```text
When the user clicks on the Next button 
given that the user has filled in all required fields 
then the user advances to step two of the form 
```

This is a Gherkin language behavior description. When the user clicks on the next button, given that the user has filled in all of the required fields, then the user advances to step two of the form. 

```text
When the user enters more than 50 characters into the `First Name` field
Then the user sees an error message
```

---

# Plan Files

- Generated by Claude
- Translate specs into actionable steps
- Agent management (split into smaller tasks)

After the spec file is created, the next step is to let me do a quick time check. After the spec file is created, then you want it to create a plan file, which is a detailed, step-by-step instruction. Almost always I use the Claude plan mode to do this. It is very good at breaking down a complex feature set or complex development task into a series of steps that it can understand. Along the way, it will ask you questions about things that you haven't fully clarified in the spec file, and this is an important part of the process. 

---

# Document Driven Process

Spec and plan files are living documents. They can be revised and reviewed multiple times before code generation. 

- Can take a break
- Adversarial Reviews (reduce risks of fixation)
- Context Clearing
  - Ideal ~ 50% of context window
  - Avoid context poisoning
  - Reduce fixation

I want to emphasize that this is a document-driven process, and there has been kind of a debate going on between "the vibe coders who kind of pants it using the AI prompt window" and the spec-driven developers. 

And the document-driven process provides a number of advantages:
- You can take a break.
- You can go back, edit, and find the exact wording that you need for this, for the feature.
- You can ask your friend at the next desk, "Hey, can you read this? Do I have this right? Am I missing something?"

It is also helpful in terms of managing AI performance. There is some, and a lot of this is anecdotal wisdom, so AIs tend to perform better and hallucinate less when you keep the context down to about 50% of the max context size. That's sort of a conventional but unproven wisdom that's been flying around.

The other thing you want to avoid is context poisoning, which is a case where you say, "Hey, let's think about using this library A," and then you decide, "No, that's not going to work; let's switch to library B." The mentions of library A and the discussion of library A are going to stay in that memory until you clear it, and that can bias the results. Also, another problem you want to avoid is fixation, where the AI will do analysis and think, "Okay, I have absolutely found what the problem is here; it is this." Sometimes the AI is wrong, but getting the AI to shift away from this and focusing on that is easy. It is easier to just say, "Okay, I'm going to wipe your memory, and we'll just start this discussion all over again." 

What you can do with an AI, you can't do with people 

---

# Generate Code and Tests

- Tests are mandatory to confirm success/failure
- Code written to pass tests
- Tests provide critical information during the debugging process.

Tests are a mandatory part of the process because generative AI is developed for pattern matching. It will think through the problem as best it can, but it can't give you a definite yes, this is correct, no, it's not correct answer. At some point in your specs, you want to say, "Okay, here, this is a hard, this is a required requirement. This is the command you want to run in order to get this information." If the test doesn't pass, you need to go back through it and fix the code. 

---

# Human Review

- Sometimes it's wrong
- Usually can be better 
- Don't generate more than I can comfortably review 
- If I can't explain it, I need to learn it


So, human review is also an important part of the process. Sometimes the AI is wrong. Often, what the AI gives you could be better. There's the disclaimer: always double check what the AI gives you, and that is especially true before you commit to bringing code into your main codebase. 

My practice: I try not to generate more code than I can comfortably review in a single session or maybe the next day. Also, as someone who is still learning a lot of this stuff, making the transition from a hobby programmer to a full-time programmer, if I can't explain how it works, if I don't understand how it works, I need to look into learning how it works because I am going to be on task to fixing it if it breaks. 

---

# Caveats

- Not necessarily faster
- Shift focus from code syntax to architecture, requirements, review, and testing
- Comprehension risk 


Some of the caveats so far are that it's not necessarily faster. Some people have reported it's very fast. Some people have reported it's not fast. Some people have reported it's fast, but code quality is significantly compromised. These are issues that we need to work out.

I've been leaning on this a lot because broken hand, but it is something that I am not choosing to go into blindly. This needs to be evaluated, and I need to take care in terms of how and when to use this intentionally. 

Okay, another thing that's been found is that developers don't do faster work, but they do more detailed work. The focus shifts to architecture review, design considerations, and more complete testing. That is something that we need to think about and manage.

There are a couple of papers that come from Anthropic. Incidentally, there is a comprehension risk that if people who rely on an AI to give them code without looking at the documentation, as opposed to using the code, use the AI to intend to interrogate what the library is doing and how the library is designed, they come out of the experiment with lower comprehension of what was created. Again, intentionality very much matters in terms of how you are using the tool. 

