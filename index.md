## User Study Details

Having established confidence in the quality of modified posts by MathLatexEdit, we further investigated whether the recommended edits by MathLatexEdit can actually assist post editors especially those with little editing experience or expertise to successfully improve the quality of mathematics posts in practice. We conducted a user study  to further evaluate the usefulness of our model for assisting domain-specific edits.

Procedures for User Study

We randomly selected 50 posts to manually check its needed edits.
We asked an experienced research staff (not involved in the study) to edit these posts and collect corresponding edits as the groundtruth.
Note that these posts are selected outside our training corpus (i.e., date after May 1, 2020) to avoid potential bias.
Among 50 posts, 14 of them require math-related edits and we further select 6 needing different kinds of edits for this user study.

We recruited ten PhD students and research assistants from our school. 
According to pre-study background survey, all participants knew MathLatexEdit and are familiar with using LaTeX. 
The study involves two groups of five participants: the experimental group P_1, P_2, P_3, P_4, P_5 who start with the post editing with our tool, and the control group P_6, P_7, P_8, P_9, P_{10} who start from scratch. 
Each pair of participants  ⟨P_x, P_{x+5}⟩ 
have comparable experience in using \site and Latex so that the experimental group has similar expertise to the control group in total. 
Note that we do not asked participants to edit half of posts with our tool while the other half without assisting tool to avoid potential tool bias.

We gave participants detailed explanation of our tool for helping them understand the results.
Participants were required to edit posts with/without our tool and have up to 10 minutes for each post.
We recorded the time used to edit each post for every participant. 
After each post editing, participants were asked to rate how satisfied they are with their edits in five-point likert scale (1: not satisfied at all and 5: highly satisfied). 
Compared with the groundtruth, we calculated the precision and recall for these post edits.


Results of User Study

<img width="498" alt="Screen Shot 2021-04-10 at 12 52 06 PM" src="https://user-images.githubusercontent.com/24599364/114258772-958fc380-99fb-11eb-9e5b-84dade815c4b.png">

This table shows that participants in the experimental group spend less time (in average 378.6s versus 64s) in editing posts than the control group.
It indicates that our tool help editors save 82.85\% editing time.
In fact, the average time of the control group is underestimated, as 2 participants failed to complete at least one post within 10 minutes, which means that they may need more time in the real editing.
In contrast, all participants in the experimental group finished all post editing within 3 minutes.
With the help of our \tool, the experimental group also obtains higher (34.22\% and 25.02\%) precision and recall score in term of the edits.
The experimental group rates 80\% of their post edits as highly satisfactory (5 point), as opposed to 10\% highly satisfactory by the control group. 
On average, the satisfactory ratings for the experiment and control group are 4.78 versus 3.58.
We carried out the Mann-Whitney U test (specifically designed for small samples) to understand the significance of the differences between two groups.
It suggests that our tool can significantly help the experimental group edit posts faster (p - value < 0.01), with higher precision, recall and satisfactoriness score (p - value < 0.01).



We believed that better performance of the experimental group is due to the assistance of our \tool which give participants a reliable starting point for editing. 
Guided by the recommended post edits, participants can easily identify the issues and finish the edit.
83.3\% recommendations provided by our tool are directly accepted by the editors.
In experimental group, compared with posts where specifically one type of edit is required, the precision and recall scores are similar in posts where multiple edits are required, which demonstrates that our model has similar performance in these two cases.
Although there may be some mistakes in our tool's recommendation, participants can easily revise them. 
Without the help of edit recommendation, the control group have to read the post thoroughly and determine where issues are and solve these issues from scratch, which results in the longer edit time and less satisfactory edit results.
For example, some latexification edits within text like replacing x-y to $x-y$ are frequently missed in the control group.
The revision of complex latex formula such as $\langle x, x\rangle \cdot\langle y, y\rangle=|\langle x, y\rangle|^{2}+|x \times y|^{2}$ is more error-prone in control group.

## Examples of math-realted edits
#1 Missing $ inserted

f(x) = ax^2 + bx + c -> $ f(x) = ax^2 + bx + c $


2 Missing { token 

$ f_{1}^{\prime}, f_{2}^{\prime: Y \rightarrow Z^{X} $ -> f_{1}^{\prime}, f_{2}^{\prime}: Y \rightarrow Z^{X}


3 Missing ^ token 

$n(t)=48 e -20.6 t$ -> $n(t)=48 e^{-20.6 t}$


4 Mis-spelled tokens

f_{1}^{\prime}, f_{2}^{\prime}: Y \rightrrow Z^{X} -> f_{1}^{\prime}, f_{2}^{\prime}: Y \rightarrow Z^{X}


5 Converting natural language words into number

six -> $ 6 $


6 Converting natural language words into LaTeX tokens

root -> \sqrt

7 Wrongly used LaTeX tokens

$a^{\^}=\left(\mathbf{X}^{T} \mathbf{X}\right)^{-1} \mathbf{X}^{T} \vec{y}$ -> $\widehat{a}=\left(\mathbf{X}^{T} \mathbf{X}\right)^{-1} \mathbf{X}^{T} \vec{y}$

8 Transcribing screenshots into LaTeX formulas


