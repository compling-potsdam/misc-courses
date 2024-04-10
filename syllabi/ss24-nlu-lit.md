*Natural Language Understanding? D. Schlangen, U Potsdam, Summer 2024*

*v0.1 2024-04-10: initial version (based on last year's edition)*


## Syllabus for "Understanding, Meaning, and Machines", Summer 2024, D. Schlangen


### Content and Practical Information

#### Course Content


How does a sign on a billboard use language? It doesn't; whoever put writing on the sign is using the sign to use language. How does your computer use language when it shows you an error message? Again, it doesn't; the programmer who connected the string to a triggering condition does. How does a parrot use language? Again, arguably, it doesn't, although it gets harder to explain why, and what is even happening when a parrot vocalises something. Finally -- how does a Large Language Model use language?

This course will deal with the question of how best to characterise what these new computer systems do with language. 
To make matters concrete, we will look at situations like the following. Suppose you typed into a cLLM ("chat-optimized LLM", such as ChatGPT) the string
"What happened in November 1963 in Dallas?", and you received the output 
"In November 1963, President John F. Kennedy was assassinated in Dallas, Texas." 
What is the connection between this production of that string, or of that sentence, and the state of affairs of JFK having been assassinated? What needs to be the case for such a production to be justifiably understood as an assertion, and for the name "John F. Kennedy" to refer to the historical person (with whom very few speakers today will have been personally acquainted)?
What does it mean, if anything, if a system that has produced this string (which we would take to be a true claim) is also liable to produce strings that evaluate as false? What, if anything, changes if the system then becomes less liable to do so?

Thinking about these question will take us on a long journey, starting from the unhappy state that evaluation of Large Language Models (as "understanding machines") is in; going back in time to earliest attempts at thinking about how to evaluate thinking machines, and returning, via learning about classic theories of meaning and understanding, to criticisms of "old AI" and reflections in criticism of "new AI", ending in discussions about what might be lacking in connections to the world (the physical and the social one). 

This is not a course about building Natural Language Understanding systems. We have other courses where that is the topic. Nevertheless, the course requires a good technical understanding of LLMs---as well as the ability to read and critically engage with literature from a variety of fields.



#### Technicalities


**Main Reading** is the material that we will discuss in class. This must be read by all, and prepared by the presenters / discussion leaders. **Background Reading** is material that will help understand the main reading material, and must be read by the presenters (and is recommended to all). **Further Reading** is material that you can use to follow up on the topic of the week, if it caught your interest.

This is a reading and discussion based course. The assumption will be that everyone has read everything under "Main Readings". Nevertheless, to help with the discussion, for each session there will be two "designated discussants". Their job is not necessarily to prepare a presentation / slides, but rather is to know the structure of the (argument in the) paper particularly well and to have thought about which segments of the text (or diagrams in it) will be particularly worth discussing.

It can be a good idea to prepare a handout that can be distributed via moodle before the class. For this, you can copy verbatim sections of the paper around which you can structure the discussion, or figures from the paper, or examples of data from datasets, etc.. Prepare questions that you have or that you think can be discussed / viewed from different perspectives. (Send this to me on the Monday before your slot, so I can give feedback.)

Here are some guiding questions that you can bring to the text:

- What kind of view of meaning is implicitly (or sometimes even explicitly) argued for in the text? What is left out?
- Implicitly or explicitly, what view of the *function* of language is espoused by the paper? Language as form of thought, or language as means for communication?
- If relevant, what are the practical reflections of meaning / understanding that the text investigates? How representative of the phenomenon are they, in your opinion? What is left out?
- How does the view expressed in the paper relate to what we've heard so far?
- How does what is labelled "understanding" in the paper relate to ordinary uses of that word, or ascriptions of "understanding" to persons or situations?

As we will quite extensively read from the papers during class, and skip around in them, please bring to each session a device with a reading surface larger than a mobile phone. (I count paper -- like, actual paper, made from trees, requiring no batteries -- as such a device. That is, you can actually print the reading material. Talk to me if you don't have access to a printer but would like to bring hardcopies.)


**Passing the course:** You need to have filled the role of discussant as often as necessary, and you need to participate in the discussions (which presupposes having read the week's material) in all sessions.

**Grade for the module:** To get a grade for the course, you will have to write a term paper on topics from the course (can be on what you presented).




### Overview

1. [Introduction](#intro)
2. [Benchmarking](#bench)
2. [The Turing Test](#turing)
2. [Meaning and Understanding](#meaning)
2. [The Chinese Octopus](#octo)
2. [Grounding and Embodiment](#ground)
2. [Computer Speech Acts](#acts)



***A side-note on literature selection:*** Quite a few of the papers below are pre-prints, that is, are not peer-reviewed. These are to be taken with a grain of salt, of which we will provide an ample supply. We will discuss in class the problems with the pre-print culture. For your final projects, you should select only regularly published papers.


### Introduction <a name="intro"></a>

In the first session, I will review how we got here (from Markov Chains to LLMs to chat-optimized LLMs [cLLMs; "clems"]), and I will introduce the guiding questions for this course, helping us to clarify how we should think about these models.



#### Background Material

- A recent talk of mine, "[NLP Use and Language Use: Toward Artificial Language Users?](https://clp.ling.uni-potsdam.de/talks/index.html#lithme)" that uses the same setup (comparing different ways language can come into the world). If you feel like listening to another 70 minutes of me talking.
- [Last year's edition](https://github.com/compling-potsdam/misc-courses/blob/master/syllabi/ss23-nlu-lit.md) of this class, with a slightly different reading list, with a bit more on reactions to LLMs, and less background.
- [The 2022 edition](https://github.com/compling-potsdam/misc-courses/blob/master/syllabi/ss22-nlu-lit.md) of this class, with a slightly different reading list, focussing a bit more on evaluation.



#### Technical Background

Here are some recent articles that may help you get up to speed with the technical background:

- Mark Riedl, [A Very Gentle Introduction to Large Language Models without the Hype](https://mark-riedl.medium.com/a-very-gentle-introduction-to-large-language-models-without-the-hype-5f67941fa59e); a nice introduction article
- Stephen Wolfram, [What is ChatGPT Doing... and Why Does it Work?](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/); a longer introduction, a little less hype-free
- Sebastian Raschka, [Understanding Large Language Models](https://magazine.sebastianraschka.com/p/understanding-large-language-models); a collection of resources


### Topic 1 - Benchmarking: Of Car-Salesmen and the Gish Gallop <a name="bench"></a>

We'll start with a look at how the creators of large language models try to convince themselves, and others, that their offering really is good, or at least, is better than yesterday's offering. Or in other words, how is *the model's ability to understand language* measured in practice in 2024?


#### 1.1 - Benchmarking: How It's Used

#### Activity

This first session will have a slightly different format from the subsequent ones. Our example exhibit is (Touvron *et al.* 2023), the paper introducing the Llama-2 model family. We will focus exclusively on Section 2.3, "Model Evaluation". The tasks of the presenters will be as follows:

1. What exactly did Touvron *et al.* (2023) do in terms of evaluation? What claims do they derive from their numbers? Do they mention words like "understanding", "meaning", "intelligence" (or even just "language")?
2. Zoom in: Make a selection of the evaluation approaches used in this section, and look at the original papers. (By April 18, upload the selected papers to Moodle, so that we can prepare as well.)
    1. What do these papers themselves claim that their task / dataset measures? How do they measure this?
	2. How was this data created?
	3. If you can find it, show us some examples of the data. (Many datasets you will be able to find also on [huggingface | datasets](https://huggingface.co/datasets).)
3. As your second task, investigate two popular ways of ranking LLMs: [huggingface OpenLLMleaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard) and the [ChatbotArena](https://huggingface.co/spaces/lmsys/chatbot-arena-leaderboard). How do they work? What can we read off the rankings?

What we want to discuss in class is what exactly one should conclude from these instruments, what their scientific validity is, and perhaps also how this relates to what the authors of these papers and methods may want us to conclude from them.


#### Main Readings

- Touvron *et al.* / Meta AI (2023), Llama 2: Open Foundation and Fine-Tuned Chat Models; [ArXiv link](https://arxiv.org/abs/2307.09288)
- ... plus the selections made by the presenters


#### Further Readings

- If you're wondering what the Gish Gallop is of the title of this section, here's a great [talk by Adina Williams, "Evaluation after the LLM boom",](https://genbench.org/assets/workshop2023_slides/williams_genbench2023.pdf) from a [recent workshop](https://genbench.org/workshop_programme/2023/).
- Schlangen, David (2023), Dialogue Games for Benchmarking Language Understanding: Motivation, Taxonomy, Strategy. [ArXiv link](https://arxiv.org/abs/2304.07007). Touches on issues of test validity.
- Bubeck, S., Chandrasekaran, V., Eldan, R., Gehrke, J., Horvitz, E., Kamar, E., … Zhang, Y. (2023). Sparks of Artificial General Intelligence: Early experiments with GPT-4. Retrieved from <http://arxiv.org/abs/2303.12712>  
   [This is a lightly edited collection of anecdotes of interactions with GPT4, some 100 pages long, but formatted to look like a research paper. You can skim this and sample examples from the sections. What are the authors claiming that they are doing with this paper? Is this research? Is this an informative way to explore the capabilities of a model?]



#### 1.2 - Benchmarking Generalist Models

In a way, we are going backwards a bit. Last week, we've seen what people actually do. This week, we'll look at some older proposals of what they *should* be doing. Specifically, we will look at efforts to address the situation where models aim to be "generalists". How do you evaluate "everything"?


#### Main Readings

These are extremely long papers. The task of the presenters will be do select the most relevant sections for discussion. (Let us know what your selection is by April 30th, via Moodle.)

- Aarohi Srivastava & very very mand other authors (2022), Beyond the Imitation Game: Quantifying and Extrapolating the Capabilities of Language Models. ArXiv.
- Liang, P., Bommasani, R., Lee, T., Tsipras, D., Soylu, D., Yasunaga, M., … Koreeda, Y. (2022). Holistic Evaluation of Language Models. ArXiv.


#### Background Readings

- Levin, Janet, "Functionalism", The Stanford Encyclopedia of Philosophy (Summer 2023 Edition), Edward N. Zalta & Uri Nodelman (eds.), forthcoming URL = <https://plato.stanford.edu/archives/sum2023/entries/functionalism/>


#### Further Readings

- David Schlangen. 2021. Targeting the Benchmark: On Methodology in Current Natural Language Processing Research. In Proceedings of ACL 2021, pages 670–674, Online. Association for Computational Linguistics. [pdf](https://aclanthology.org/2021.acl-short.85/)
- Raji, I. D., Bender, E. M., Paullada, A., Denton, E., & Hanna, A. (2021). AI and the Everything in the Whole Wide World Benchmark. In NeurIPS 2021 Track on Datasets and Benchmarks. 


### Topic 2: The Turing Test <a name="turing"></a>

One of last week's papers claims to go "beyond the Imitation Game". But what is that "Imitation Game"? This week, we go back 70 years, to even before computers were invented, and look at an early attempt at answering the question of how to evaluate them.

We will discuss what this test implicitly says about what intelligence is, and how much of what it put forward may still be present in today's tests.


#### Main Readings

- Turing, A. M. (1950). Computing Machinery and Intelligence. Mind, 59(236), 433–460. [Sections 1--3, 6, 7.]


#### Background Readings

- Hofstadter, D. (1981), "The Turing Test: A Coffeehouse Conversation"; ch. 5 in Hofstadter, D. and Dennett, D. (1981), "The Mind's I", Basic Books.
- Saygin, A. P, Cicek, I., and Akman, V. (2000), "Turing Test: 50 Years Later".




### Topic 3: Meaning and Understanding <a name="meaning"></a>

By this point, we have seen many attempts at getting at meaning and understanding via doing something. Maybe there is a way of accessing "meanings" more directly? What kinds of things are these, anyway? Let's look at what the responsible scientific disciplines have thought up.

We'll look at three classics from the Philosophy of Language, and one example of typical thinking in the more applied domains.


#### 3.1: Where Are the Meanings?

This week we'll have two papers that may seem to take opposing positions. Hagoort (2019), representatively for most of neuroscience, and possibly also AI, quite explictly locates meanings "behind the eyes and between the ears". Putnam (1975) quite explicitly says "meanings just ain't in the head".


##### Main Readings

- Hagoort, P. (2019). The meaning-making mechanism(s) behind the eyes and between the ears. Philosophical Transactions of the Royal Society B., 375.

- Putnam, Hilary (1975). The meaning of 'meaning'. Minnesota Studies in the Philosophy of Science 7:131-193.


##### Background Readings

- Lycan, William (2019). Philosophy of Language: A Contemporary Introduction. Routledge. [Chapters 1, 5-7, 9]



#### 3.2: Meanings or Doings?

This week's papers attack the idea that "meanings" even are things, putting focus instead more on *intentions*, or on *uses* / *activities*. This will bring us back to questions of what good activities are to test understanding.



##### Main Readings

- Grice, H. Paul (1957). Meaning. The Philosophical Review, 66:3, p. 377--388.

-  Wittgenstein, Ludwig (1953). _Philosophical Investigations_. New York, NY, USA: Wiley-Blackwell. [§§ 1--43, 143--158]



##### Background Readings

- Baker, G.P and Hacker, P.M.S. (2009). Wittgenstein: Understanding and Meaning. 2nd edition. Wiley-Blackwell. [Chapter 8, "meaning and use"; Chapter 17, "understanding and ability"]

- Lycan, William (2019). Philosophy of Language: A Contemporary Introduction. Routledge. [Chapters 1, 5-7, 9]





### Topic 4: The Chinese Octopus in The Underwater Room <a name="octo"></a>

Whatever those meanings are, can computers *have* them? Or *acquire* them? In this unit, we discuss two influential papers that claim otherwise.


#### 4.1: The Chinese Room

This week's paper introduced an influential "thought experiment" (or "intuition pump"), aiming to show, via a *reductio ad absurdum*, that something that *executes* rules cannot "have" meanings.



##### Main Readings

- Searle, John (1980). Minds, brains, and programs. Behavioral and Brain Sciences 3 (3):417-57.


##### Background Readings

- Hofstadter, D. (1981), "Reflections on Searle"; ch. 22 in Hofstadter, D. and Dennett, D. (1981), "The Mind's I", Basic Books.
- Dennett, D. (1981), "The Intentional Stance"; ch 9; MIT Press
- Churchland, P. M., & Churchland, P. S. (1990). Could a machine think? Scientific American, 262(1), 32–37. 


#### 4.2: The Octopus Paper

This week's paper is much more recent, but has also proven influential (if for the opposition it created). In certain ways, its central piece can be seen as an update of Searle's argument for the learning machine era; it also offers a variety of other claims that will connect to the material of later weeks.

##### Main Readings

- Bender, E. M., & Koller, A. (2020). Climbing towards NLU: On Meaning, Form, and Understanding in the Age of Data. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics (ACL) (pp. 5185–5198).


##### Background Readings

- Søgaard, A. (2023). Grounding the Vector Space of an Octopus: Word Meaning from Raw Text. Minds and Machines.



#### Topic 5: Grounding and Embodiment <a name="ground"></a>

One way of reading the type of criticism voiced in last week's paper is that "text is not enough". What could be missing? One aspect is the connection to other modalities, which would provide "perceptual grounding", the other is the connection to, or rather placement in, the entity that "has" the meanings --- which, at least so far, tends to be a live human *body*.

##### Main Readings

- Harnad, S. (1990). The Symbol Grounding Problem. Physica D, 42, 335–346.
- Barsalou, L. W. (2008). Grounded Cognition. Annual Review of Psychology, 59(1), 617–645. 



#### Topic 6: Computer Speech Acts <a name="acts"></a>

We're on the home stretch. With all the conceptual tools we have collected by now, we can turn our attention to the "other side": What about *meaning something*? That is, instead of *grasping* meanings, *producing* meanings? Can machines produce meanings?


##### 6.1: Using Language?

This week we will be looking at a theory of language use that in certain respects follows up on Grice 1957, by placing *intentions*, and especially *joint intentions* and *joint activities* in the center. This is about real / human/human communication, but our guiding question will be what this can tell us about human/computer interaction (communication?).

###### Main Readings

* Clark, Herbert (1996). Using Language. Cambridge University Press. [Chapter 3, "Joint Actions"; Chapter 4, "Common Ground"; Chapter 5, "Meaning and Understanding"; and Chapter 7, "Joint Projects"]


##### 6.2: Assertion

We will close with a look at one particularly, arguably central, speech act, that of *assertion*. What needs to be true about an entity for it to be an *asserter*? Our question in the background will be whether this is true of LLMs, or even could ever be true about machines.

#### Main Readings

- Axel Gelfert (2014). A Critical Introduction to Testimony. [Chapter 1 "What is Testimony"]]. Bloomsbury Academic.
- Sanford Goldberg (2015). Assertion. Oxford University Press. [Chapter 1 "What is Assertion? In Defense of the Norm-Based Account"; Chapter 4 "Assertion and the Method of Interpretation", pp. 95,96; Chapter 7 "The Ethics of Assertion (and Belief)"]


#### Background Readings

- Harris, P. L., Koenig, M. A., Corriveau, K. H., & Jaswal, V. K. (2018). Cognitive Foundations of Learning from Testimony. Annual Review of Psychology, 69, 251–273.


#### Further Readings

- Schlangen, D. (2022), "Norm Participation Grounds Language". Proceedings of the "(dis)embodiment workshop", Gothenburg.


