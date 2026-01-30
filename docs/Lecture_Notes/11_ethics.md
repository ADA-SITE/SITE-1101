# 11. Ethics, Security, and Logical Reasoning

:material-account: Nilufar Ismayilova, Rumiyya Alili, Ismayil Shahaliyev  
:material-calendar: Nov 29 2025 :material-calendar-edit: Jan 31, 2026

## Space Shuttle _Challenger_ Disaster

> The most dangerous phrase in the language is: "We've always done it this way" ~ [_Grace Hopper_](https://en.wikipedia.org/wiki/Grace_Hopper)

One of the most important historical examples used to discuss ethics in engineering and information systems is the [Space Shuttle _Challenger_ disaster](https://en.wikipedia.org/wiki/Space_Shuttle_Challenger_disaster) (1986). The _Challenger_ shuttle broke apart shortly after launch, resulting in the deaths of all seven crew members. 

<figure class="w80">
  <img src="../../assets/images/lecture11/challenger_crew.jpg" alt="STS-51-L Challenger Shuttle Crew">
  <figcaption>
    STS-51-L crew: (back) Onizuka, McAuliffe, Jarvis, Resnik; (front) Smith, Scobee, McNair. By NASA - <a rel="nofollow" class="external text" href="https://spaceflight.nasa.gov/gallery/images/shuttle/sts-51l/html/s85-44253.html">NASA Human Space Flight Gallery</a> (<a rel="nofollow" class="external text" href="https://spaceflight.nasa.gov/gallery/images/shuttle/sts-51l/hires/s85-44253.jpg">image link</a>), Public Domain, <a href="https://commons.wikimedia.org/w/index.php?curid=181762">Link</a>
  </figcaption>
</figure>

Investigations later showed that the disaster was not caused by a single technical failure alone, but by a combination of engineering, organizational, and ethical failures. A critical technical issue involved [O-ring](https://en.wikipedia.org/wiki/O-ring) seals in the solid rocket boosters.

These O-rings were responsible for preventing hot combustion gases from escaping during launch. This design created a [single point of failure](https://en.wikipedia.org/wiki/Single_point_of_failure): if the O-ring did not seal properly, there was no additional system to contain the pressure. One component became responsible for the safety of the entire mission.

Before the _Challenger_ launch, engineers from _Morton Thiokol_ analyzed data from previous shuttle flights and noticed that the O-rings performed worse at lower temperatures. During a pre-launch meeting, engineers explicitly recommended delaying the launch because the temperature on launch day was far below any previous flight conditions. However, NASA managers were under pressure to maintain the launch schedule and asked engineers to provide proof that the launch would fail, instead of proof that it was unsafe. Communication problems, schedule pressure, and fear of delaying the mission played a major role in ignoring these warnings.


<figure class="w60 float-left">
  <img src="../../assets/images/lecture11/oring.jpg" alt="SRB field joint O-ring Challenger Shuttle">
  <figcaption>
    Cross-sectional diagram of the original SRB field joint. The top end of the lower rocket segment has a deep U-shaped cavity, or clevis, along its circumference. The bottom end of the top segment extends to form a tang that fits snugly into the clevis of the bottom segment. Two parallel grooves near the top of the clevis inner branch hold ~20 foot (6 meter) diameter O-rings that seal the gap between the tang and the clevis, keeping hot gases out of the gap. By Rogers Commission into the loss of the Space Shuttle Challenger - <a rel="nofollow" class="external free" href="https://history.nasa.gov/rogersrep/v1ch4.htm">http://history.nasa.gov/rogersrep/v1ch4.htm</a>, Public Domain, <a href="https://commons.wikimedia.org/w/index.php?curid=107789463">Link</a>
  </figcaption>
</figure>

This phenomenon is called [normalization of deviance.](https://en.wikipedia.org/wiki/Normalization_of_deviance) NASA had seen O-ring erosion in earlier flights but accepted it as "normal" because flights had not failed yet. When warning signs appear repeatedly without immediate catastrophic consequences, organizations can begin to accept abnormal and risky conditions as normal. This creates a culture where critical safety concerns are downplayed, and each successful outcome despite the warnings reinforces the dangerous belief that "it will be fine this time too."

!!! success "Exercise"
    Identify the key ethical mistakes that occurred in the _Challenger_ shuttle case and explain what engineers and decision-makers should have done differently to ensure public safety and proper handling of technical concerns.

## Trolley Problem

Ethical questions in technology (and life) often involve difficult trade-offs, where every available option leads to some form of harm or disadvantage. One well-known thought experiment used to explore moral reasoning in such situations is the [trolley problem](https://en.wikipedia.org/wiki/Trolley_problem). In its basic form, a runaway trolley is heading toward several people standing on a track. You have the option to pull a lever that redirects the trolley onto another track, where it will harm only one person instead. The dilemma forces individuals to choose between actively causing harm to one person or passively allowing greater harm to occur.

<figure class="w100">
  <img src="../../assets/images/lecture11/trolley.svg" alt="Trolley Problem">
  <figcaption>
    The trolley problem presents a dilemma: is it preferable to pull the lever to divert the runaway trolley onto the side track with just one person? By <a href="//commons.wikimedia.org/wiki/File:Trolley_problem.png" title="File:Trolley problem.png">Original: </a> <a href="//commons.wikimedia.org/wiki/User:McGeddon" class="mw-redirect" title="User:McGeddon">McGeddon</a> Vector: <a href="//commons.wikimedia.org/wiki/User:Zapyon" title="User:Zapyon">Zapyon</a> - This SVG diagram includes elements from this icon:, <a href="https://creativecommons.org/licenses/by-sa/4.0" title="Creative Commons Attribution-Share Alike 4.0">CC BY-SA 4.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=67107784">Link</a>
  </figcaption>
</figure>


The trolley problem has no simple or universally correct answer. Instead, it highlights how ethical decisions often involve conflicting values, such as minimizing harm, respecting individual rights, and determining responsibility for outcomes. Some people focus on the consequences of actions and choose the option that saves the most lives, while others believe it is morally wrong to actively cause harm, even if it leads to a better overall outcome. These different responses demonstrate how ethical reasoning can vary depending on personal values, cultural background, and situational context.

[Consequentialism](https://plato.stanford.edu/entries/consequentialism/) judges decisions by their outcomes. A consequentialist, especially a utilitarian, might argue that diverting the trolley is morally right because it reduces the total loss of life. The focus is on maximizing overall well-being, even if doing so involves harming an individual.

[Deontological ethics](https://plato.stanford.edu/entries/ethics-deontological/) evaluates actions based on rules, duties, and respect for individual rights. From this view, deliberately causing a person's death - by pulling the lever or pushing someone - is morally wrong regardless of the positive result. The right action is determined not by consequences but by adherence to moral principles.

The scenario also engages the [doctrine of double effect](https://plato.stanford.edu/entries/double-effect/), which distinguishes between harm that is foreseen but unintended and harm that is used as a means to an end. Saving five lives while unintentionally causing death may be seen differently from intentionally killing one person to save five. Another important idea is agent responsibility: whether moral judgment depends on what we do directly versus what we merely allow to happen. Some argue that actively intervening and causing harm makes us more morally responsible than if harm occurs without our direct action.

In the context of information systems, artificial intelligence, and automation, similar dilemmas arise in real-world system design. For example, engineers developing autonomous vehicles must consider how a system should behave in unavoidable accident scenarios. Should the system prioritize the safety of passengers inside the vehicle, pedestrians outside, or follow traffic laws strictly regardless of the outcome? Likewise, algorithmic systems may face ethical trade-offs between maximizing efficiency and fairness, such as optimizing delivery routes at the cost of increased pollution in certain neighborhoods or using automated decision systems that unintentionally disadvantage specific groups.

!!! note
    Consider a self-driving car approaching an unavoidable accident. If the car continues forward, it will collide with several pedestrians crossing the street illegally. If it swerves, it will crash into a barrier, putting the passenger at serious risk. Engineers must decide how the system should behave in this situation. Should the algorithm prioritize minimizing total harm, protecting the passenger, or following traffic laws strictly? Different answers lead to different ethical outcomes. What would you choose? Why?

## Deduction and Induction

Logical reasoning plays a central role in engineering, information systems, and ethical decision-making. From designing algorithms to evaluating system security and making responsible choices, professionals rely on logic to analyze problems and justify conclusions. Many of the foundational ideas behind logical reasoning were first systematized by [Aristotle](https://plato.stanford.edu/entries/aristotle/), who is often regarded as the founder of [formal logic](https://en.wikipedia.org/wiki/Logic#Formal_logic). His work established structured methods for evaluating arguments and distinguishing valid reasoning from flawed or misleading conclusions.

Aristotle introduced [deductive logic](https://en.wikipedia.org/wiki/Deductive_reasoning), particularly through the concept of the [syllogism](https://en.wikipedia.org/wiki/Syllogism), which is a structured form of argument consisting of _premises_ that lead to a necessary conclusion. In deductive reasoning, the argument moves from general principles to specific cases. If the premises are true and the logical structure is valid, the conclusion must also be true. This type of reasoning is especially important in system design and formal verification, where **certainty** and correctness are required.

!!! note
    Below is perhaps the most famous syllogism:
    
    _All humans are mortal.<br>
    Socrates is a human.<br>
    Therefore, Socrates is mortal._

    The conclusion (third line) follows logically from the two premises. The structure correctly moves from a general rule to a specific case.

!!! success "Exercise"
    Is the argument below logically sound? If not, identify what is wrong with its reasoning.

    _All secure systems require authentication.  
    This system requires authentication.  
    Therefore, this system is secure._

In contrast, [inductive reasoning](https://en.wikipedia.org/wiki/Inductive_reasoning) moves from specific observations to broader generalizations. Rather than guaranteeing truth, induction produces conclusions that are **probable** or **likely**, based on _patterns in observed data_. Aristotle recognized induction as a key method for gaining knowledge about the world, especially when universal rules are not yet established.

!!! note
    _This system failed after several cyber attacks.  
    Similar systems also failed after attacks.  
    Therefore, such systems are likely vulnerable._

    Here, the conclusion is reasonable but not absolutely certain. A future system might behave differently, or additional factors may influence outcomes.

!!! success "Exercise"
    Can you bring an example of inductive reasoning in information systems, where conclusions are drawn from historical data rather than strict rules?

Modern science relies primarily on induction. We observe patterns in data and infer general laws or predictions. Engineers test systems repeatedly and assume that components that behaved reliably before will continue to do so. Security analysts look at previous cyberattacks to estimate future threats. Machine learning itself is grounded in induction: models infer patterns from past samples in the hope that those patterns generalize to new cases. This approach is powerful - _but it never guarantees certainty._

!!! warning "Important"
    [Mathematical induction](https://en.wikipedia.org/wiki/Mathematical_induction) is actually a _deductive_ proof method, not induction from repeated observations. Meanwhile, the so-called "deductions" of Sherlock Holmes are typically inductive generalizations from clues and experience rather than strict logical necessity.

This reliance on induction raises a major philosophical issue identified by [David Hume](https://plato.stanford.edu/entries/hume/). Inductive conclusions assume that the future will resemble the past, yet there is no logical proof for this assumption. We expect the sun to rise tomorrow because it has always risen before, but that reasoning only works if we already assume the future behaves like the past. Hume called this circular: we justify induction by appealing to past success, which is itself an inductive reasoning.

[Karl Popper](https://plato.stanford.edu/entries/popper/) later emphasized that _no amount of positive evidence can conclusively prove a scientific theory, but a single counterexample can disprove it_. This idea was popularized through the "black swan" illustration: after centuries of observing only white swans, Europeans concluded that all swans must be white - until the discovery of black swans in Australia instantly [falsified](https://en.wikipedia.org/wiki/Falsifiability) that belief. Popper argued that progress in science comes not from proving theories true, but from exposing them to conditions under which they could be shown false. A claim that cannot, even in principle, be falsified does not count as scientific.

Hume's challenge motivated the search for certainty through deduction. If observation cannot guarantee truth, perhaps truth could be established through pure reasoning. Mathematics follows this strategy: it begins with [axioms](http://axioms) - statements accepted as foundational - and applies strict logical rules to derive conclusions. If the axioms are true, then the conclusions must also be true. Deductive reasoning does not rely on the future behaving like the past; its certainty comes from structure, not observation.

!!! warning "Important" 
    Even mathematical certainty is limited by the axioms that define a system. Change those axioms, and the truths derived from them change as well. For example, in [Euclidean geometry](https://en.wikipedia.org/wiki/Euclidean_geometry), based on Euclid's [fifth postulate](https://en.wikipedia.org/wiki/Parallel_postulate), parallel lines are defined as lines that never intersect. But in [spherical geometry](https://en.wikipedia.org/wiki/Spherical_geometry), the closest analogue to straight lines are great circles - and every pair of great circles intersects - so parallel lines do not exist at all. Both geometries are internally valid because each follows logically from different foundational assumptions. Deductive certainty therefore conditional and applies only within the chosen axiomatic framework, not as a universal reflection of reality. Deductive conclusions are guaranteed only if the starting assumptions are.

## Ambiguity of Language

Natural language is inherently imprecise. Many disagreements in engineering, science, and ethics arise not from factual disputes but from differences in how people interpret the same words. Terms such as "secure," "harm," or "responsibility" may appear obvious, yet their meaning can shift dramatically depending on **context**.

To avoid such misunderstandings, we may attempt to translate vague statements into precise logical form. Mathematics is especially attractive for this goal because, at least within a defined axiomatic system, it provides deductive certainty: if the premises are true and the reasoning is valid, the conclusion must also be true.

Philosophers have long recognized this problem and sought ways to make reasoning more reliable. Aristotle took the first major step by abstracting arguments away from their wording and focusing on their form. He expressed reasoning patterns using generalized terms, similar to variables in modern logic:

> _All **A** are **B**. <br>
**C** is **A**. <br>
Therefore, **C** is **B**._

This structure is valid no matter what **A**, **B**, and **C** refer to. In this role, these letters function much like variables in programming or algebra: they stand in for any object or concept, allowing the logical structure to be tested independently of the specific content.

Aristotle's innovation laid the foundation for formal logic by showing that correct reasoning can be analyzed independently of ordinary language. As scientific knowledge expanded, ambiguity became an increasingly serious obstacle. Philosophers aimed to construct systems where truth could be determined without relying on interpretation. [Gottlob Frege](https://plato.stanford.edu/entries/frege/) attempted to rebuild reasoning using a _symbolic language_ (see example above) that separated meaning from grammar.

[Bertrand Russell](https://plato.stanford.edu/entries/russell/) continued this project in the effort to eliminate contradictions from mathematics by grounding it entirely in logic. Famously, in [_Principia Mathematica_](https://plato.stanford.edu/entries/principia-mathematica/), authored by Russell and his teacher [Alfred North Whitehead](https://plato.stanford.edu/entries/whitehead/), $1 + 1 = 2$ is finally proved after a few hundred pages of formal logical development. Their work influenced the [Vienna Circle](https://plato.stanford.edu/entries/vienna-circle/), who argued that every meaningful statement must be expressible in exact logical form. They hoped that by reducing knowledge to logical structures - essentially advanced kinds of AND/OR relationships used in digital circuit - reasoning itself could become precise, verifiable, and immune to error. If all argumentation could be translated into symbolic logic, rational thought could in principle be automated and made reliable.

However, this project revealed important limitations. Even if the structure of an argument is perfectly logical, its symbols must still be defined by humans. The meaning of key terms remains uncertain, especially in ethical or social contexts. Context can alter interpretation dramatically, and real-world decisions often involve conflicting goals and values that cannot be fully captured by rigid rules.

## Asimov's Laws of Robotics {#laws}

The prolific science-fiction writer and professor of biochemistry [Isaac Asimov](https://en.wikipedia.org/wiki/Isaac_Asimov) proposed the _Three Laws of Robotics_ in 1942 as a framework for robot behavior, after editor John W. Campbell recognized a consistent pattern in Asimov's stories and encouraged him to formalize those principles as explicit laws:

1. A robot may not injure a human being or, through inaction, allow a human being to come to harm.
2. A robot must obey the orders given it by human beings except where such orders would conflict with the First Law.
3. A robot must protect its own existence as long as such protection does not conflict with the First or Second Laws.

In structure, these laws resemble boolean algebra or programming statements: IF/THEN, AND/OR rules that one would encounter in basic propositional logic or in early [digital logic design](../02_binary): _IF a robot must obey humans AND must NOT harm humans, THEN commands that would cause harm are NOT allowed._ The laws function like conditional chains in a circuit.

While the laws seem logical and protective, Asimov's own stories showed how these clean, binary rules break down, and produce unintended and sometimes dangerous consequences. Consider the First Law's prohibition against allowing humans "to come to harm". In Asimov's fiction, robots interpreting this literally concluded they must protect humans from all possible danger - including themselves. This led robots to imprison humans, restricting freedom and choices to eliminate any risk of harm. The rule was followed perfectly, but the outcome violated human well-being.

This is an early representation of the [AI alignment problem](https://en.wikipedia.org/wiki/AI_alignment): aligning machine behavior with human values is not solved by simply giving a machine a bunch of hand-crafted rational rules. Modern AI alignment research faces the same dilemma. We can define rules, objectives, or [reward functions](https://en.wikipedia.org/wiki/Reinforcement_learning), yet systems may still follow them in ways that violate human expectations. Language is imprecise, values conflict, and context continually changes. Algorithms alone cannot ensure safe or morally responsible behavior.

!!! note
    An AI programmed to "maximize user engagement" on social media might discover that divisive, inflammatory content keeps people engaged longer. The algorithm optimized for its stated goal perfectly, but the outcome was harmful: increased polarization and spread of misinformation.

!!! success "Execise" 
    Design an improved version of the engagement algorithm noted in the example above by specifying a clearer objective function. Include constraints that protect user well-being, reduce misinformation, and prevent harmful content from being promoted, while still allowing the system to recommend interesting material.

The deeper issue is still the inherent ambiguity of natural language. Words like "harm," "obey," and "protect" appear to carry precise meaning, but when applied in complex environments, they require interpretation. A robot asked to prevent harm may choose solutions humans consider outrageous. A system told to obey orders might follow dangerous commands literally.

We mentioned how logicians pursued a vision of language modeled on mathematics - free from vagueness, contradiction, or subjective interpretation. The aim was certainty through formalization: if all knowledge could be translated into exact logical structures, then reasoning could become universally valid and immune to misunderstanding. But real ethics and real language resist such reduction. Mathematical logic works with well-defined symbols and truth values; ethical decisions involve contested principles, emotional context, and unpredictable consequences. You cannot represent every nuance in an AND/OR gate.

Asimov's laws demonstrate a crucial insight in applied ethics and technology design: even rules that appear perfectly rational can fail when _language_ is imprecise, _human values_ conflict, or real-world _context_ complicates their interpretation. Hand-crafted rules cannot anticipate every scenario, resolve every conflict, or encode the full complexity of human moral life.

## ACM Code of Ethics

Decisions made by computing professionals can protect users or put them in danger. A system that performs well but leaks personal information, or an AI that boosts engagement by amplifying harmful content, may succeed technically but still fail the people who rely on it. Good engineering requires more than correct algorithms.

Professional organizations such as the [Association for Computing Machinery](https://www.acm.org/) (ACM) provide [codes of ethics](https://www.acm.org/code-of-ethics) to guide these decisions. These codes emphasize honesty, accountability, protection of user privacy, and the duty to prevent harm, even when it conflicts with business goals or tight deadlines. Because we cannot encode every ethical rule into formal logic, the ACM Code relies on the assumption that computing professionals will apply fair and responsible human judgment when facing unclear or conflicting situations.

We haven't yet found a way to reduce ethics to formulas, logical gates, or automated decision rules. Ethical judgment requires human interpretation, awareness of context, and attention to values that may compete or change over time. Professionals must therefore combine technical skill with ethical judgment. Logical reasoning helps detect inconsistencies and foresee risks, but ethical awareness ensures that performance improvements do not come at the expense of human dignity, privacy, or safety. Responsible design means anticipating consequences - not just solving technical problems - and accepting accountability for the systems we create.

## Viruses and Cyber Attacks

Technological advancement is not inherently good or bad - it is _neutral_. Every innovation expands what humans can do, and that includes what humans can do to harm. The same network that enables global collaboration can also enable global exploitation. The same cryptography that protects dissidents can also shield criminals. Attackers exploit weaknesses not because technology is flawed, but because human purposes differ: some aim to create, others to manipulate or disrupt. When power increases faster than accountability, the potential for harm grows.

Having positive ethical intentions alone is not enough. A system that works flawlessly under honest use may crumble under malicious intent. Attackers push technology to its edges, probing for assumptions we failed to consider - assumptions about behavior, trust, incentives, or access. Their actions reveal the truth that _every technological system embodies both possibility and vulnerability._

Computing professionals must therefore understand _how systems are attacked,_ not only how they are designed. Protecting users requires anticipating misuse, resisting manipulation, and acknowledging that technology's benefits are inseparable from its risks.

[Social engineering](https://en.wikipedia.org/wiki/Social_engineering_%28security%29) attacks focus on people rather than code. [Phishing](https://en.wikipedia.org/wiki/Phishing) messages may impersonate banks or universities to trick users into giving away credentials. Closely related techniques like [spear-phishing](https://en.wikipedia.org/wiki/Spear-phishing) can compromise entire organizations. These attacks succeed because trust is easier to manipulate than technology.

[Malware](https://en.wikipedia.org/wiki/Malware) attacks exploit weaknesses in software and system configurations. [Trojan horse](https://en.wikipedia.org/wiki/Trojan_horse_%28computing%29) can appear as a legitimate software application and perform malicious actions. [Ransomware](https://en.wikipedia.org/wiki/Ransomware) encrypts data and demands payment. [Worms](https://en.wikipedia.org/wiki/Computer_worm) spread automatically across networks, while [spyware](https://en.wikipedia.org/wiki/Spyware) collects private information silently. Despite their differences, all malware seeks control, disruption, or theft.

[Network attacks](https://en.wikipedia.org/wiki/Cyberattack) target communication itself. [Man-in-the-Middle (MITM) attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack) intercepts or alters data. [Denial-of-Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack) attacks overwhelm servers so legitimate users cannot access services. These attacks show that even secure software can fail if communication channels are not protected.

[Credential stuffing](https://en.wikipedia.org/wiki/Credential_stuffing) uses leaked usernames and passwords from one service to break into accounts on another. [Brute-force attacks](https://en.wikipedia.org/wiki/Brute-force_attack) systematically guess passwords until one succeeds. These threats work not through sophisticated hacking, but through human error and poor security design.

[Wipers](https://en.wikipedia.org/wiki/Data_wiping) permanently erase data for sabotage. [Clickjacking](https://en.wikipedia.org/wiki/Clickjacking) disguises harmful actions behind innocent clicks. [Typosquatting](https://en.wikipedia.org/wiki/Typosquatting) exploits small URL mistakes to redirect victims to fake sites. These attacks undermine trust and enable fraud or political manipulation.

!!! note
    A student downloads what appears to be a free PDF textbook from an unofficial website. The file secretly contains a Trojan that installs itself on the laptop. Once installed, the Trojan records keystrokes and sends login credentials to an attacker. Later, the same laptop becomes part of a [botnet](https://en.wikipedia.org/wiki/Botnet) and is used to send traffic during a DoS attack against a university server.

## Digital Hygiene

[Digital hygiene](https://karpathy.bearblog.dev/digital-hygiene/) refers to everyday habits and practices that help users protect their devices, personal data, and online identity. Similar to personal hygiene, it focuses on regular and simple actions that prevent long-term harm rather than reacting only after problems occur. Good digital hygiene reduces the likelihood of cyber attacks, data loss, and unauthorized access, especially as users increasingly rely on digital systems for communication, study, and financial activities.

Some basic recommendations include using strong and unique passwords for different accounts. A single reused password becomes a _master key_: if one service is breached, attackers can access email, banking, and other vital accounts. Password managers help solve this problem by generating and storing unique passwords securely. However, they create a _single point of failure_: if the master password is weak, forgotten, or stolen, every account stored in the password manager may be compromised at once. Enabling [multi-factor authentication](https://en.wikipedia.org/wiki/Multi-factor_authentication) (MFA) adds an extra layer of security by requiring a second verification step, such as a code sent to a phone.

Users should avoid relying on any single component of their digital life. If all important files exist only on one laptop or one server, a hardware failure, ransomware attack, or accidental deletion could permanently destroy access. Regular [backups](https://en.wikipedia.org/wiki/Backup) - stored offline or in a trusted cloud environment - ensure that critical data can be recovered even if the primary device fails. The goal is to avoid single points of failure anywhere that matters.

Keeping software, applications, and operating systems updated is essential, as updates often fix known security vulnerabilities. Users should avoid clicking suspicious links or downloading files from unknown sources, since these remain common delivery methods for malware. Caution is also needed when sharing personal information online, especially on social media, where attackers collect details to craft convincing phishing attacks.

Using secure and trusted networks further reduces exposure to [eavesdropping](https://en.wikipedia.org/wiki/Network_eavesdropping) and interception, particularly when accessing sensitive accounts such as online banking or university services. Together, these practices form a proactive defense: small habits that prevent major harm.

## Additional Material
- [Challenger Distaster](https://archive.org/details/ChallengerDisaster)
- [Consequentialism vs. Deontology](https://www.youtube.com/watch?v=NT3VU4B5Dsc)
- [Absurd Trolley Problems](https://neal.fun/absurd-trolley-problems/)
- [AI Decides on Absurd Trolley Problems](https://www.youtube.com/watch?v=1boxiCcpZ-w)
- [David Hume and the Problem of Induction](https://www.youtube.com/watch?v=9_Gor1E8IxI)
- [The Ascent of Money Episode 3: Blowing Bubbles](https://www.youtube.com/watch?v=_ig5AqP0SFE&list=PLSP9UbXmBuqq2VIdj2JhYgjlYVWrWC2or&index=3)
- [Aristotle: Logic Internet Encyclopedia of Philosophy](https://iep.utm.edu/aristotle-logic/)
- [Isaac Asimov - Laws of Robotics - Extra Sci Fi](https://www.youtube.com/watch?v=3teiT--QGzo)
- [ACM Code of Ethics](https://www.acm.org/code-of-ethics)
- [Theranos - Silicon Valley's Greatest Disaster](https://www.youtube.com/watch?v=3CccfnRpPtM)
- [Every Type of Computer Virus Explained in 8 Minutes](https://www.youtube.com/watch?v=VJFaO2-zsCU)
- [Every Type of Cyber Attack Explained in 8 Minutes](https://www.youtube.com/watch?v=6mQ1L6YX9pY)
- [Digital hygiene](https://karpathy.bearblog.dev/digital-hygiene/)