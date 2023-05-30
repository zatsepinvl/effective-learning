# [97 Things Every Software Architect Should Know](https://www.amazon.com/Things-Every-Software-Architect-Should/dp/059652269X)

### 1. Don't put your resume ahead of the requirements (Nitin Borwankar).

1. The best thing for your career is a long string of happy customers eager to recommend you because you did the right
   thing by them and for the project.
2. Always put the customer’s long-term needs ahead of your own short-term needs, and you won’t go wrong.

### 2. Simplify essential complexity; diminish accidental complexity (Neal Ford).

1. Essential complexity represents the difficulty inherent in any domain problem or functional requirement.
2. Accidental complexity grows from the things we feel we must build to mitigate essential complexity.
3. It’s the duty of the architect to solve the problems inherent in essential complexity without introducing accidental
   complexity.
    1. Prefer frameworks derived from working code rather than ones cast down from ivory towers.
    2. Look at the percentage of code you have in a solution that directly addresses the business problem versus code
       that merely services the boundary between the application and the users.

### 3. Chances are, your biggest problem isn’t technical (Mark Ramm).

1. Most projects are built by people, and those people are the foundation for success and failure.
2. Use a conversation to understand the real problem.
3. Learning to treat people with respect, and learning give them the benefit of the doubt, is one of the core skills
   that turn a smart architect into an effective one.

### 4. Communication is king; clarity and leadership, its humble servants (Mark Richards).

1. The key to effective communication is clarity and leadership.
2. Keep things as simple as possible at the start of a project.
3. Throw away the lengthy Word documents and focus more on getting your ideas across.
4. Create simple diagrams to convey your thoughts.
5. Record the details of your architectural decisions ([Use Architectural Decision Records](https://adr.github.io/)).
5. Conduct informal whiteboard meetings.
6. Communicate with developers, work with developers, not against them.
7. Gain the respect of your co-workers to work in a healthy and effective environment.

### 5. Application architecture determines application performance (Randy Stafford).

1. Appreciate that application architecture is the primary determinant of application performance and scalability.
2. If the deployment of an application is insufficiently architected for the expected load, or if the application’s
   functional architecture is too inefficient in its utilization of computing resources, then no amount of “tuning” will
   bring about the desired performance and scalability characteristics.

### 6. Seek the value in requested capabilities (Einar Landre).

1. Always ask "Why" and understand the real value to address the real problem, and hopefully provide a better and
   cheaper solution.
2. The focus on value also simplifies prioritization: the most valuable requirements become the driving requirements.
3. Arrange workshops and meetings where the architects’ focus is on customer needs — helping the customers to answer the
   “why” question.

### 7. Stand Up! (Udi Dahan).

### 8. Everything will ultimately fail (Michael Nygard).

1. Accept that your system (software, hardware) inevitably fail.
2. Design and implement safe failure modes in advance (see crumple zones).

### 9. You’re negotiating more often than you think (Michael Nygard).

1. Dont make concessions on the first demand.
2. Look for a collaborative solution-finding exercise.
3. We’re trained as engineers, and engineering is all about making tradeoffs.
4. Negotiate win-win solution without being passive aggressive.

### 10. Quantify (Keith Braithwaite).

1. If performance matters, ask for exact numbers:
   How many? In what period? How often? How soon? Increasing or decreasing? At what rate? Reject “Lots” and “soon” as
   answers.
2. If performance doesn't matter, ensure for that and then focus on aspects of the system that are worth paying for.

### 11. One line of working code is worth 500 of specification (Keith Braithwaite).

1. Design matters, but the fact is that specifications alone have no value. The ultimate goal of a software project is a
   production system.
2. No design is perfect from the start; all designs need to be modified as they are implemented.
3. Listen to the team who work on implementing your vision or better try to program it on your own.

### 12. There is no one-size-fits-all solution (Randy Stafford).

1. Architects must continuously develop and exercise "contextual sense".
2. (system architecting) The most important knowledge of software patterns is the knowledge of when to apply them and
   when not to apply them depending on the context.
3. (problem analysis) Root cause hypotheses and associated corrective actions during problem analysis depend on the
   context.
4. **Problem analysis and system architecting requires accumulated contextual sense.**

### 13. It's never too early to think about performance (Rebecca Parsons).

1. Strive to begin testing performance as soon as possible from the very beginning of the project.
2. Set up performance testing incrementally.
3. Why is this so important? The biggest reason is that at the very least you know the kinds of changes that made
   performance fall off a cliff.

### 14. Architecting is about balance (Randy Stafford).

1. Software architecting is about balancing technical requirements with the business requirements of stakeholders in the
   project.

### 15. Commit-and-run is a crime (Niclas Nilsson).

1. Commit-and-run is a crime because it kills flow and stops the development.
2. Implement automated tests that will build and check every commit.
3. Make tests fast. People should not wait for computers, or they will take shortcuts otherwise, which often causes
   problems for others.
4. Invest time in making the development environment fast to work with.

### 16. There can be more than one (Keith Braithwaite).

1. One "Account" table (or data model, message format, message transport) may not be enough for an enterprise to do the
   job.
2. Always consider the possibility that decomposition of your system by nonfunctional parameters may reveal
   opportunities to allow diverse solutions to your customers’ advantage.
3. OLTP and OLAP with ETL process on the boundary between are examples of two subsystems that works together well for
   messy, fuzzy and inconsistent world of business processes.

### 17. Business drives (Dave Muirhead).

1. Let the business drive.
2. **The architect must understand the desired ROI, and by implication, the limits of the value of the software
   initiative to the business.**
3. Development team must not make business decisions.

### 18. Simplicity before generality, use before reuse (Kevlin Henney).

1. Simplicity through experience rather than generality through guesswork.
2. When there are two possible solutions, favor one that is simpler and based on concrete need.
3. Software components should, first and foremost, be designed for use and to fulfill that use well.
4. Effective generality comes from understanding, and understanding leads to simplification.

### 19. Architects must be hands on (John Davies).

1. A good architect should lead by example.
2. A good architect should be able to spot a problem, call the team together, and without picking out a victim, explain
   what the problem is or might be and provide an elegant workaround or solution.
3. It is perfectly respectable for an architect ask for help from the team or peer architects.
4. All good architects are well-connected.

### 20. Continuously integrate (David Bartlett).

1. Continuous Integration (CI) is a must for any software project today.
2. Always do CI.

### 21. Avoid scheduling failures (Norman Carnovale).

1. The idea that schedules can be shortened in order to reduce cost or speed up delivery is a very common misconception.
   Avoid it at all costs.
3. Rushing only leads to low quality and bugs that are very difficult to fix in the future.
4. Speak up early. Prepare and negotiate moving noncritical functionality to future release(s).

### 22. Architectural tradeoffs (Mark Richards).

1. It is virtually impossible to design an architecture that has it all at the same time.
2. Trying to fulfill each and every requirement (as with the [Vasa](https://en.wikipedia.org/wiki/Vasa_(ship)) ship)
   creates an unstable architecture that essentially accomplishes nothing well.
3. Use [Architecture Tradeoff Analysis Method](https://resources.sei.cmu.edu/library/asset-view.cfm?assetID=5177) (ATAM)
   and [Cost Benefit Analysis Method](http://www.sei.cmu.edu/architecture/cbam.html) (CBAM) to determine what the
   tradeoffs should be applied.

### 23. Database as a fortress (Dan Chak).

1. Build a solid data model from Day One.
2. Do not take shortcuts at database level. Migrations are difficult, time-consuming and error pron.
3. Implement referential integrity and domain constraints on database layer.

### 24. Use uncertainty as a driver (Kevlin Henney).

1. When you have to choose between two reasonably appropriate options A and B, make the decision not to make a decision.
2. Instead of trying to decide between options A and B, separate or isolate the unknown implementation details where the
   decision should be made from the abstract known part (e.g. use dependency inversion or interfaces).
3. Defer the actual decision until a decision can be made more responsibly, based on actual knowledge, but not so late
   that it is not possible to take advantage of that knowledge.

### 25. Warning: Problems in mirror may be larger than they appear (Dave Quick).

1. Issues that seemed trivial early in the project become critical after it is too late to fix them.
2. Establish an organized approach to managing risks. Track that kind of issues as risks like you do for bugs and tasks.
   Review, re-evaluate and prioritize them.
3. “Bad smells” are worth recognizing. If the facts aren’t there yet, look for the simplest tests that would provide the
   facts.
4. Blind spots are, by definition, hard to recognize. People you trust to tell you the hard truth when you need it are a
   precious resource.

### 26. Reuse is about people and education, not just architecture (Jeremy Meyer).

1. The truth is that even the most beautiful, elegant, and reusable architecture, framework, or system will only be
   reused by people who:
    1. Know It’s There. Push information about framework using different communication channels (like wiki, emails,
       personal meetings).
    2. Know How to Use It. Provide easy access to documentation, train, teach how to use the framework or architecture.
    3. Are Convinced That It’s Better Than Doing It Themselves. See point 1.

### 27. There is no "I" in Architecture (Dave Quick).

1. Our egos can be our own worst enemy.
2. Follow the following to avoid it:
    1. Requirements don’t lie. You don’t drive the architecture, the requirements do. You do your best to serve their
       needs.
    2. Focus on the team. You need their help as much or more than they need yours.
    3. Check your work. The model is not the architecture. It is only your understanding of how the architecture should
       work.
    4. Watch yourself. Consider your interactions for a few minutes every day.
3. Removing the ‘I’ from architecture doesn’t guarantee success. It just removes a common source of failure that’s
   entirely your fault.

### 28. Get the 1,000-foot view (Erik Doernenburg).

1. “I know it when I see it." - But how to see the quality of the software?
2. Design diagrams a 30,000-foot view, the source code is a ground-level view. Both views fail to convey much
   information about the **quality** of the software.
3. Add tools to aggregate different metrics and views on the source code like
    * method count,
    * class fanout,
    * cyclomatic complexity,
    * design structure matrix
    * dependency graphs.
4. Even with just a single diagram, we can rely on our ability to spot patterns and perceive aesthetics. Most of the
   time a very simple relationship holds: if it looks good, it probably is good.

### 29. Try before reuse (Erik Doernenburg).

1. Delay commitment until the last responsible moment.
2. Ask several developers to come up with a solution to the problem and go with it for a while.
3. As the last responsible moment approaches, the team meets to assess the benefits and drawbacks of the different
   solutions.
4. Trying two or even more approaches to the same problem requires more effort than making a decision upfront but
   eventually might be the least expensive option.

### 30. Understand the business domain (Mark Richards).

1. Knowing the business domain allows a software architect to better understand the problems, issues, goals, data, and
   processes, all of which are key factors when designing an effective enterprise architecture.
2. Having strong knowledge of a particular domain gives you the ability to communicate with C-level executives in their
   language. This in turn creates a strong level of confidence that the software architect knows what he or she is
   doing.

### 31. Programming is an act of design (Einar Landre).

1. There are two main processes in classical engineering, like building a new car model in car industry: creative design
   and manufacturing of cars in line.
2. The only artifact of software engineering that satisfies the criteria for a design document, as such a document is
   understood and used in classical engineering, is the source code (By “What is software design?”, Jack Reeves).
3. Source code = new model design; compiler, build and test scripts = manufacturing line.
4. Programming is an act of design, not an act of construction.

### 32. Give developers autonomy (Philip Nelson).

1. Give all of your teammates enough autonomy to exercise their own creativity and abilities.
2. As an architect, looking at how the whole system fits together is your main focus. Listen for points of pain and try
   to improve them.
3. Create the environment where teammates come and ask you for suggestions.

### 33. Time changes everything (Philip Nelson).

1. Pick a worthy challenge - we can influence what we are asked to do and choose what is really needed. A good solution
   to the right challenge will probably outlast all others.
2. Simple rules - keep it simple, stupid. Try to learn what simple means in the lens that only time can grind.
3. Be happy with that old stuff - learn to embrace that old stuff, and resist the temptation to think you should go back
   and “fix” it. If it solved the needs and the solution is an appropriate one for the problem, just move on and be
   happy.

### 34. “Software Architect” has only lowercase a’s; deal with it (Barry Hawkins).

### 35. Scope is the enemy of success (Dave Quick).

1. Expanding scope is the enemy of success because the probability of failure grows faster than expected.
2. Strategies can help to reduce or manage scope in real-world projects:
    1. Understand the real needs. Question any requirements not explained in terms of measurable value to the customer.
    2. Divide and conquer. Look for opportunities to divide up the work into smaller independent chunks or subprojects.
    3. Prioritize. Important requirements usually remain important as the business changes, while others change or even
       evaporate.
    4. Deliver results as soon as possible. Building the most important things first gets you the most important
       feedback early, when you need it most.
3. Reducing project scope often results in a simpler architecture, and is one of the most effective strategies an
   architect can apply to improve the odds of success.

### 36. Value stewardship over showmanship (Barry Hawkins).

1. Stewardship, taking responsibility and care of another’s property, is the appropriate role of an architect.
2. Value stewardship over showmanship; never forget that you are playing with other people’s money.

### 37. Software architecture has ethical consequences (Michael Nygard).

1. It’s not ethical to worsen the lives of others, even a small bit, just to make things easy for yourself.
2. Always be mindful of the impact your decisions have on your users. You should be willing to bear large burdens to
   ease theirs.

### 38. Skyscrapers aren't scalable (Michael Nygard).

1. The construction process has to go from a bare site to a finished building. In the interim, every worker must be able
   to apply his trade, and the unfinished structure has to stand up the whole time.
2. **Incremental deployment**. The lesson from the civil engineering: We should plan to deploy one component at a time.
   Benefits are:
    1. We spread technical risk out over a longer period of time.
    2. It forces us to create well-defined interfaces between components to support reverse-integration with the old
       system.
3. **Early release**. Conversley, we should deploy early:
    1. Each component can iterate independently.
    2. It will force you to work out thorny issues like continuous availability during deployments and protocol
       versioning.

### 39. Heterogeneity wins (Edward Garson).

1. Text-based protocols (REST) have brought about the ability to use different languages for different components in
   distibuted systems.
2. Now you can employ the right paradigm (like OOP, functional programming) not just language for problems and domains
   that match the best.
3. Your job as architect has become even more challenging because technology silos are crumbling in the face of new
   possibilities: embrace this, think outside the stack, and leverage the new diversity: heterogeneity wins.

### 40. It's all about performance (Craig Russell).

1. Performance is not only about response time:
    1. Performance of the people building the system (productivity) - cost and schedule of the project.
    2. Performance of the human interactions of the system, e.g. time to complete a domain-specific task (use case) or
       how many gestures are required.
    3. Performance of the noninteractive components, e.g. how fast are nightly builds and how fast the system can be
       recovered after the disaster.
2. When considering the implementation and operation of a successful system, architects and designers should always pay
   careful attention to all of the performance aspects.

### 41. Engineer in the white spaces (Michael Nygard).

1. When you diagram your system connecting componets represented as boxes with arrows there is the white space between
   the boxes.
2. This white space or the substrate is about latency, throughput, retries, SLAs, request/replay formats, data limits
   and so on.
3. Ask as many questions about the arrows as you can and answer them all - that is the essence of engineering the white
   spaces.

### 42. Talk the talk (Mark Richards).

1. In any profession, jargon is used so that individuals within that profession can effectively communicate with one
   another.
2. Architects communicate effectivly using architecture and design patterns:
    1. Enterprise architecture patterns - high-level architecture, e.g. event-driven (EDA), service-oriented (SOA),
       resource-oriented and pipeline architectures.
    3. Application architecture patterns - architecture of a particular application or subsystem, e.g. J2EE design
       patterns, Martin Fowler’s book Patterns of Enterprise Application Architecture.
    4. Integration patterns - design of the white space between components/systems, e.g., file sharing, remote procedure
       calls, and numerous patterns (http://www.enterpriseintegrationpatterns.com/eaipatterns.html).
    5. Design patterns - design of individual components, e.g., Gang of Four book
    6. Anti-patterns - http://en.wikipedia.org/wiki/Anti-patterns.

### 43. Context is king (Edward Garson).

1. Effectively there are no architectural ideals.
2. Context is the only force that trumps simplicity when you’re making architectural decisions.
3. Sometimes the most important decisions are not about what you put in, but rather what you omit.
4. Your team should be free of ideals, reflect on context in the first instance, and reach for the simplest solutions
   from there.

### 44. Dwarves, elves, wizards, and kings (Evan Cofsky)

1. There are many characters can be on the project. Architect is a king of sorts.
2. The architect must be familiar with all of them, and ensure that the architecture has roles for all of them.
3. Without all the characters, the team can only solve one class of problem, and is stopped at the first barrier
   impassable to that solution.
4. The team makes the project, not just one type of the characters.

### 45. Learn from architects of buildings (Keith Braithwaite).

1. The role of architect is not primarily technical, but also is about the social act and the material theater of human
   activity.
2. There are things that strongly mark out architects: taste, refinement and generosity spirit.
3. Frank Lloyd Wright said that the architect’s best friend was the sledgehammer. What have you demolished recently?
4. As an architect, aim to give delight with your work.

### 46. Fight repetition (Niclas Nilsson).

1. Duplication is evil.
2. Repetitive work slows down development.
3. As an architect, you set the tone, thus you should provide the most clean, intention revealing and free of
   duplication source code examples.
4. Watch out for repetition and fight it.

### 47. Welcome to the real world (Gregor Hohpe).

1. The real world is full of delays, request rejections, broken promises, concurrency issues and inconsistency. 
2. When you run applications on many machines, failure is no longer a question of “if,” but of “when”.
3. Awareness is a first important step toward a solution.
4. Be ready to respond to events at any time in any order, regaining your context as needed.
5. Use different exception handling approaches: https://www.enterpriseintegrationpatterns.com/ramblings/18_starbucks.html.
6. Avoid complete chaos by modeling your application using event-driven process chains or state models. Reconcile errors through compensation, retry, or tentative operations.

### 48.Don’t control, but observe (Gregor Hohpe).

1. Don't try to intensively document your architectue - it will be out of date the moment it is printed.
2. Being a control-freak architect is so yesteryear, leading to tightly coupled and brittle solutions. But letting the software run wild is sure to spawn chaos.
3. You have to supplement the lack of control with other mechanisms and instruments:
   1. The current system configuration is another great source of information.
   2. A graph model of the actual communication between components.
   3. “Reverse MDA.”1 Instead of a model driving the architecture, you build a flexible architecture, and extract the model from the actual system state.
   4. 1,000-foot view as described by Erik Doernenburg.

### 49. Janus the architect (David Bartlett).

1. Janus was the god of beginnings and endings, doors and passageways. He is usually depicted with two heads facing in different directions.
2. Architects should be like Janus: have two heads capable of carrying two different ideas or thoughts, different goals and visions.
3. An excellent IT architect will be a superior listener and evaluator.
4. Architects should endeavour to ensure their products will withstand the transitions and changes that are sure to come.

### 50. Architects' focus is on the boundaries and interfaces (Einar Landre).

1. "Divide and conquer" or "separate concerns".
2. Minimize coupling, maximize cohesion.
3. Do not slice through regions where high rates of information exchange are required.
4. Practical steps (either for a new project or existing one):
   1. Separate the domain into bounded contexts. 
   2. Define the relationships (functional, organizational or technical dependencies) between the contexts - create a context map.
   3. Create well-defined interfaces for cross boundary communications.

### 51. Empower developers (Timothy High).

1. Every architect nees good team of developers.
2. To the extent your responsibilities allow, you should do everything possible to empower your developers:
   1. Developers should have the tools they need: don't impose it on them.
   2. Developers should have the skills they need: organize meetings, conferences, trainings.  **The work life of a developer should be hands-on and practical, but also should be actively academic.**
   3. Let developers make their own decisions wherever it won't contradict the overall goal of the software design.
   4. Protect developers from nonessential parts of their job: even not being a manager, asseess processes are used, make sure they are designed to remove obstacles, not increase them.

### 52. Record your rationale (Timothy High).

1. One type of documentation that ages well, doesn't require much effort, and almost always pays off is a record of the rationale behind decisions that are made regarding the software architecture.
2. Choose the appropriate format of the documentation. Dont spend much time on it. Focus only on committing rationale, not the current state. Use [Use Architectural Decision Records](https://adr.github.io/).
3. This documentation gives the folowing benefits:
   1. It forces you to be explicit about yout reasoning in order to verify that your foundations are solid - **"Challenge Assumptions - Especially Your Own"**.
   2. It can be used as a starting point to re-evaluate a decision when the conditions that influenced it have changed.

### 53. Challenge assumptions - especially your own (Timothy High).

1. Wethern's Law Of Suspended Judgement: Assumption Is The Mother Of All Screw-ups.
2. Again, document the rationale behind each decision that is made.
3. Record along with each decision the context of that decision, e.g., requirements, facts that decision-makers found important and **assumptions**.
4. Validate any assumption and make sure that it isn't based on relevant empirical evidence.
5. Facts and assumptions are the pillars on which your software will be built. Whatever they are, make sure the foundations are solid.

### 54. Share your knowledge and experiences (Paul W. Homer).

1. Rationalize your experience. The best and easiest way of working through it is to attempt to explain it to another person.
2. You dont really understand something until you can explain it easily.
3. While we may have had specific experiences, the inferences we draw from them not be entirely corrrect in the overall context.
4. It's only when we accept our flaws that we open up the possibility of improving.
5. The old adage about learning more from failure always holds.

### 55. Pattern pathology (Chad LaVigne).

1. Design patterns are reusable, discovered, documented solutions to recurring problems.
2. Design patterns are excellent tools for mitigating necessary complexity, but like all tools, they can be misused.
3. It's our job to identify problems solved by design patterns when they arise and apply them appropriately.

### 56. Don't stretch the architectue metaphors (David Ing).

1. Use metaphors only for exploratory communication purposes because of the following:
   1. Interpretation issues. Example: "We're building a transport system like a ship travelling between a series of docks" - is it about crossing the Pacific or just a swimming pool?
   2. Odd decisions because of a fondness for the metaphor. Example: "We said it's a filing cabinet (but with six dimensions and of infinite length), so we have to show it to the user alphabetically..."
   3. Obsolete and broken metaphors in the legacy and old code. 
2. Don't put the architecture metaphors into the code.

### 57. Focus on application suport and maintenance (Mncedisi Kasper).

1. Since 80% of an application's lifecycle is spent in maintenance, you should pay a lot of attention to the problems of support and maintenance whe you're desiging.
2. Operation team can not debug the system in production or reissue a financial transaction to see what went wrong.
3. Traceability, auditing and logging are crucial.

### 58. Prepare to pick two (Bill de hOra).

1. CAP state that it's impossible to achieve all three in the distributed system (consistency, availability, partition tolerance).
2. Trying to have all three will drastically increase the engineering costs and typically increase complexity without actual achieving the desired effect or business goal.
3. Be ever the skeptic about system properties (like 100% available, no single point of failure and so on), because architectural dogma tends to undermine delivery.
4. Tradeoffs are inevitable, but accepting them often induces a creative and inventive result.

### 59. Prefer principles axioms, and analogies to opinion and taste (Michael Harmer).

1. An architecture with clear principles is an architecture that afress its architect from reviewing everything and being everywhere.
2. Disagreements about opinion and tast invariably turn into political arguments in which authority is used to win.
3. Principles and axioms also give an architecture consistency throughout its implementation and across time.

### 60. Start with a walking skeleton (Clint Shank).

1. One very useful strategy for implementing, verifying, and evolving an application architecture is to start with what Alistair Cockburn calls a walking skeleton.
2. Assumptions about the architecture are validated earlier.
3. More difficult and time consuming efforts should be done earlier in the project.
4. Start with walking skeleton, keet it running, and grow it incrementally.

### 61. It is all about the data (Paul W.Homer).

1. The data is conceptually smaller than the code and considerably less complicated.
2. The data-oriented perspective - seeing the system entirely by the structure of its underlying information - can reduce even the most complicated system down to a tangible collection of details.
3. Data sits at the core of most problems Business domain problems creep into the code via the data.
4. The functionality is what we see first, but it's data the forms the core of every system.

### 62. Make sure the simple stuff is simple (Chad LaVigne).

1. If you find yourself designing a solution so clever that it may be self-aware, stop and think.
2. Before moving forward with an architectural decision that exceeds system requirements, ask yourself how difficult it would be to remove after it's in place.
3. **Remember this: when you try to guess at future requirements, 50% of the time you're wrong and 49% of the time you're very, very wrong.**
4. Solve today's problem today. Get the application out the door on time and wait for feedback to generate real requirements.

### 63. Before anything, an architect is a developer (Mike Brown).

1. We all know the quickest way to gain a developer's trust: _your code is your currency_.
2. Pick up some of the more intricate tasks: it's fun,  helps you to keep your development skills sharp and to demonstrate that you are not just blowing smoke where the sun doesn't shine.
3. You should know the effort involved in  developing the solution you are designing. Therefore, if you design the solution, you should be able to code it.

### 64. The ROI Variable (George Malamidis).

1. One of the way of measuring the success of investments is byt rate of return, also known as _return on investment_ (ROI). For example, devoting 4 hours a week to testing, we save 8 hours a week spent on bug fixing, thus ROI = 200% (8/4*100%).
2. Investments should always result in added value.
3. Consider architectural decisions as investments and take into account the associated rate of return; it is a useful approach for finding out how pragmatic or appropriate ever option on the table is.

### 65. Your system is legacy; design for it (Dave Anderson).

1. The nature of software today means things go out of date fast.
2. Design for maintenance, that means several things: Clarity, Testability, Correctness, Tracebility.
3. Try to think of a different team opening up the codebase and working out what's happening. This is fundamental for great architecture.
4. Legacy tends to be a bad word in software circles, but in reality, all software systems should endure the tag. It is not a bad thing, as it may indicate that your system is durable, meets expectations, and has business value.

### 66. If there is only one solutionl get a second opinion (Timothy High).

1. If you can think only of one solution to a problem, you're in trouble.
2. Generally, tradeoffs must be made by choosing the solution that satisfies the requirements according to the most critical priorities. If you only have one solution to the problem at hand, it means that you will have no room to negotiate these tradeoffs.
3. If you don't have enough experience in the particular problem domain, do yourself a favor and ask someone more experienced to give you a hand.
4. Don't design the architecture from habit. Know and compare different styles of architecture.

### 67. Understand the impact of change (Doug Crawford).

1. The great architect understands the impact of change - not just in isolated software modules, but also between people and between systems.
2. The architect's role is not necessarily to manage change, but rather to ensure that change is manageable.
3. There are many tools and techniques to mitigate the impact of change:
   1. Make small, incremental changes
   2. Build repeatable test cases and run them often
   3. Make building test cases easier
   4. Track dependencies
   5. Act and react systematically
   6. Automate repetitive tasks

### 68. You have to understand hardware, too (Kamal Wickramanayake).

1. The defense against poor hardware planning is to work closely with an infrastructure architect.
2. Drawing on our past experience can help.
3. Budgeting for capacity planning can be much more cost effective than buying more hardware than you need. In this case, horizontal scalability is the key - adding hardware as needed rather than overbuying in the beginning.
4. Just as an architect is responsible for establishing the links between business demands and a software solution, she is responsible for envisioning the links between hardware and software.

### 69. Shortcuts now are paid back with interest later (Scot Mcphee).

1. It's important to remember when architecting a system that maintenance will, in the long run, consume more resources than initial development of the project. Shortcuts taken during the initial development phase of a project can result in significant costs later.
2. In addition to avoiding shortcuts at the inception of a project, it's also important to correct poor design decisions as quickly as they are discovered.
3. As an architect, whenever you encounter an architectural problem or design flaw, insist on that it be rectified now, when it is cheapest to fix.

### 70. "Perfect" is the enemy of "Good Enough" (Greg Neyberg).

1. My advice: don't give in to the temptation to make your design, or our implementation, perfrect! Aim for "good enough" and stop when you've achived it.
2. Good enough means that the remaining imperfections do not impact system functionality, maintainability, or performance in any meaningful way.
3. Remember that application development is not a beauty contest, so stop looking for flaws and wasting time chasing perfection.

### 71. Avoid "Good Ideas" (Greg Nyberg).

1. Good ideas kill projects. Something it's quick death, but often it's a slow, lingering death caused by missed milestones and a spiraling bug count.
2. You know the kind of good ideas I'm talking about: tempting, no-brainer, innocent-looking, couldn't-possibly-hurt-to-try sorts of ideas.
3. You tell your project manager you need a few weeks to implement this "good idea", but it ends up impacting more code that originally anticipated, and your schedule starts to slip.

### 72. Great content creates great systems (Zubin Wadia).

1. Great content means the difference between a system that is hollow and one that is relevant.
2. Content is king. Content is the network. Content is the interface. In an increasingly interconnected world, content quality is rapidly becoming the difference between success and failure. 
3. Part of the design process for a new system should be devoted to assessing content inventory. Designing an effective domain/object/data model is not enough.
4. Analyze all available content and assess its value.

### 73. The business versus the angry architect (Chad LaVinge).

1. We're confident in our solutions and we deliver as advertised. We have reached homeostasis. This is the perfect time to make a colossal mistake - likde deciding you know so much that it's time for you to start talking more than you listen.
2. Remember, when you're talking you can hear somtehing you already know. Don't ever start thinking you're so smart that no one else has something valuable to say.
3. Don't allow yourself to become a disgruntled genius who spends all of his time trying to impress others by making witty, condescending statements about how poorly the company is run.
4. Regardless of how, find a way to establish a good relationship with the business and don't let your ego damage it. It will make you a happier, more roductive architect.

### 74. Stretch key dimensions to see what breaks (Stephen Jones).

1. Dimensions are stretched individually and then in combination to tease out the unseen limits that might lie hidden in the initial design.
2. Stretching key dimensions allows an architect to validate a solution by:
   1. Understanding where the limits are.
   2. Comfirming that where is head room to accommodate "busy days" or "catch up" after an outage.
   3. Validating that the data access choices are still valid as system scales.
   4. Confirming how the application's increased workload will be scaled across additional hardware.
   5. Confirming that he application can still be recovered if the data volumes are increased and/or data is now split among an increased infrastructure.
3. The redesign will be cheaper whilst the design is still virtual, technical choices are not locked-in and the business data has yet to be stored in the repositories.

### 75. If you design it, you should be able to code it (Mike Brown).

1. In architecture, it's tempting to create elaborate designs and abstractions that elegantly address the problem at hand. At the end of the day, someone has to implement your design, and the architectural acrobatics that you have the developers perform impact the project.
2. If your architecture depends on design elements that you haven't personally used, there are a number of negative side effects:
   1. You will not have experienced the learning curve that your developers will have to face.
   2. You will not know the pitfalls to avoid when using the elements.
   3. You will lose the confidence of your developers.
   4. You will intoduce unnecessary risk.
3. There is another axiom in and of itself: before anything, an architect is a developer.

### 76. A rose by any other name will end up as a cabbage (Sam Gardiner).

1. If you don't know what a thing should be called, you cannot know what it is. If you don't know what it is, you cannot sit down and write code.
2. If you can't agree on a name that is specific enough for you to know when it is wrong, then you might have some difficulty even getting started.
3. If you change the name three times, then you should stop until you know what you are trying to build.

### 77. Stable problems get high-quality solutions (Sam Gardiner).

1. In the real world, the best architects don't solve hard problems, they work around them.
2. An architect should look at a whole mess of concepts and data and process and separate them into smaller **stable** pieces or "chunks" that should be
   1. Internally cohesive.
   2. Well separated from other chunks (decoupled).
3. If the problem is stable, then when it is solved, it is solved permanently.
4. A stable problem (separtated stable chunks) allows you to create a system with a stable design; stable design allows you to concentrate on making an application that has very high quality.

### 78. It takes diligence (Brian Hart).

1. Igenuity is a key trait of successful architects. However, an equally important characteristic of the activities of a successful architect is diligence.
2. It is important to realize in these retrospective of failed projects that in most cases it isn't incompetence that drove failure, but rather the lack of both diligence and a sence of urgency.
3. Diligence also requires an architect to succeed at the deceptivly simple task of making and keeping commitments.
4. It does not take genius. It takes diligence. It takes moral clarity. It takes ingenuity. And above all, it takes a willingness to try.

### 79. Take responsibility for your decisions (Yi Zhou).

1. You should *not* claim that an architectual decision has been made until the following two conditions are met:
   1. A decision has been put in writing.
   2. A decision has been communicated to the people who execute it and the people who will be affected directly or indirectly.
2. Second, review your architectual decisions perdiodically.
3. Third, enforce your architectual decisions.
4. Finally, delegate some decision making to others who are experts in a problem domain in which you are not proficient.

### 80. Don't be clever (Eben Hewitt).

1. Clever software is expensive, hard to maintain, and brittle. Don't be clever. Be as dumb as you possibly can and still create the appropriate design.
2. Work in rough chalk sketches; stay general. Let go of the flavor of the day. It takes a smart architect to be dumb.
3. Empty your head and approach the problem without your extensive knowledge of closures and generics and how to manipulate object graduation in the heap.
4. More developers can implement and maintain dumb solutions. In dumb solutions, each component can do only one thing. They will take less time to create, and less time to change later.

### 81. Choose your weapons carefully, relinquish them reluctantly (Chad LaVinge).

1. As seasoned veterans of software design and implementation, all architects are armed with an array of weapons they've used with repeated success.
2. Before adopting new technology, you should justify the risk involved with it:
   1. Ask yourself how the business will benefit from this decision.
   2. Esitmate the cost associated with the shortcomings of new technology.
   3. Consider future relevance, wait for the hype to die down and see if the technology settles into a space of usefulness.
3. Don't jeopradize your project for a technology that doesn't have a future.

### 82. Your customer is not your customer (Eben Hewitt).

1. Your customer's customer is your customer. If your customer's customer wins, you customer wins. Which means you win.
2. If you know that your customer is leaving out things your customer's customer will need, address them, and communicate why.
3. You're killing your customer's customer when you agree to do work you known is a bad idea.
4. Remember that while your customer is writting your check, you must be clear that you need to honor best practices, so that you can make what the customer really needs, not just what they say they need.
5. We cannot love your customers so much, love we not their customers more. ([Richard Lovelace "To Lucasta, on Goging to the Wars"](https://poets.org/poem/lucasta-going-wars)).

### 83. It will never look like that (Peter Gillard-Moss).

1. No matter how in-depth, how well researched, and how well thought-out your design, it will never come out looking the same as in your head.
2. Design is a discovery process; as we implement, we discover new information that is often impossible to know upfront.
3. By accepting that design is an ongoing and empirical process in a forever-changing world, we learn that the design process must be flexible and ongoing too.

### 84. Choose frameworks that play well with others (Eric Hawthorne).

1. You must choose frameworks that do not overlap and that are humble, simple, and specialized.
2. Make sure you understand how the logical domains and concerns addressed by your candidate frameworks overlap. Draw a Venn diagram if you need to.
3. Your system should be comprised of mutually exclusive frameworks, each of which may be a master of its domain, but which is also simple, humble, and flexible.

### 85. Make a strong business case (Yi Zhou).

1. The benefits of software architecture are obvious for architects, but are mythical for many stakeholders. Mass psychology tells us that "seeing in believing" is the strongest belief for most people. 
2. If you can control how people perceive the architectural approach you propose, it's virtually guaranteed that you can control how they will react to your proposal. 
3. Employ the followibg steps to generate solid business cases:
   1. _Establish the value proposition_. Focus on the capability of your architecture to increase the productivity and effiency of the business.
   2. _Build metrics to quantify_. Measure and quantify the values that you promise to deliver. 
   3. _Link back to traditional business metrics_. Translate your techical analysis into dollar figures. 
   4. _Know where to stop_. Prepare a roadmap and let the stakeholders decide where to stop.
   5. _Find the right timing_.

### 86. Control the data, not just the code (Chad LaVigne).

1. For some reason the data portion of the migration plan seems to be easily overlooked during archiecture planning. As a result, it can become brittle, manual process that gets bolted on as an afterthought.
2. Database changes shouldn't create a ripple in your build's time-space continuum.
3. You need to be able to build the entire application, including the database as one unit.
4. Make data and schema management a seamless part of your automated build and testing process early on and include an undo button; it will pay large dividends. 

### 87. Pay down your technical debt (Burkhardt Hufnagel).

1. When a change must be made (add feature, fix bug), there are two possible choices: you can take the time needed to "do it right", or you can take one or more "shortcuts" and try to get the change out the door sooner.
2. If you believe the system is reasonably stable, then it may make sense to go the "quick and dirty" route and get the change into production quickly, **but don't stop there**.
3. There's hidden cost to making these quick and dirty fixes. For financial debts the hidden cost is called "interest".
4. Once the fix is in production, have the developers go back and fix it properly so that it can be included in the next scheduled release. This is the equivalent of charging something on your credit card and then paying off the balance at the end of the month so you don't get charged interest.

### 88. Don't be a problem solver (Eben Hewitt).

1. :exclamation: Architects and developers learn to enter problem-solving mode immediately. But sometimes the best solution is no solution. Many software problems need not be solved at all.
2. :bulb: We must interrogate the problem itself. We must learn, like a telephoto lens, to zoom in and zoom out, in order to ensure that the question is really framed properly, and that we're not merely accepting what we're given.
3. :bulb: Instead of immediately working to solve the problem as presented, see if you can change the problem. Ask yourself, what would the architecture look like if I just didn't have this problem.
4. :bulb: And even more, think what the world would look like if you just didn't have this problem.

### 89. Build systems to be zuhanden (Keith Braithwaite).

1. ❗ We build tools. The systems that we make have no other reason to exist (nor we to get paid) than to help someone do something.
2. 💡 During successful use, a tool is _zuhanden_ ("ready-to-hand", having the property of "handiness"). The tool is experienced directly; it is used  without consideration, without theorisation (the development of something beyond its obvious and practical scope). **In use, it vanishes**.
3. 💡 Alternatively, and usually when something has gone wrong with it, the user may experience a tool as _vorhanded_ ("present-at-hand"). The user is no longer able to proceed toward his goal but must deal first with the tool, without it doing anything to move him toward his goal.
4. 💡 Finally, ask yourself the following questions:
   1. Are your system architected to be invisible in use?
   2. Does the user interface fall naturally to hand?
   3. Or do your system keep demanding attention, distracting users from their goal?

### 90. Find and retain passoinate problem solvers.

1. ❗ Putting together a team of outstanding developer is one if the most important things you can do to ensure the success of a software project. Therefore, you to need to carefully select your development team and diligently protect it once assembled.
2. 💡 You are searching for developers with problem-solving skills and passion. You need people who are good at attacking problems regardless of the technologies involved. Asking them about past experience will bring out that passion and tell you what correct answers to technical trivia questions cannot.
3. 💡 Good developers are often strinly motivated by recognition. Finding great developers is difficult; letting people know they are values is not. Don't miss simple chances to build morale and boost productivity.
4. 💡 Good developers are smart; they know they're not wrong all of the time. If you're picking apart the minutiae of their work, you'll lose their respect. Keep critisism constructive and don't require that every solution look like it came from you.

### 91. Software doesn't really exist (Chad LaVigne).

1. ❗ While applying engineering principles to the software design phase works well, assuming you can implement the design in the same manner used by more traditional engineering approaches in unrealistic.
2. 💡 Engineering endeavors of the physical flavor are much easier to implement in a "plan the work, work the plan" nature. With software, things need to tackled in more of a "plan the work, massage the plan" fasion.
3. 💡 As architects, we are very aware of the "soft" nature of our craft and we like to solve problems. Worse yet, the business owners are vaguely aware of these facts. This makes it easy for them to push big changes.
4. 💡 The virtual objects that we create are easier to change than their physical-world counterparts, which is a good thing because many times they're required to. It's OK to plan as though we're building an immovable objects; we just can't be surprised or unprepared when we're asked to move said object.

### 92. Learn a new language (Burkhardt Hufnagel).

1. ❗ To be successful as an architect, you must be able to make yourself understood by people who don't speak your native tongue. So you should at least speaл basic Business, and Testing. And, if you aren't fluent in Programmer, you should make that a top priority.
2. 💡 It's basic psychological principle that people are more comfortable with those who are similar to them than those who are different from them.
3. 💡 Architect should be able to explain the issues to the business folk in terms they understand and relay the business issues to the programmers in terms they understand. Instead of surprise and mistrust, the result would be agreement and approval.

### 93. You can't future-proof solutions (Richard Monson-Haefel).

1. ❗ Today's solution is tomorrow's problem. It's simply not possible to future-proof architecture. No matter what architectural decision you make now, that choice will become obsolete eventually.
2. 💡 If any choice you make today will be a bad choice in the future, then don't worry about what the future will hold - choose the best solution that meets your needs today.
3. 💡 Choosing a good technology for right now is hard enough; choosing one that will be relevant in the future is futile.
4. 💡 Look at what your business needs now. Look at what the technology market offes now. Choose the best solution that meets your needs now, because anything else will not only be wrong choice tomorrow, but the wrong choice today.

### 94. User acceptance problem (Norman Carnovale). 

1. ❗ People aren't always happy about new system or major upgrades. This can pose a threat to the successful completion of a project.
2. ❗ Your goal as an architect is to be aware of and measure the threat of acceptance problems and work toward mitigation those threats.
3. 💡 Know the reasons for problems. Some of the more common ones are:
   1. People may have concerns about the need for a new system.
   2. People fear new (unproven) technology.
   3. People have cost/budget concerns.
   4. People simple do not like changes.
4. 💡 Some of the problems you can address and others you can't. You have to recognize the difference and deal quickly with those that you can:
   1. Discuss the new system and changes with your end users. Use the design of the system itself if needed.
   2. Scheudle demonstrations and knowledge sharing.
   3. Add "project chamption" into the team. Ideally this should be a person that represents the user group or stakeholders.

### 95. The importance of consomme (Eben Hewitt).

1. ❗ A consomme is an extremely clarified broth, usually made with beef or veal, served as a delicate soup. The absolute clarity requires simple, fine-grained straining repeated again and again.
2. ❗ Software architecture requires a continual refinement of thought, a repeated straining of ideas until we have determined the essence of each requirement in the system.
3. 💡 Many missed requirements and bugs in software can be traced to ambiguous, general language. Ask everyone the same questions repeatedly, until they are drowsy boredom. Strain and strain again.
4. 💡 Bring surgical precision to the language you find in your requirements, rejecting ambiguity, generality, unwarranted assumptions, or extraneous verbiage. This serves to make your concepts richer, more robust. Reduce and reduce again.
5. 💡 Test statements by asking "Would you make the same statement if I appended 'always and forever and in every circumstance' to it"? Do this again, until you are left with only the exhaustive list of simple and verifiable true statements that describe the essential nature of the system.

### 96. For the end user, the interface is the system (Vinayak Hedge).

1. ❗ There are too many good products hidden behind bad user-interfaces.
2. 💡 The architect should enlist the services of specialists such as user experience designers and usability experts. Involving them at an early stage and thoughout the product development phases ensures that the final product is polished, and the integration of user interface with the product is seamless.
3. 💡 User interactions should be one of the goals of the complete product architecture. In fact, user interaction should be an integral part of the decision-making process for architecture tradeoffs and internal product documentation as much as robustness and performance.
4. 💡 It is the architect's responsibility to make the most common interactions not only easy but also rewarding for the end user. Better user interfaces lead to happier customers, which helps improve customer productivity. If your product helps people become more productive, then it will contribute to the business's bottom-line.

### 97. Great software is not built, it is grown (Bill de hOra).

1. ❗ Even though we are called architects, we borrow many metaphors from building and engineering, great software is not built, is it grown.
2. ❗ The single biggest predictor of software failure is size; on reflection there's almost no benefit to be had from starting with a large system design.
3. 💡 Have a grand vision, but not a grand design. Let you and your system learn to adapt as the situatin and requirements inevitably change.
4. 💡 The best way to ensure that a software system can evolve and adapt is to evolve and adapt it from the very outset. Inducing a system to evolve means starting with a small running system, a working subset of the intended architecture - the simplest thing that could possible work.
5. 💡 Design the smallest system you can, help deliver it, and let it evolve toward the grand vision. 
6. 💡 Do not confuse an evolutionary approach with throwing requirements out, the dreaded phasing, or building one to throw away.
