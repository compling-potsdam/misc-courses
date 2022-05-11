*Natural Language Understanding? D. Schlangen, U Potsdam, Summer 2022*

*v0.4 2022-05-11: selection made in 2; some papers moved*

## Syllabus for "Natural Language Understanding: What does it Mean?", Summer 2022, D. Schlangen

### Preliminaries

#### Content

The goal to endow computers with general "Natural Language Understanding" has come back from being somewhat obscure for a while to now being at the forefront of NLP again --- with the result that rumour now has it that it has been reached. In NLP, the way that capabilities are framed and operationalised is through *language tasks* instantiated in *datasets*, which serve as *benchmarks*  for measuring the degree of presence of the capability; so that "having" a type of capability becomes "reaching high numbers on the metrics defined for the benchmark datasets", which, if high enough, in turn then is taken to mean that the dataset / task / capability is "solved". If this is to be more than (overloaded) labelling, the question becomes whether the benchmark actually covers the phenomenon of interests, or, even more fundamentally, whether the phenomenon is one that lends itself to the presuppositions behind this whole approach.

In this course, we will investigate this question, taking a long journey from current practices in NLP benchmarking, through work from the philosophy of language on what "meaning" (and hence, "understanding") might be, to work that suggests that whatever meaning is, it is to include more than what is typically measured, back to the question of modelling and measuring. Note that this course is *not* about *methods* for "doing" NLU, or at least not directly (we have other courses that touch more directly on this); it is about the conditions of possiblity of machine language understanding, and about how to think about the topic. Hence, a focus will be on (critical) reading of papers with respect to the arguments they make (implicitly or explicitly), and on finding our way around this rather wide-ranging and ultimately rather important topic -- after all, meaning making and understanding is arguably a large part of what defines us as human beings.


#### Technicalities

**Main Reading** is the material that we will discuss in class. This must be read by all, and prepared by the presenters / discussion leaders. **Background Reading** is material that will help understand the main reading material, and should be read by the presenters (and is recommended to all). **Further Reading** is material that you can use to follow up on the topic of the week, if it caught your interest.

**Instructions for presenters:** The main focus should be on the *discussion* of the text. You should assume that everybody has read the text. It can be a good idea to prepare a couple of slides that summarise the main points or technical details (which, unless you have very good reasons, should be done in the order that they appear in the paper), but also consider making a handout. (A PDF that will be distributed via moodle, and which, if you send it to me early enough, I will print out in a number of copies before class.) For this, you can copy verbatim sections of the paper around which you can structure the discussion, or figures from the paper, or examples of data from datasets, etc.. Prepare questions that you have or that you think can be discussed / viewed from different perspectives.

Here are some guiding questions that you can bring to the text:

- What kind of view of meaning is implicitly (or sometimes even explicitly) argued for in the text? What is left out?
- Implicitly or explicitly, what view of the *function* of language is espoused by the paper? Language as form of thought, or language as means for communication?
- If relevant, what are the practical reflections of meaning / understanding that the text investigates? How representative of the phenomenon are they, in your opinion? What is left out?
- How does the view expressed in the paper relate to what we've heard so far?
- Keeping it real: How does what is labelled "understanding" in the paper relate to ordinary uses of that word, or ascriptions of "understanding" to persons or situations?

Some further notes: For papers from *ACL conferences (ACL, NAACL, EACL, etc.), it is likely that you can find a video of the conference presentation on the ever useful [ACL anthology](https://aclanthology.org).

**Passing the course:** You need to present / lead the discussion at least once, and you need to participate in the discussions (which presupposes having read the week's material) in all sessions. If we have more slots than participants, some of you will have to present more than once.

**Grade for the module:** To get a grade for the course, you will have to write a term paper on topics from the course (can be on what you presented).


### Overview

1. [Introduction](#intro)
2. Topic 1: [Benchmarking](#bench)
2. Topic 2: [Meaning, as Seen from NLP](#nlpmean)
2. Topic 3: [Symbol Grounding](#ground)
2. Topic 4: [Classic NLU](#classic)
2. Topic 5: [Meanings, as Seen from the Philosophy of Language](#phil)
2. Topic 6: [Word Meanings](#words)




### Introduction <a name="intro"></a>

We start with a puzzle: We have NLP models that seem to be solving tasks that seem to require fairly sophisticated language understanding, and yet the "intelligent agents" (Alexa, Siri, etc.) that we have ... kind of suck. Why is that? Is that because Amazon, Apple, etc are lazy, and don’t yet know how to utilise these "natural language understanding" models? Or is it that the kind of understanding exhibited on NLP language tasks is different from the practical understanding required for intelligent assistants? And if that is so, is that a problem, and for whom?
Is "understanding" something that can be exhibited and measured in single instances of "understanding tasks", with these measures then being aggregated into an average score of "understanding", or is it something that must be sustained and (cooperatively) achieved?
<!-- Or both? But if so, how are these manifestations of "understanding" related? -->

This framing has already used a distinction that I will try to sharpen a bit further and probe for its use for guiding (and measuring) developments in NLP, as the difference between the *language task approach*, and the *language games approach*. The former is the dominant approach in NLP, and consequently will take up more space in the course. The language games approach, on the other hand, is derived from a view of langauge that has been very influential in the philosophy of language and in linguistic pragmatics, and we will discuss these roots to see if they can be made productive for our current problems. 





#### Background Material

- David Schlangen. 2021. Targeting the Benchmark: On Methodology in Current Natural Language Processing Research. In Proceedings of ACL 2021, pages 670–674, Online. Association for Computational Linguistics. [[pdf]](https://aclanthology.org/2021.acl-short.85/)
- Schlangen, D. 2019. Language Tasks and Language Games: On Methodology in Current Natural Language Processing Research. CoRR 2019  (an older, but longer version of the above that focusses more on the distinction between tasks and games) [[pdf]](https://clp.ling.uni-potsdam.de/bibliography/Schlangen-2019-1/)
- a recent talk of mine, "[Are We Nearly There Yet? On NLU and NL-Use](https://clp.ling.uni-potsdam.de/talks/index.html#nearlythere)", that starts from the same puzzle (indeed, the same slides); with video of the talk, if you feel like listening to another hour of me talking.
- very recent (2022-04-18) blog post by Emily Bender, [On NYT Magazine on AI: Resist the Urge to be Impressed](https://medium.com/@emilymenonbender/on-nyt-magazine-on-ai-resist-the-urge-to-be-impressed-3d92fd9a0edd)
- A class that's actually on the *how* of NLU: Chris Potts' [CS224U: Natural Language Understanding](https://web.stanford.edu/class/cs224u/)
- Again Chris Potts, with [Perspectives on meaning and interpretation](https://web.stanford.edu/class/linguist130a/materials/ling130a-meaning-interpretation.pdf)



### Topic 1: Benchmarking <a name="bench"></a>

#### 1.1: General Language Understanding Evaluation; Imitation Game

##### Main Readings

* Presentation 1

    * Wang, A., Singh, A., Michael, J., Hill, F., Levy, O., & Bowman, S. R. (2019). GLUE: A Multi-Task Benchmark and Analysis Platform for Natural Language Understanding. In ICLR 2019.
    * Wang, A., Pruksachatkun, Y., Nangia, N., Singh, A., Michael, J., Hill, F., … Bowman, S. R. (2019). SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems. In NeurIPS.  [main focus; data can be explored via [Hugging Face Datasets](https://huggingface.co/datasets/super_glue)]
* Presentation 2
    * Turing, A. M. (1950). Computing Machinery and Intelligence. Mind, 59(236), 433–460. [Sections 1--3, 6, 7.]


##### Background 

* Williams, A., Nangia, N., & Bowman, S. R. (2018). A Broad-Coverage Challenge Corpus for Sentence Understanding through Inference. In NAACL 2018.
* Nangia, N., & Bowman, S. R. (2019). Human vs. Muppet: A conservative estimate of human performance on the GLUE benchmark. In ACL 2019 - 57th Annual Meeting of the Association for Computational Linguistics, Proceedings of the Conference - Short Papers (pp. 4566–4575).
* The [BIG-bench (Beyond the Imitation Game Benchmark)](https://github.com/google/BIG-bench) project.

##### Further Reading

* Hendrycks, D., Mazeika, M., Burns, C., Song, D., Zou, A., Steinhardt, J., & Berkeley, U. C. (2021). Measuring Massive Multitask Language Understanding. In ICLR.




#### 1.2: Extensions to Benchmarking Approach


##### Main Readings

* Kiela, D., Bartolo, M., Nie, Y., Kaushik, D., Geiger, A., Wu, Z., … Williams, A. (2021). Dynabench: Rethinking Benchmarking in NLP. In NAACL 2021 (pp. 4110–4124).
* Ribeiro, M. T., Wu, T., Guestrin, C., & Singh, S. (2020). Beyond Accuracy : Behavioral Testing of NLP Models with Check List. In ACL 2020 (pp. 4902–4912).


##### Background

* The [dynabench project page](https://dynabench.org/).


##### Further Reading

* Zheng, Y., Zhou, J., Qian, Y., Ding, M., Liao, C., Li, J., … Yang, Z. (2022). FewNLU: Benchmarking State-of-the-Art Methods for Few-Shot Natural Language Understanding. Retrieved from http://arxiv.org/abs/2109.12742


#### 1.3: Critique of Benchmarking

##### Main Reading

* Raji, I. D., Bender, E. M., Paullada, A., Denton, E., & Hanna, A. (2021). AI and the Everything in the Whole Wide World Benchmark. In NeurIPS 2021 Track on Datasets and Benchmarks. 
* Bowman, S. R., & Dahl, G. E. (2021). What Will it Take to Fix Benchmarking in Natural Language Understanding? In NAACL 2021 (pp. 4843–4855). 


##### Background

* Sinha, K., Parthasarathi, P., Pineau, J., & Williams, A. (2021). UnNatural Language Inference. In ACL 2021 (pp. 7329–7346).




### Topic 2: Meaning, as seen from NLP <a name="nlpmean"></a>

#### Main Readings

* Dunietz, J., Burnham, G., Bharadwaj, A., Rambow, O., Chu-Carroll, J., & Ferrucci, D. (2020). To Test Machine Comprehension, Start by Defining Comprehension. In ACL 2020 (pp. 7839–7859).
* Bender, E. M., & Koller, A. (2020). Climbing towards NLU: On Meaning, Form, and Understanding in the Age of Data. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics (ACL) (pp. 5185–5198).


#### Background

* The Stanford Encyclopedia of Philosophy on [The Chinese Room Argument](https://plato.stanford.edu/entries/chinese-room/)
* 2020 Blog Post by Chris Potts, [Is it possible for language models to achieve language understanding?](https://chrisgpotts.medium.com/is-it-possible-for-language-models-to-achieve-language-understanding-81df45082ee2)
* Trott, S., Chang, N., & Schneider, N. (2020). (Re)construing Meaning in NLP. In ACL 2020 (pp. 5170–5184).



### Topic 3: Symbol Grounding <a name="ground"></a>


#### Main Reading

* Chandu, K. R., Bisk, Y., & Black, A. W. (2021). Grounding “Grounding” in NLP. In Findings of ACL-IJCNLP 2021 (pp. 4283–4305).
* Bisk, Y., Holtzman, A., Thomason, J., Andreas, J., Bengio, Y., Chai, J., … Turian, J. (2020). Experience grounds language. EMNLP 2020 - 2020 Conference on Empirical Methods in Natural Language Processing, Proceedings of the Conference, 8718–8735. [main focus]


#### Background

* Harnad, S. (1990). The Symbol Grounding Problem. Physica D, 42, 335–346.
* McClelland, J. L., Hill, F., Rudolph, M., Baldridge, J., & Schütze, H. (2019). Extending Machine Language Models toward Human-Level Language Understanding, 1–8.  https://doi.org/10.48550/arXiv.1912.05877



### Topic 4: A Blast from the Past: Classic NLU <a name="classic"></a>

#### Main Reading

* Allen, James (1995). Natural Language Understanding. Benjamin / Cummings. [Chapter 1, Introduction]
* Condoravdi, C., Crouch, R., de Paiva, V., Stolle, R., & Bobrow, D. G. (2003). Entailment, intensionality and text understanding. In Proc. of the HLT-NAACL 2003 Workshop on Text Meaning (pp. 38–45). 




### Topic 5: Theories of Meaning / Philosophy of Language <a name="phil"></a>

#### 5.1: Overview; Using Language

##### Main Readings

* Lycan, William (2019). Philosophy of Language: A Contemporary Introduction. Routledge. [Chapters 1, 5-7, 9] (Could be distributed over several presenters?)
* Clark, Herbert (1996). Using Language. Cambridge University Press. [Chapter 5, "meaning and understanding"]


##### Background

* Clark, Herbert (1996). Using Language. Cambridge University Press. [Chapter 4, "common ground"]


#### 5.2: Meaning as Use (for a large class of cases)

##### Main Reading

*  Wittgenstein, Ludwig (1953). _Philosophical Investigations_. New York, NY, USA: Wiley-Blackwell. [§§ 1--43, 143--158]


##### Background

* Baker, G.P and Hacker, P.M.S. (2009). Wittgenstein: Understanding and Meaning. 2nd edition. Wiley-Blackwell. [Chapter 8, "meaning and use".]


#### 5.3: Inferentialism / Conceptual Role Semantics 


##### Main Readings

(to be determined, one of:)

* Sellars, W. (1954). Some Reflections on Language Games. Philosophy of Science, 21(3), 204–228.
* Sellars, W. (1969). Language as Thought and as Communication. Philosophy and Phenomenological Research, 29(4), 506–527.
* Greenberg, M., & Harman, G. (2005). Conceptual Role Semantics. In OXFORD HANDBOOK OF PHILOSOPHY OF LANGUAGE (pp. 1–30).


#### Further Readings Topic 5

* Dennett, D. C. (1988). Précis of The Intentional Stance. Behavioral and Brain Sciences, 11(3), 495–505.
* Lewis, D. (1975). Languages and Language. In K. Gunderson (Ed.), Minnesota Studies in the Philosophy of Science.


#### Topic 6: Word Meanings <a name="words"></a>

##### Main Reading

* Lake, B. M., & Murphy, G. L. (2021). Word meaning in minds and machines. Psychological Review. 

##### Background 

* Bloom, P. (2001). Précis of How Children Learn the Meanings of Words. Behavioral and Brain Sciences, 24(06), 1095–1103. 
