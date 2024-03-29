---
layout: home
permalink: /overview/
title: Seldonian \| Overview
---
<div class="container mt-4" align="center">
    <a href="{{ "/" | relative_url }}" class="btn btn-primary">&laquo; Previous: Home</a>
    <a href="{{ "/tutorials/" | relative_url }}" class="btn btn-primary">Next: Getting started &raquo;</a>
</div>

<!-- Main Container -->

<div class="container p-3 my-4 border" style="background-color: #f3f4fc;">
    <h3 class="mb-3">Overview</h3>
    <hr class="my-4" />
    <p>At this website, you will find a description of Seldonian algorithms as well as hands-on tutorials for implementing them with the Seldonian Toolkit. Use the navigation buttons at the top of the page to jump between pages, or click the links in the navbar at the top of the page. This page provides an overview of Seldonian algorithms, the Seldonian framework, and this software toolkit. If you are new to these topics, we recommend reading from the top down, but you are welcome to jump ahead using the links below. The content below is organized into the following topics:</p>
    <ol>
        <li>
            <a href="#need">The need for safe and fair machine learning</a>
        </li>
        <li>
            <a href="#probabilistic">The necessity of <i>probabilistic</i> guarantees</a>
        </li>
        <li>
            <a href="#algorithm">What is a Seldonian algorithm?</a>
        </li>
        <li>
            <a href="#framework">What is the Seldonian framework?</a>
        </li>
        <li>
            <a href="#toolkit">What is the Seldonian ML Toolkit?</a>
        </li>
        <li>
            <a href="#limitations">What are some limitations of this software toolkit?</a>
        </li>
    </ol>
</div>

<div class="container p-3 my-5 border" style="background-color: #f3f4fc;">
        <h3 class="mb-3" id="need">The need for safe and fair machine learning</h3>
        <hr class="my-4" />
        <p>
            Intelligent machines are everywhere, ranging from simple data analysis and pattern recognition tools used across the sciences, to complex systems that achieve superhuman performance on various tasks. Ensuring that these machines are well-behaved&mdash;that they do not, for example, harm humans or act in a racist or sexist way&mdash;is therefore not a hypothetical problem to be dealt with in the future, but a practical one that must be addressed today.
        </p>
        <p>
            Already, intelligent systems have caused harm. They have exhibited racist, sexist, and otherwise unfair behaviors that could reinforce existing social inequalities [<a href="https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing">1</a>, <a href="https://www.ted.com/talks/joy_buolamwini_how_i_m_fighting_bias_in_algorithms">2</a>, <a href="https://www.reuters.com/article/us-amazon-com-jobs-automation-insight/amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK08G">3</a>, <a href="https://www.scientificamerican.com/article/racial-bias-found-in-a-major-health-care-risk-algorithm/">4</a>, <a href="https://www.technologyreview.com/2019/04/05/1175/facebook-algorithm-discriminates-ai-bias/">5</a>, <a href="https://qz.com/1141122/google-translates-gender-bias-pairs-he-with-hardworking-and-she-with-lazy-and-other-examples/">6</a>, <a href="https://www.bloomberg.com/graphics/2016-amazon-same-day/">7</a>] and have produced dangerous behaviors [<a href="https://www.statnews.com/wp-content/uploads/2018/09/IBMs-Watson-recommended-unsafe-and-incorrect-cancer-treatments-STAT.pdf">1</a>], including those that have caused harm and death [<a href="https://en.wikipedia.org/wiki/Death_of_Elaine_Herzberg">1</a>, <a href="https://www.osha.gov/pls/imis/accidentsearch.search?sic=&amp;sicgroup=&amp;naics=&amp;acc_description=&amp;acc_abstract=&amp;acc_keyword=%22Robot%22&amp;inspnr=&amp;fatal=&amp;officetype=&amp;office=&amp;startmonth=&amp;startday=&amp;startyear=&amp;endmonth=&amp;endday=&amp;endyear=&amp;keyword_list=on&amp;p_start=40&amp;p_finish=45&amp;p_sort=&amp;p_desc=DESC&amp;p_direction=Prev&amp;p_show=40">2</a>, <a href="https://www.bbc.com/news/world-europe-62286017">3</a>]. 
        </p>
        <p>
            Safety is of primary importance in established engineering fields, due to historical disasters that motivated and shaped regulations, education, and professional practice. Though safety is of growing interest in the relatively nascent field of <i>artificial intelligence</i> (AI) and the subfield of <i>machine learning</i> (ML), the primary emphasis in these fields remains on increasing capabilities without sufficient concern for risks, and sometimes without proper scientific evaluation [<a href="https://arxiv.org/pdf/1902.03271.pdf">1</a>]. With the rapid increase of AI and ML applications, the safety and fairness of such systems must become a primary focus if we hope to avoid the historical disasters that shaped established engineering fields. 
        </p>
    </div>

<div class="container p-3 my-5 border" style="background-color: #f3f4fc;">
    <h3 class="mb-3" id="probabilistic">The necessity of <i>probabilistic</i> guarantees</h3>
    <hr class="my-4" />
    <p>
        There are two possible types of safety and fairness guarantees: <b>deterministic</b> and <b>probabilistic</b> (also called <i>stochastic</i>). Deterministic guarantees hold with certainty. A <i>deterministic</i> guarantee that an ML system will not give a medical treatment that results in a patient dying means that the ML system will <i>never</i> give a medical treatment that results in a patient dying. As another example, Asimov's <a href="https://en.wikipedia.org/wiki/Three_Laws_of_Robotics">three laws of robotics</a> are three proposed deterministic safety constraints for robots.
    </p>
    <p>
        Unlike deterministic guarantees, probabilistic guarantees only hold with some probability (typically a "high probability"). This high probability is usually written in math as \(1-\delta\), where \(\delta\in(0,1)\) is a (typically small) constant. Common values of \(\delta\) include 0.1, 0.05, and 0.01, resulting in guarantees that hold with probability 0.9, 0.95, and 0.99, respectively. So, a \(1-\delta\) probability guarantee that an ML system will not give a medical treatment that results in a patient dying means that the probability that the ML system gives a medical treatment that results in the patient dying will be at most \(\delta\).
    </p>
    <p>
        Obviously, we prefer deterministic guarantees over probabilistic ones. However, often deterministic guarantees are not possible, particularly when an ML system must use data when reasoning about a guarantee. To make this point clear, we provide two examples.
    </p>
    <ol>
        <li>
            <p>
                <b>Sepsis treatment.</b> <a href="https://en.wikipedia.org/wiki/Sepsis">Sepsis</a> is a potentially life-threatening condition that arises when the body's response to infection damages its own tissues. It is responsible for roughly <a href="https://www.who.int/news-room/fact-sheets/detail/sepsis">one in five deaths worldwide</a>. When a new strategy for treating sepsis is proposed (by a human or a machine), we should ensure that it is safe before it is used. Ideally, we would like a deterministic guarantee that says "If the new strategy is used, fewer people will die from sepsis." However, such a guarantee is not possible. Instead, trials are run using computer simulations, other animals, and eventually small groups of people in controlled scientific studies called <i>clinical trials</i>. In such a scientific study, one group of people would be treated using the new strategy, and another group would be treated using the current strategy. If more people who were treated with the new strategy survive, then we might aim to conclude that the new strategy is better. 
            </p>
            <p>
                However, we must be careful not to jump to conclusions prematurely. In the United States, clinical trials begin with roughly 20&#8211;80 human participants (see "What are the four phases of clinical trials?" <a href="https://www.nia.nih.gov/health/what-are-clinical-trials-and-studies">here</a>). What if the new strategy "got lucky," and happened to be tested on the people who would have survived even with the older treatment strategy? In this case, even if the new strategy is significantly worse and would result in far more deaths from sepsis if it replaced the current strategy, it would still appear to be better in the initial clinical trial. So, though we have evidence supporting the conclusion that the new strategy is actually better, we cannot yet be certain of this conclusion. If the initial trial is successful, we might conduct trials with more people to  gain more certainty and ensure that the new strategy didn't just "get lucky." In the United States, there are four phases of clinical trials that build up to trials with several hundred to about 3,000 people.
            </p>
            <p>
                Imagine that the new strategy was again effective in subsequent trials with a few thousand people. We <i>still</i> cannot be completely certain that the new strategy will be better. It could still be that the new strategy again "got lucky," and that all of the people treated with the new strategy would have survived if treated with the old one. However, with so many people in the study, the new strategy would have to have been <i>very</i> lucky! Notice that no matter how many people are treated with the new strategy, we can always make this argument. So, although we can never be completely certain that the new strategy is actually better, as we obtain increasing amounts of data, we can become increasingly certain about our conclusion that it is better. At some point, we are so certain that we are willing to accept the conclusion. This raises the question: how much data do we need (how many people do we need to experiment with) and how large of a difference in survival rate must we see before we can conclude that the new strategy is better with a reasonable amount of certainty?
            </p>
            <p>
                This question has been heavily studied by mathematicians and statisticians. Given the results of a (carefully constructed) study, we can use statistical tools to obtain a confidence interval for the percent of people who will survive if the new strategy is used. In this case, a \(1-\delta\) <i>confidence interval</i> \((l,u)\) indicates that with probability of at least \(1-\delta\) the true percent of people who will survive if the new strategy is used is between \(l\) and \(u\) percent. If \(1-\delta\) is sufficiently large and \(l\) is also sufficiently large (e.g., larger than the percent of people who survive when using the old strategy), then we can accept the conclusion that the new strategy is better and that using the new strategy for other people would be a responsible choice. As we obtain more and more data, the <i>width</i> of the confidence interval (that is, \(u-l\)) typically shrinks as we become increasingly certain about the actual percentage of people who will survive if the new strategy is used.
            </p>
            <p>
                In conclusion, notice that here a deterministic guarantee is not possible: We cannot know with absolute certainty that the new strategy for treating sepsis will be an improvement upon the old strategy. However, using data and statistical tools, we can characterize our certainty that the new strategy is superior. That is, we can obtain a \(1-\delta\) confidence guarantee that the new strategy is superior, and with enough data, \(1-\delta\) can become large enough that we are willing to trust the conclusion. This is an example of a probabilistic safety guarantee: a \(1-\delta\) confidence guarantee that the new strategy will be safe.
            </p>
        </li>
        <li>
            <p>
                <b>Loan approval.</b> One commonly discussed use of machine learning is to determine which loan applications should be approved. For this application, it is important that machine learning algorithms do not exhibit racist, sexist, or other such discriminatory behavior. For example, a machine learning algorithm that only approves loans for people of one type or which makes more accurate predictions for people of one type might be considered unfair and could reinforce existing social inequalities.
            </p>
            <p>
                One common misconception is that machine learning algorithms that are designed to optimize for the accuracy of their predictions would not produce unfair predictions, since they have no incentive to be unfair. This is, unfortunately, not the case. Machine learning algorithms tend to make unfair predictions unless algorithms are specifically designed to ensure that they are in some way "fair." Though a complete description of this issue is beyond the scope of this document, one core underlying problem is that fairness constraints are typically not perfectly aligned with optimizing for accuracy (or any other standard primary objective). As an analogy, asking a machine learning system to maximize some measure of the accuracy of its predictions while ensuring fairness is like asking you to run down the sidewalk as fast as you can while not stepping on any cracks. While you can run fast while dodging cracks, sometimes you need to slightly modify where your foot lands to avoid a crack, resulting in a slight slowdown. Similarly, the machine learning system may need to slightly modify its predictions to remain fair, resulting in a (typically) slight reduction in accuracy. So, just like how you would tend to step on cracks when only told to run as fast as possible, machine learning algorithms tend to produce unfair predictions when only told to maximize the accuracy of their predictions, since in both cases the primary objective (run fast / make accurate predictions) is not perfectly aligned with the constraint (avoid cracks / make fair predictions). A clear and easily reproduced example of how this happens when considering fairness of machine learning algorithms is provided in Section 2 in the supplementary materials of our <i>Science</i> paper. To access this document, go <a href="http://aisafety.cs.umass.edu/paper.html">here</a>, click "Open Access Link", then on the left click "Supplementary Material", then under "Resources" click the "Download" button. 
            </p>
            <p>
                So, for this example we might aim to ensure that the predictions of a machine learning system enforce some notion of fairness. To do so, we must precisely define what it means for predictions to be fair. This has turned out to be an exceptionally difficult task. Not only are there dozens of different definitions of fairness (see <a href="https://fairware.cs.umass.edu/papers/Verma.pdf">this</a> paper for some common definitions from 2018), but often these definitions are <i>conflicting</i>. That is, often it is not possible for any system (human or machine) to simultaneously satisfy two desired definitions of fairness. This is an issue we ran into when using machine learning to predict students' GPAs in college from their application materials. <i>Any</i> system for making these predictions (in the setting that we studied, which included self-reported binary gender) must either A) produce higher predictions on average for students of one gender, or B) tend to overpredict for one gender and underpredict for the other (particularly bad systems could overpredict for both or underpredict for both, but it would still overpredict or underpredict significantly more for one gender). In this case, we <i>must</i> view either (A) or (B) as being acceptable and not unfair, even though our intuition might suggest that both are unfair.
            </p>
            <p>
                Before continuing, we want to make one point abundantly clear: We (the authors of the <i>Science</i> paper), and we (the creators of this software toolkit) are not endorsing or promoting a specific definition of fairness or safety for any application. Instead, our goal is to give data scientists the ability to select the definitions of safety and fairness that are appropriate for the tasks they are faced with. When showing how our system can be used, we use examples of possible definitions of safety and fairness, but these are merely illustrative <i>examples</i>. Moreover, they are not examples of what the "right" definition of safety or fairness is for the problem being studied; rather, they are examples of how someone could enforce one definition of safety or fairness if that is the one that they selected. The appropriate definition of fairness for the loan approval application should not be chosen by individual computer scientists, but by a community of social scientists, fair-machine-learning researchers (to provide insight into what is and is not possible), domain experts, representatives of the relevant communities, and perhaps even lawmakers. 
            </p>
            <p>
                For now, imagine that we aim to ensure that the machine learning system is "fair" in that for people who would actually repay the loan if it were approved, the system is not more likely to reject their application if they are of one type (e.g., one race or gender) than another. At first glance, it might seem like this is something that we could ensure deterministically, for example, by ensuring that the machine learning system cannot look at the applicant's race, gender, or any other protected attribute. However, this is not the case because race and gender influence almost every piece of information about the person in ways that are subtle and challenging to model. For example, race and gender can be correlated with everything from zip code to income to undergraduate institution. Machine learning systems can therefore still produce unfair behavior (with our chosen definition of fairness) even without explicitly considering the applicant's race or gender. In fact, for most fairness definitions it is critical that fair machine learning algorithms have access to protected attributes like race and gender in order to ensure that they are fair!
            </p>
            <p>
                How then can we ensure that a loan system is fair? One way is to use available data about whether people repaid loans in the past. We can use our machine learning system to predict whether these people would repay their loans and then  compare the system's predictions to what actually happened. If we then only consider the data from people who <i>did</i> repay their loans, we can check how often the system predicts that someone will not repay the loan given that they are of each type of interest (race, gender, etc.). If these rates are significantly different, then we might conclude that the system is unfair. 
            </p>
            <p>
                However, this runs into the exact same issue we faced in the sepsis example! What if the system appears to be perfectly fair on the data that we use to test it, but this is because it "got lucky" and happened to be shown applicants for which it makes fair predictions? Given enough data, it would have to be extremely lucky, and so we might aim to use enough data to ensure that we are sufficiently certain that the system is actually fair (and not just that it happened to get lucky in terms of the data used to test it). This can be achieved using the same statistical techniques described in the sepsis example, providing a \(1-\delta\) confidence guarantee that the machine learning system is fair. Though we can never be absolutely certain that the system is fair, with sufficient data we should be able to obtain sufficiently large confidence for the machine learning system to be responsibly used in the future.
            </p>
        </li>
    </ol>
    In summary, most safety and fairness guarantees cannot be ensured <i>deterministically</i>. However, fairness and safety can usually be tested using data. These tests can sometimes be wrong, but the chance that they are wrong tends to shrink as we obtain more and more data. Using statistical techniques, we can quantify the probability that these tests will cause us to draw the wrong conclusion, and so we can obtain probabilistic guarantees about safety and fairness. That is, guarantees that hold with probability at least \(1-\delta\). Returning to our earlier example of Asimov's three laws of robotics, the first law states that "A robot may not injure a human being, or through inaction, allow a human being to come to harm." Notice that this law is impossible for any system to satisfy, as nothing (no human or machine) can be absolutely certain that none of its actions will cause a human to be harmed in the future. Instead, real safety guarantees of this sort must be probabilistic, requiring the robot to have sufficient confidence that its actions will not cause harm to a human.
</div>

<div class="container p-3 my-5 border" style="background-color: #f3f4fc;">
    <h3 class="mb-3" id="algorithm">What is a Seldonian algorithm?</h3>
    <hr class="my-4" />
    <p>Seldonian algorithms are machine learning algorithms that provide high-confidence guarantees that they will not produce undesirable behavior. To make this statement more precise, we will define notation and then convert the English statement into a mathematical statement.</p>
    Notation:
    <ul>
        <li>\(\mathcal D\) is the set of all possible inputs (data sets) to the algorithm. If a machine learning algorithm takes any other inputs beyond the data set (like random numbers), this is also viewed as part of \(\mathcal D\), though for simplicity one can initially think of each item in the set \(\mathcal D\) as just a data set.</li>
        <li>\(D\) is the data set given as input to the algorithm, which we view as a <a href="https://en.wikipedia.org/wiki/Random_variable">random variable</a>. In subsequent statements of probability, \(D\) is the only source of randomness.</li>
        <li> \(\Theta\) is the set of all possible outputs of the algorithm, each of which we refer to as a <em>solution</em> \(\theta \in \Theta\). For supervised learning problems, \(\theta\) corresponds to the weights or parameters of the model (e.g., weights of the learned neural network). For reinforcement learning problems, \(\theta\) corresponds to the weights or parameters of the policy.</li>
        <li>\(a:\mathcal D \to \Theta\) is a machine learning algorithm, which takes a data set as input and returns a solution. That is, \(a(D)\) is the solution (an element of \(\Theta\)) output by the algorithm when run on input \(D\). Recall that any random numbers required by the algorithm should be included in \(D\).</li>
        <li>\(\mathcal A\) is the set of all possible machine learning algorithms.</li>
        <li>\(f:\mathcal A \to \mathbb R\) is the <em>objective function</em> of the algorithm designer. The goal of the designer is to find an algorithm that maximizes \(f\), subject to the behavioral constraints.</li>
        <li>\(n\) is the number of <em>behavioral constraints</em>.</li>
        <li>\((g_i,\delta_i)_{i=1}^n\) is a set of \(n\) behavioral constraints, each of which contains a <em>constraint function</em> \(g_i:\Theta\to\mathbb R\) and a <em>confidence level</em> \(\delta_i\).
            <ul>
                <li>
                    The constraint function measures undesirable behavior: we say that \(\theta \in \Theta\) produces undesirable behavior if and only if \(g_i(\theta) > 0\). In more colloquial terms, we might say that \(g_i(\theta) \leq 0\) means that \(\theta\) is "safe" or "fair."
                    <ul>
                        <li>For the sepsis treatment example above, \(\theta\) specifies a new treatment strategy, and we might define \(g_i\) such that \(g_i(\theta) = \Pr(\text{survive}|\text{current treatment strategy}) - \Pr(\text{survive}|\theta)\). Hence, \(g_i(\theta) > 0\) means that the new treatment strategy specified by \(\theta\) decreases the probability a randomly selected patient will survive. Later, in the tutorials, we show how a constraint of this form can be specified.</li>
                        <li>For the loan approval example above, a <i>false positive</i> occurs when the machine learning system predicts that a person would not repay a loan when in fact they would. Our <i>example</i> fairness definition requires the false positive rates to be similar for people of different types (here we assume two types: A and B). So, we might define \(g_i\) such that \(g_i(\theta) = \left |\text{false positive rate given type A} - \text{false positive rate given type B}\right | - \epsilon\), where \(|\cdot|\) denotes absolute value and \(\epsilon\) is a constant that specifies the maximum allowed difference in false positive rates. With this definition, \(g_i(\theta)>0\) means that the difference in false positive rates when using the machine learning model with parameters \(\theta\) is more than \(\epsilon\).</li>
                    </ul>
                </li>
                <li>The confidence level specifies the maximum probability that the algorithm can return a solution \(\theta\) where \(g_i(\theta)>0\).</li>
            </ul>
        </li>
    </ul>
    <p>
        A <em>Seldonian algorithm</em> ensures that for all \(i \in \{1,2,\dotsc,n\}\):
        $$\Pr(g_i(a(D))\leq 0)\geq 1-\delta_i.$$
        That is, a Seldonian algorithm \(a\) ensures that for each of the \(n\) behavioral constraints, the probability that it outputs a solution that produces undesirable behavior as defined by \(g_i\) is at most \(\delta_i\). In other words, a Seldonian algorithm \(a\) returns, with high probability, a solution that does not break any of the behavioral constraints. An algorithm is <em>quasi-Seldonian</em> if it relies on reasonable but possibly false assumptions regarding the data being analyzed. These assumptions often appeal, for instance, to the central limit theorem, common in scientific research. More precisely, Seldonian algorithms often rely on concentration inequalities like Hoeffding's inequality (which makes no distributional assumptions other than boundedness), while quasi-Seldonian algorithms often rely on confidence intervals from Student's \(t\)-test or Efron's bootstrap methods.
    </p>
    <p>
        As discussed in the next section, the data scientist applying a Seldonian algorithm is free to select the appropriate definition of undesirable behavior for the application at hand. One consequence of giving the data scientist this freedom is that they can ask the impossible. That is, they can ask the algorithm to satisfy constraints that are impossible to satisfy (such as conflicting fairness constraints), or they can ask for very strong and very high-confidence constraints given very little data. In these cases, a Seldonian algorithm needs a way to say, "I cannot do that." This capability is provided by including a special solution, "No Solution Found" (NSF), within \(\Theta\) (the set of possible solutions) and by defining \(g(\text{NSF})=0\) so that it is always safe for a Seldonian algorithm to return NSF, alerting the data scientist that it was unable satisfy the provided constraints.
    </p>
</div>

<div class="container p-3 my-5 border" style="background-color: #f3f4fc;">
    <h3 class="mb-3" id="framework">What is the Seldonian framework?</h3>
    <hr class="my-4" />
    <p>
        The Seldonian <i>framework</i> provides guidance for the creation of useful Seldonian algorithms. The most critical points are:
    </p>
    <ul>
        <li>The user of the algorithm (typically a data scientist) should be able to select the definition of undesirable behavior. This means that the user of the algorithm must be able to choose the appropriate definition of \(g_i\) for their application.</li>
        <li>The user of the algorithm should also be able to select the confidence level \(\delta_i\) that is appropriate for their application.</li>
        <li>The designer of a Seldonian algorithm should therefore provide both A) the Seldonian algorithm itself, and B) an <i>interface</i> that the user can use to define \(g_i\) and \(\delta_i\) for each \(i\). The framework does not have any further requirements on the form of the interface. Examples of interfaces can include dropdown menus that allow users to select from multiple common definitions of fairness, systems that allow users to write equations that describe what it means for a solution to be safe or fair, and systems that allow users to label data (episodes in the reinforcement learning setting) to indicate whether undesirable behavior was present or not. Future interfaces could include natural language conversations with the user or the use of inverse reinforcement learning to infer the user's objective.</li>
        <li>The designer of the algorithm should strive to make their algorithm and interface compatible with as many definitions of safety and fairness as possible. This is important because the designer does not know what problems their algorithm will be applied to, and therefore does not know the appropriate definitions of safety and fairness.</li>
        <li>The designer of the algorithm should make their interface as simple to use as possible. This is important because machine learning algorithms are already used by people, including children, who are not experts in machine learning.</li>
    </ul>
</div>

<div class="container p-3 my-4 border" style="background-color: #f3f4fc;">
    <h3 class="mb-3" id="toolkit">What is the Seldonian ML Toolkit?</h3>
    <hr class="my-4" />
    <p>
        We developed the Seldonian Toolkit to provide:
        <ul>
            <li><b>Basic Seldonian algorithms and interfaces.</b> The <code>Engine</code> library provides a basic Seldonian algorithm that can be used for parametric machine learning models (future versions of the toolkit may support non parametric methods). This includes regression, classification (binary and multiclass), and offline (batch) reinforcement learning. It also provides basic interfaces for communicating definitions of undesirable behavior to these algorithms, along with tutorials showing how the <code>Engine</code> and interfaces can be used.</li>
            <li><b>Tools to facilitate the development of new Seldonian algorithms.</b> The modular design of the <code>Engine</code> library was chosen so that researchers can easily swap out components with new methods. Though the current Seldonian algorithms are quite effective, there remains room for improvement, and the library is designed to enable researchers to develop these improvements.</li>
            <li><b>Tools to evaluate the performance of Seldonian algorithms.</b> Whether you are a data scientist considering using Seldonian algorithms for your application, or a researcher trying to determine whether your algorithmic improvement actually provides better performance, you will want tools to quickly and easily evaluate how effective the algorithms are. This includes evaluating A) how much data the algorithm requires, B) how often the algorithm produces undesirable behavior (how often $g_i(a(D)) > 0)$, and C) how good the solutions found are in terms of the primary objective (the primary loss function). The Seldonian Toolkit therefore contains an <code>Experiments</code> library that makes it easy to evaluate Seldonian algorithms (and any other algorithms you would like to compare against!) on many existing problems as well as new problems and data sets that you provide.</li>
        </ul>
    </p>
    <p>
       To get started using the Seldonian Toolkit, we recommend starting with the <a href="{{ "/tutorials/" | relative_url}}">tutorials</a>. These start with how to install the libraries in the Seldonian Toolkit (if you already have Python, it should be a simple pip install command!), and then provide examples of how the libraries can be used to solve real problems of interest.
    </p>
</div>

<div class="container p-3 my-5 border" style="background-color: #f3f4fc;">
        <h3 class="mb-3" id="limitations">What are some limitations of this software toolkit?</h3>
        <hr class="my-4" />
        <p>
            This toolkit, and Seldonian algorithms in general, have important limitations, several of which are listed below.
        </p>
        <ul>
            <li>Seldonian algorithms allow users to define "undesirable behavior" (unsafe behavior) for the problem at hand, and then ensure that the probability they produce this undesirable behavior is sufficiently low. This results in machine learning algorithms that are more obedient. However, this does <b>not</b> address other AI safety problems. For example, if a user does not consider a possible safety risk and therefore does not think to add a safety constraint to their system, Seldonian algorithms will not automatically determine the possible safety risk or notify the user.</li>
            <li>Seldonian algorithms return "No Solution Found" (NSF) to indicate that they were unable to satisfy the safety constraints provided by the user (either because they did not have enough data or because the constraints are impossible to satisfy simultaneously). Seldonian algorithms in future versions of this toolkit may provide the user of the algorithm with a prediction of which of these was the cause of NSF being returned (and perhaps how much more data would be required if the limitation was the amount of training data). This feature is not present in the current toolkit. Though the ability to return NSF is a direct consequence of providing the user of the algorithm with the freedom to select the appropriate definition of safety or fairness for their application at hand (allowing them to ask for the impossible), it also means that Seldonian algorithms are limited to applications where it is ok for the algorithm to return NSF. This is typically the case when ML is used to improve upon some existing solution, so that NSF would correspond to continuing to use the current system. For potential applications where there is not an existing solution that can be used if NSF is returned, Seldonian algorithms may not be appropriate.</li>
            <li>All existing Seldonian algorithms are batch algorithms. That is, they take a data set as input and produce as output a trained model (called a "policy" in the reinforcement learning setting). This differs from online or streaming algorithms, which continually refine and improve ML models as more data becomes available. Seldonian algorithms ensure that the probability that they produce undesirable behavior when run will be at most \(1-\delta\) (where \(\delta\) is chosen by the user of the algorithm). If a Seldonian algorithm were to be run multiple times (as a naïve strategy for handling the online setting where more data may become available over time), the probability of undesirable behavior occurring would compound across runs, possibly resulting in unacceptable risk. </li>
            <li>The current version of the software toolkit supports <i>parametric</i> machine learning. Nonparametric models such as random forest and support vector machines are not currently supported, though we may consider supporting them in future versions.</li>
            <li>Often, the distribution of training data does not precisely match the distribution of data that an algorithm will face in the future. For example, training data collected in the past may not account for shifting trends over time (like seasonality). Similarly, data collected by an autonomous vehicle that undergoes wear and tear may not accurately represent the vehicle's future degraded performance. As another example, data collected in one city will not accurately capture the demographics of a different city, meaning that a model that is fair when trained on data from Los Angeles may not be fair when applied to a problem where it makes decisions for people in New York. Prof. Thomas and collaborators are actively working on methods to handle these types of "distributional shift," "covariate shift," "demographic shift," and general non-stationarity (<a href="https://people.cs.umass.edu/~pthomas/papers/Chandak2020b.pdf">1</a>, <a href="https://people.cs.umass.edu/~pthomas/papers/Giguere2022.pdf">2</a>). However, these advances are not in the existing toolkit. The safety guarantees of the current toolkit assume that the learned model will be deployed to data that comes from the same distribution that the training data was sampled from. Though this assumption is extremely common in machine learning, when it is false, the Seldonian algorithms in this toolkit do not provide high-confidence safety guarantees.</li>
            <li>Seldonian algorithms are <i>not</i> inherently robust to corrupted data. That is, if an adversary can corrupt even a few points in a data set, they can cause Seldonian algorithms to be extremely <i>unsafe</i> (particularly in the reinforcement learning setting). Though this issue has been studied, and techniques exist for making Seldonian algorithms more robust to (adversarially) corrupted data (<a href="https://people.cs.umass.edu/~pthomas/papers/Ozisik2020.pdf">1</a>), these extensions are not included in the current Seldonian Toolkit.</li>
            <li>
                <p>
                    If a Seldonian algorithm returns No Solution Found (NSF), a user might be tempted to tweak settings of the algorithm and try running it again. This raises a potential issue. As an analogy, consider a study testing a new drug by giving a placebo to a control group and the new drug to the other participants. After gathering data from this study, one might test whether people in the control group tend to have more headaches. If this is not the case, one might test whether the people in the control group had more fevers. One could continue testing hypotheses until one is found where the drug appears to have an effect. Even if the new drug has no effect (it was also a placebo), eventually one will find some property that happens to be more prevalent in the control group (say, people in the control group were in fewer car accidents). This isn't because the new drug actually influenced the frequency of car accidents, but rather is because the people in the control group happened to have fewer accidents. This is a common example of the <a href="https://en.wikipedia.org/wiki/Multiple_comparisons_problem">multiple comparisons problem</a>, showing why only one hypothesis (does the new drug reduce the frequency of headaches?) should be tested using a given data set. If multiple hypotheses are tested, then the appropriate statistical tools must be used to account for this practice. One can think of the "safety test" mechanism as running such a hypothesis test (testing whether the candidate solution is safe), and so this same issue arises. The key point is to recognize that a Seldonian algorithm's high-probability guarantee applies to a single run of the algorithm.
                </p>
                <p>
            If the algorithm produces undesirable behavior with probability at most \(\delta\), and you run the algorithm \(k\) times in a row, <a href="https://en.wikipedia.org/wiki/Boole%27s_inequality">Boole's inequality</a> tells us that the probability that it produces undesirable behavior can be as large as \(\operatorname{min}(1,k\delta)\) (if separate independent data sets are used for the runs, the failure events would be statistically independent, bringing the probability of undesirable behavior down to $1-(1-\delta)^k$). For example, if \(\delta=0.1\), the algorithm should produce unsafe solutions at most \(10\%\) of the time. However, if you run the algorithm two times, the probability that it produces unsafe behavior could be as high as \(20\%\) of the time.
            </p> </li>
        </ul>
</div>

<div class="container" align="center">
    <a href="{{ "/" | relative_url }}" class="btn btn-primary">&laquo; Previous: Home</a>
    <a href="{{ "/tutorials/" | relative_url }}" class="btn btn-primary">Next: Tutorials &raquo;</a>
</div>
