*Natural Language Understanding? D. Schlangen, U Potsdam, Summer 2023*

*v0.4 2023-05-07: clarified role of discussants; v0.1 2023-04-12: initial version*

## Syllabus for "Natural Language Understanding and the Meaning of ChatGPT", Summer 2023, D. Schlangen

### Content and Practical Information

#### Course Content


How does a sign on a billboard use language? It doesn't; whoever put writing on the sign is using the sign to use language. How does your computer use language when it shows you an error message? Again, it doesn't; the programmer who connected the string to a triggering condition does. How does a parrot use language? Again, arguably, it doesn't, although it gets harder to explain why, and what is even happening when a parrot vocalises something. Finally -- how does a Large Language Model use language?

This course will deal with the question of how best to characterise what these new computer systems do with language. 
To make matters concrete, we will look at situations like the following. Suppose you typed into a cLLM ("chat-optimized LLM", such as ChatGPT) the string
"What happened in November 1963 in Dallas?", and you received the output 
"In November 1963, President John F. Kennedy was assassinated in Dallas, Texas." 
What is the connection between this production of that string, or of that sentence, and the state of affairs of JFK having been assassinated? What needs to be the case for such a production to be justifiably understood as an assertion, and for the name "John F. Kennedy" to refer to the historical person (with whom very few speakers today will have been personally acquainted)?
What does it mean, if anything, if a system that has produced this string (which we would take to be a true claim) is also liable to produce strings that evaluate as false, or if anything changes if it becomes less liable to do so.


Thinking about these question will take us on a long journey, starting from the (quite confused, as we will see) public discussion about such systems; over the increasingly helpless attempts at measuring what the programs do; to a deep dive into theories from linguistics pragmatics and the philosophy of language about what *we* do when we use language; and back to attempts at understanding LLMs---and ways of using them without being used by them.

This is not a course about building Natural Language Understanding systems. We have other courses where that is the topic. Nevertheless, the course requires a good technical understanding of LLMs---as well as the ability to read and critically engage with literature from a variety of fields.



#### Technicalities


**Main Reading** is the material that we will discuss in class. This must be read by all, and prepared by the presenters / discussion leaders. **Background Reading** is material that will help understand the main reading material, and should be read by the presenters (and is recommended to all). **Further Reading** is material that you can use to follow up on the topic of the week, if it caught your interest.

This is a reading and discussion based course. The assumption will be that everyone has read everything under "Main Readings". Nevertheless, to help with the discussion, for each session there will be two "designated discussants". Their job is not necessarily to prepare a presentation / slides, but rather is to know the structure of the (argument in the) paper particularly well and to have thought about which segments of the text (or diagrams in it) will be particularly worth discussing.

It can be a good idea to prepare a handout that can be distributed via moodle before the class. For this, you can copy verbatim sections of the paper around which you can structure the discussion, or figures from the paper, or examples of data from datasets, etc.. Prepare questions that you have or that you think can be discussed / viewed from different perspectives. (Send this to me on the Monday before your slot, so I can give feedback.)

Here are some guiding questions that you can bring to the text:

- What kind of view of meaning is implicitly (or sometimes even explicitly) argued for in the text? What is left out?
- Implicitly or explicitly, what view of the *function* of language is espoused by the paper? Language as form of thought, or language as means for communication?
- If relevant, what are the practical reflections of meaning / understanding that the text investigates? How representative of the phenomenon are they, in your opinion? What is left out?
- How does the view expressed in the paper relate to what we've heard so far?
- Keeping it real: How does what is labelled "understanding" in the paper relate to ordinary uses of that word, or ascriptions of "understanding" to persons or situations?

Besides the discussants, there will also be additional roles to fill, for "minute keepers with an interest". These will take notes during the discussion (while also engaging in it), from different points of view. For example: Imagine that you are sent by a regulator charged with making laws about the use of "AI technologies". Take note of anything that might be helpful for them! Another protocol to be prepared is for a company that is thinking about using these technoologies in their knowledge work (keeping records about the company, deriving insights from company data). What do they need to be aware of? The third role is to keep notes for a journalist planning to write an article about the wonderful new world of AI (or maybe the terrible upcoming dystopia, they haven't decided yet).

This means that almost everyone will be kept busy during each session. We will cycle through the roles so that they are all filled for each session.

As we will quite extensively read from the papers during class, and skip around in them, please bring to each session a device with a reading surface larger than a mobile phone. (I count paper -- like, actual paper, made from trees, requiring no batteries -- as such a device. That is, you can actually print the reading material. Talk to me if you don't have access to a printer but would like to bring hardcopies.)


**Passing the course:** You need to have filled each role (discussant and minute keeper roles) at least once, and you need to participate in the discussions (which presupposes having read the week's material) in all sessions.

**Grade for the module:** To get a grade for the course, you will have to write a term paper on topics from the course (can be on what you presented). (To be confirmed; I'm also thinking about using writing a blogpost or making a podcast as an alternative.)




### Overview

1. [Introduction](#intro)
2. [Phenomenology: Public Perception of cLLMs](#phen)
2. [What We Talk About When We Talk About LLMs](#talk)
2. [Benchmarking](#bench)
2. [Joint Action & Common Ground](#cg)
2. [Speaker Meaning](#lit)
2. [Symbol Grounding](#sg)
2. [Reference and Externalism](#ext)
2. [LLMs as Agent Models](#llma)
2. [Assertion and Knowledge from Testimony](#ass)
2. [Uses Worth Wanting](#use)
2. [Outro](#outro)



***A side-note on literature selection:*** Quite a few of the papers below are pre-prints, that is, are not peer-reviewed. These are to be taken with a grain of salt, of which we will provide an ample supply. We will discuss in class the problems with the pre-print culture. For your final projects, you should select only regularly published papers.


### Introduction <a name="intro"></a>

In the first session, I will review how we got here (from Markov Chains to LLMs to chat-optimized LLMs [cLLMs; "clems"]).



#### Background Material

- A recent talk of mine, "[NLP Use and Language Use: Toward Artificial Language Users?](https://clp.ling.uni-potsdam.de/talks/index.html#lithme)" that uses the same setup (comparing different ways language can come into the world). If you feel like listening to another 70 minutes of me talking.
- Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021). On the Dangers of Stochastic Parrots: Can Language Models Be Too Big ? In Conference on Fairness, Accountability, and Transparency (FAccT ’21), March 3–10, 2021, Virtual Event, Canada (Vol. 1). Association for Computing Machinery. 
- Jeremy Wanderer (2008), Robert Brandom. McGill-Queen's University Press. Chapter 1: Parrots.
- [Last year's edition](https://github.com/compling-potsdam/misc-courses/blob/master/syllabi/ss22-nlu-lit.md) of this class, with a slightly different reading list, focussing a bit more on evaluation. Still very relevant marterial.

#### Technical Background

Here are some recent articles that may help you get up to speed with the technical background:

- Mark Riedl, [A Very Gentle Introduction to Large Language Models without the Hype](https://mark-riedl.medium.com/a-very-gentle-introduction-to-large-language-models-without-the-hype-5f67941fa59e); a nice introduction article
- Stephen Wolfram, [What is ChatGPT Doing... and Why Does it Work?](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/); a longer introduction, a little less hype-free
- Sebastian Raschka, [Understanding Large Language Models](https://magazine.sebastianraschka.com/p/understanding-large-language-models); a collection of resources


### 01 - Phenomenology: Public Perception, Stunned Researchers, Panicking Rationalists <a name="phen"></a>

We'll start with a look at the state we're in: Confusion about what it all means. (This is what we'll try to help clear up over the rest of the semester.)



#### Activity

Bring examples from local media articles. (Better: Upload them to or put link into page on moodle, so that we can show them in class / use machine translation, if necessary.) How does the article talk about ChatGPT? What kinds of attributes does it ascribe to the sytem, explicitly or implicitly? Does it use terms like "understanding", "thinking"? What is the stance that takes towards it -- positive, negative, neutral? What does it say about its abilities, practical and in principle? 



#### Main Readings

- Bubeck, S., Chandrasekaran, V., Eldan, R., Gehrke, J., Horvitz, E., Kamar, E., … Zhang, Y. (2023). Sparks of Artificial General Intelligence: Early experiments with GPT-4. Retrieved from <http://arxiv.org/abs/2303.12712>  
   [This is a lightly edited collection of anecdotes of interactions with GPT4, some 100 pages long, but formatted to look like a research paper. You can skim this and sample examples from the sections. We will discuss this paper more on a meta-level: What are the authors claiming that they are doing with this paper? Is this research? Is this an informative way to explore the capabilities of a model?]
- Eliezer Yudkowsky (2023), ["Pausing AI Developments Isn't Enough. We Need to Shut it All Down](https://time.com/6266923/ai-eliezer-yudkowsky-open-letter-not-enough/). Time Magazine, March 2023.  
   This is... what is this? Again, we will be discussing this on a meta-level. What are the presuppositions made here about what the current state is, and where it is going? What is this saying about near-term risks, and what is it saying about far-far-far term risks?



#### Background Readings

- Lee Vinsel (2021), ["You're Doing It Wrong: Notes on Criticism and Technology Hype"](https://sts-news.medium.com/youre-doing-it-wrong-notes-on-criticism-and-technology-hype-18b08b4307e5). Medium Blog Post, February 1st 2021.
- Emily Bender (2022), ["On NYT Magazine on AI: Resist the Urge to be Impressed"](https://medium.com/@emilymenonbender/on-nyt-magazine-on-ai-resist-the-urge-to-be-impressed-3d92fd9a0edd)


#### Further Readings

- Nathan Lambert (2023), ["Behind the curtain: what it feels like to work in AI right now"](https://robotic.substack.com/p/behind-the-curtain-ai). Newsletter Post. (An interesting look at the real consequences of the situation / the hype on AI research.)
- Gebru, T. and Torres, Émile P. (2023), ["Eugenics and the Promise of Utopia through Artificial General Intelligence"](https://www.youtube.com/watch?v=P7XT4TWLzJw), Keynote at the IEEE Conference on Secure and Trustworthy Machine Learning, February 2023. (Link to YouTube recording.)




### 02 - What We Talk About When We Talk About LLMs <a name="talk"></a>

#### Main Readings

- Shanahan, M. (2023). Talking About Large Language Models. ArXiv.
- Bowman, S. R. (2023). Eight Things to Know about Large Language Models. ArXiv.
- David Schlangen (2023), What a Situated Language-Using Agent Must be Able to Do: A Top-Down Anaylsis. ArXiv

<!--
#### Background Readings
-->

#### Further Readings
- Stephen Wolfram, ["What is ChatGPT Doing ... and Why Does it Work?"](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/). Blogpost.




### 03 - Benchmarking <a name="bench"></a>

#### Main Readings

The first two are again extremely long papers. We need to discuss in the week prior to discussion what to focus on.

- Aarohi Srivastava & very very mand other authors (2022), Beyond the Imitation Game: Quantifying and Extrapolating the Capabilities of Language Models. ArXiv.
- Liang, P., Bommasani, R., Lee, T., Tsipras, D., Soylu, D., Yasunaga, M., … Koreeda, Y. (2022). Holistic Evaluation of Language Models. ArXiv.
- Schlangen, David (2023), Dialogue Games for Benchmarking Language Understanding: Motivation, Taxonomy, Strategy. ArXiv.

#### Background Readings

- Levin, Janet, "Functionalism", The Stanford Encyclopedia of Philosophy (Summer 2023 Edition), Edward N. Zalta & Uri Nodelman (eds.), forthcoming URL = <https://plato.stanford.edu/archives/sum2023/entries/functionalism/>


#### Further Readings




### 04 - Joint Action and Common Ground <a name="cg"></a>

#### Main Readings

* Clark, Herbert (1996). Using Language. Cambridge University Press. [Chapter 3, "Joint Actions"; and Chapter 4, "Common Ground"]


#### Background Readings

#### Further Readings

<!--
TODO:
- think more about the convention angle..
-->








### 05 - Literal Meaning and Speaker Meaning, Convention and Intention<a name="lit"></a>

#### Main Readings

- Clark, Herbert (1996). Using Language. Cambridge University Press. [Chapter 5, "Meaning and Understanding"; and Chapter 7, "Joint Projects"]


#### Background Readings

- Grice, H. Paul (1957). Meaning. The Philosophical Review, 66:3, p. 377--388.
- Lycan, William (2019). Philosophy of Language: A Contemporary Introduction. Routledge. [Chapter 7] 


#### Further Readings

- Lewis, D. (1975). Languages and Language. In K. Gunderson (Ed.), Minnesota Studies in the Philosophy of Science.









### 06 - Symbol Grounding <a name="sg"></a>


#### Activity

Somewhat fitting to the topic, we'll take a break from reading, and do some watching. The topic of this session is "symbol grounding" and whether "it is needed", and this happens to be a question that quite recently was discussed at an event, which was recorded:
[Debate: Do Language Models Need Sensory Grounding For Meaning and Understanding?](https://wp.nyu.edu/consciousness/do-large-language-models-need-sensory-grounding-for-meaning-and-understanding/).

Your preparation task will be to watch the debate (and see if you can find the slides as well), and note which parts we should discuss in class. We can't watch the whole thing (it's over 2 hours!), but we should discuss some highlights, in the light of what we've learned so far in previous sessions.


#### Background Readings

- Harnad, S. (1990). The Symbol Grounding Problem. Physica D, 42, 335–346.
- Bender, E. M., & Koller, A. (2020). Climbing towards NLU: On Meaning, Form, and Understanding in the Age of Data. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics (ACL) (pp. 5185–5198).


#### Further Readings

- Søgaard, A. (2023). Grounding the Vector Space of an Octopus: Word Meaning from Raw Text. Minds and Machines.



### 07 - Reference and Externalism <a name="ext"></a>

#### Main Readings

- Cappelen, H and Dever, J (2021). "Making AI Intelligible: Philosophical Foundations". Oxford University Press. [Chapters 4 & 5]



#### Background Readings

- Lycan, William (2019). Philosophy of Language: A Contemporary Introduction. Routledge. [Chapter 4] 


#### Further Readings

- Cappelen, H and Dever, J (2021). "Making AI Intelligible: Philosophical Foundations". Oxford University Press. [Chapter 7]




### 08 - LLMs as Agent Models <a name="llma"></a>

#### Main Readings

- Andreas, J. (2022). Language Models as Agent Models. In Findings of EMNLP 2022. 

#### Background Readings

- David Schlangen (2023), What a Situated Language-Using Agent Must be Able to Do: A Top-Down Anaylsis. ArXiv


#### Further Readings



### 09 - Assertion and Knowledge from Testimony <a name="ass"></a>

#### Main Readings

- Sanford Goldberg (2015). Assertion. Oxford University Press. [Chapter 1 "What is Assertion? In Defense of the Norm-Based Account"; Chapter 4 "Assertion and the Method of Interpretation", pp. 95,96; Chapter 7 "The Ethics of Assertion (and Belief)"]
- Harris, P. L., Koenig, M. A., Corriveau, K. H., & Jaswal, V. K. (2018). Cognitive Foundations of Learning from Testimony. Annual Review of Psychology, 69, 251–273.


#### Background Readings


#### Further Readings

- Schlangen, D. (2022), "Norm Participation Grounds Language". Proceedings of the "(dis)embodiment workshop", Gothenburg.



### 10 - Uses Worth Wanting <a name="use"></a>

Having come this far, what can we now say about Uses Worth Wanting for LLMs? We'll discuss some examples from the interweb, examples you can bring, maybe guidelines that universities put out. In particular, we will try to analyse how these uses get around possible problems that we may have seen over the previous sessions. As what kind of thing do these uses treat the cLLMs?

- Simon Willison (<https://simonwillison.net>), as an example of a working programmer who seems to be loving it.
- <https://www.oneusefulthing.org/p/how-to-use-ai-to-do-practical-stuff>


#### Main Readings

#### Background Readings

#### Further Readings




### Conclusion <a name="outro"></a>

Bringing it all together.




