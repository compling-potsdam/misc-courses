*David Schlangen, 2022-10-04*
### Project Class "Language & Vision" 2022: GuessWhat?!


As part of the MSc "Cognitive Systems" at the University of Potsdam, students need to take two so-called "project modules", which are classes where the students get to do small research projects on given topics.

In the past couple of years, I've offered one such module every summer in the general area of "language and vision". In 2022, we focussed on the "GuessWhat?!" dataset (de Vries et al. 2017) (which is one of the few examples of sustained communal effort around the same dataset...).

In the first part of the class, the students presented (to each other) one paper (from the list below) that used this dataset. They then picked one or two of those for the **replication** part, before in the final part the built on that work to come up with some **extension** of the proposed models.

This page documents the results. (Incomplete, as of June 2023.)


#### Paper List

* De Vries, H., Strub, F., Chandar, S., Pietquin, O., Larochelle, H., & Courville, A. (2017). GuessWhat?! Visual object discovery through multi-modal dialogue. In CVPR 2017.
* Strub, F., de Vries, H., Mary, J., Piot, B., Courville, A., & Pietquin, O. (2017). End-to-end optimization of goal-driven and visually grounded dialogue systems. In IJCAI 2017. Retrieved from 
* Lee, S.-W., Heo, Y.-J., & Zhang, B.-T. (2018). Answerer in Questioner’s Mind: Information Theoretic Approach to Goal-Oriented Visual Dialog. In NeurIPS 2018 (pp. 1–15)
* Shekhar, R., Testoni, A., & Fernández, R. (2019). Jointly Learning to See , Ask , Decide when to Stop , and then GuessWhat. In 23rd Italian Conference on Computational Linguistics (CLiC-it).
* Shukla, P., Elmadjian, C., Sharan, R., Kulkarni, V., Turk, M., & Wang, W. Y. (2019). What Should I Ask? Using Conversationally Informative Rewards for Goal-Oriented Visual Dialog. In ACL 2019 (pp. 6442–6451)
* Suglia, A., Konstas, I., Vanzo, A., Bastianelli, E., Elliott, D., Frank, S., & Lemon, O. (2020). CompGuessWhat?!: A Multi-task Evaluation Framework for Grounded Language Learning. In ACL 2020 (pp. 7625–7641)
* Suglia, A., Vergari, A., Konstas, I., Bisk, Y., Bastianelli, E., Vanzo, A., & Lemon, O. (2020). Imagining Grounded Conceptual Representations from Perceptual Information in Situated Guessing Games. In Coling 2020 (pp. 1090–1102). 
* Mazuecos, M., Testoni, A., Bernardi, R., Benotti, L., & C, U. N. De. (2020). On the role of effective and referring questions in GuessWhat ?! In First Workshop on Advances in Language and Vision Research (pp. 19–25).
* Greco, C., Testoni, A., & Bernardi, R. (2020). Which Turn do Neural Models Exploit the Most to Solve GuessWhat ? Diving into the Dialogue History Encoding in Transformers and LSTMs. In Proceedings of the 4th Workshop on Natural Language for Artificial Intelligence (NL4AI 2020) (pp. 29–43).
* Testoni, A., & Bernardi, R. (2021). “I’ve Seen Things You People Wouldn’t Believe”: Hallucinating Entities in GuessWhat?! In ACL-IJCNLP 2021 SRW (pp. 101–111). 
* Suglia, A., Bisk, Y., Konstas, I., Vergari, A., Bastianelli, E., Vanzo, A., & Lemon, O. (2021). An Empirical Study on the Generalization Power of Neural Representations Learned via Visual Guessing Games. In EACL 2021 (pp. 2135–2144).
* Testoni, A., & Bernardi, R. (2021). Looking for Confirmations: An Effective and Human-Like Visual Dialogue Strategy. In EMNLP 2021
* Testoni, A., & Bernardi, R. (2021). The Interplay of Task Success and Dialogue Quality: An in-depth Evaluation in Task-Oriented Visual Dialogues. In EACL 2021 (pp. 2071–2082)
* Mogadala, A., Kalimuthu, M., & Klakow, D. (2021). Trends in integration of vision and language research: A survey of tasks, datasets, and methods. Journal of Artificial Intelligence Research, 71, 1183–1317. 
* Testoni, A., Greco, C., & Bernardi, R. (2022). Artificial Intelligence Models Do Not Ground Negation, Humans Do. GuessWhat?! Dialogues as a Case Study. Frontiers in Big Data, 4(January). 
* Zheng, D., Meng, F., Si, Q., Fan, H., Xu, Z., Zhou, J., … Wang, X. (2022). Spot the Difference: A Cooperative Object-Referring Game in Non-Perfectly Co-Observable Scene


#### Replication

Overall, this was an interesting experience for the students, giving them insights into what the typical state of research code repositories is, how quickly code (and dependencies!) age, and what the general state is of reproducability is in the field.

The students were encouraged to contact the original authors (sparingly), in cases where they could not recover information on their own. Overall, the original authors turned out to be a great help, and much thank is due to them!

Tamara Atanasoska (group A) wrote a blog post about her experiences: [A Successful Reproduction Project](https://www.holophrase.de/blog/the-making-of-a-sucessful-paper-reproduction-project).



##### Group A

Replicated paper:

* Greco, C., Testoni, A., & Bernardi, R. (2020). Which Turn do Neural Models Exploit the Most to Solve GuessWhat? Diving into the Dialogue History Encoding in Transformers and LSTMs. NL4AI@AI*IA

[Repository for the replication "Which Turn?"](https://github.com/TamaraAtanasoska/dialogue-history)

The students also contributed some fixes to the original repositories.


##### Group B

Replicated papers:

* Harm de Vries, Florian Strub, Sarath Chandar, Olivier
Pietquin, Hugo Larochelle, and Aaron Courville. 2016. Guesswhat?! visual object discovery through multi-modal dialogue.
* Florian Strub, Harm de Vries, Jérémie Mary, Bilal
Piot, Aaron Courville, and Olivier Pietquin. 2017.
End-to-end optimization of goal-driven and visually
grounded dialogue systems. In Proceedings of the
Twenty-Sixth International Joint Conference on Arti-
ficial Intelligence, IJCAI-17, pages 2765–2771.

[Repository for the replication "Baseline+RL"](https://github.com/AntJulRab/GuessWhat)


##### Group C

Replicated papers:

* Shekhar, R., Testoni, A., Fernández, R., & Bernardi, R. (2019). Jointly Learning to See, Ask, Decide when to Stop, and then GuessWhat. CLiC-it.

[Repository for the replication "Jointly"](https://github.com/yanweiser/Beyond-Task-Success-NAACL2019)



#### Extension

In the second part, the students went and tried to implement extensions or twists that occurred to them during the replication experiments.

Again, here is Tamara Atanasoska with a blog post about her group's experience: [Beyond paper reproduction: adding own experiments and reflections](https://www.holophrase.de/blog/beyond-paper-reproduction-adding-own-expriments-and-reflections).



