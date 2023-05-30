# [97 Things Every Programmer Should Know](https://www.amazon.com/Things-Every-Programmer-Should-Know/dp/0596809484)

❗   -   point of attention, 📖  -   definition, 💡  -   solution point, * - editor's extra point.

### 1. Act with prudence (Seb Rose)

1. ❗ If you find yourself having to choose between "doing it right" and "doing it quick" it is often appealing to "do it quick" with the understanding that you'll come back and fix it later.
2. 📖 This sort of deferred work is known as **deliberate technical debt** by Martin Fowler, and it should not be confused with **inadvertent technical debt**.
3. ❗ Technical debt is like a loan: you benefit from it in the short term, but you have to pay interest on it until it is fully piad off.
4. 💡 Try to avoid technical debt, 
5. 💡 If the situation absolutly demands technical debt, then go ahead, **BUT**:
    1.  **Visualize it** - write a task card or log it in your issue-tracking system.
    2.  **Pay it off as soon as possible** - include the most actual technical debts into each iteration or sprint.

### 2. Apply futional programming principles (Edward Garson)

1. ❗ A leading cause of defect in imperative code is attributable to mutable variables.
2. 📖 Functional paradigm implies high degree of **referential transparancy**, - functions consistently yield the same result given the same input, irrespective of where and when they are invoked. That is, function evaluation depends less - ideally, not at all - on the side effects of mutable state.
4. 💡 With astute test-driven design, particularly when being sure to "Mock Roles, not Objects", unnecessary mutability can be designed away.
5. 💡 Master functional programming paradigm so you are able to judicously apply the lessons learned to other domains.
6. 💡 In fact, some would event assert that, at their apex, functional programming and object orientation are merely a reflection of each other, a form of computational yin and yang.


### 3. Ask, "What would the user do?" (You are not the user) (Giles Colborne)

1.  📖 We all tend to assume that other people think like us. But they don't. Psychologists call this the _false consensus bias_.
2. ❗Users don't think like programmers. They neither know nor care how a computer works. They don't recognize the patterns and cues programmers use to work with, through, and around an **interface**.
3. 💡 The best way to find out how a user thinks is to watch one. Spending an hour watching users is more informative than spending a day guessing what they want.
4. 💡 Provide one really obvious way of doing things than two or three shortcuts.
5. 💡 Work with an UI/UX expert.*

### 4. Automate your coding standard (Filip van Laenen)

1. ❗ At the beginning of a project, everybody has lots of good intentions - call them "new project's resolutions". But when the project is finally delivered, the code looks like a mess, and nobody seems to know how it came to be that way. The reason is that the coding standard was not in the first place.
2. 💡 Automate your coding standard and enforce where possible:
    1. Make code formatting is part of the buld process.
    2. Use static code analysis tools.
    3. Measure test coverage and check test results, break the build if it fails.
3. 💡 Remember, that the coding standard should be dynamic rather than static.

### 5. Beauty is in simplicity (Jorn Olmheim)

1. 📖 "Beauty of style and harmony ang grace and good rhythm depends on simplicity", Plato.
2. ❗ There are number of things we strive for in our code: **Readability**, **Maintainability**, **Speed of development**, **The elusive quility of beauty**. Plato is telling us that the enabling factor for all of these quilities is simplicity.
3. 💡 If you haven't spent time studing other people's code, stop reading this right now and find some open source code to study.
4. 💡 No matter how comples the total applicaion or system is, the individual parts have to be kept simple. Strive for short methods of 5-10 lines of code even if it sounds extreme for you.
5. 💡 The bottom line is that beautiful code is simple code.

### 6. Before you refactor (Rajith Attapattu)

1. ❗ Before you refactor, please think about the following, as this could save you and others a great deal of time (and pain).
2. ✔️ Dos:
    1. Understand the strengths and weaknesses of the code as it currently stands, so you ensure that you retain the strong points while avoiding the mistakes.
    2. Avoid the temptation to rewrite everything.
    3. Do many incremental changes rather than one massive change.
    4. Ensure that the existing tests pass and the new ones are written.
3. ❌ Don'ts:
    1. Don't allow personal preferences and ego get in the way.
    2. Don't refactor just because of a new technology.

### 7. Beware the Share ((Udi Dahan)

1. Check the context before reuse.
2. Wrong reuse decreases the absolute number of lines of code, but increases the number of dependencies (coupling).
3. Reuse only in the right context.

### 8. The Boy Scout Rule (Robert C. Martin)

1. 💡 Always leave the campground cleaner than you found it. 
2. If follow this rule, the system would gradually get better and better as it evolves.
3. Teams should help one another and clean up after one another.

### 9. Check Your Code First Before Looking to Blame Others (Allan Kelly)

1. ❗Developers have trouble believing our own code is broken.
2. Given how rare compiler (external lib/dependency/system) bugs are, you are far better putting your time and energy info finding the error in your code than into proving that the compiler is wrong.
3. 💡 Question your own assumptions and assumptions of others.
4. 💡 Simplicity of design is paramount.
5. 💡 Remember Sherlock Holmes's advice, "Once you eliminate the impossible, whatever remains, no matter how improbable, must be the truth."

### 10. Choose your tools with care (Giovanni Asproni)

1. 💡 When choosing a tool, known the context assumed by it to avoid architectual mismatch.
2. ❗ Be aware of a tool's:
    1. upgrading effort
    2. configuration complexity
    3. vendor lock-in
    4. licensing terms
3. 💡 Start small by using the tools that are absolutly necessary. 
4. 💡 Focuse on removing the need to engage low-level infrastructure programming.
5. 💡 Isolate the external tools from business domain.

### 11. Code in the Language of the Domain (Dan North)

1. ❌ Don't bare/primitive types to declare domain logic.
2. 💡 Use user-defined types with domain-related methods.
3. 💡 Use domain terms to model relationships.
4. 💡 Make domain concept explicit. That is, make domain more visible.

### 12. Code Is Design (Ryan Brush)

1. ❗ If construction cost were almost rezo in civil engineering, we were living in partialy finished or broken buildings. Because design time was sucrifised to gain an edge in the market.
2. Consturction cost is more easily calculated than design cost. 
3. Less consturction cost leads to less design quality.
4. That is how design or software crisis explained: validated design vs capacity to create it and pressure.
5. 💡 Design isn't complete until it is fully validated and tested.

### 15. Coding with Reason (Yechiel Kimchi)

1. Reason semiformally about code correctness.
2. 💡 Limit the scope to reason about using smaller functions (up to 24 lines) and fewer parameters (up to 4).
3. 💡 Reason about preconditions, postconditions, invariants.
4. 💡 Use immutable variables whenever relevant.
5. 💡 Make narrow interfaces.
6. 💡 Argue about your code with peer programmers to better understand it.

### 17. Comment Only What the Code Cannot Say (Kelvin Henney)

1. 💡Delete parroting comments.
2. 💡Delete commented-out code.
3. 💡Treat comments as though they were code.
4. 💡Code should speak for itself:
    1. Instead of compensating for poor method or class names, rename them.
    2. Instead of commenting sections in long functions, extract smaller functions with descriptive names.
5. 💡Comment what the code _cannot_ say, not simply what it does not say.

### 19. Convenience Is Not an -ility (Gregor Hohpe)

1. Good API
    1. follows a consistent level of abstraction
    2. exhibits consistency and symmetry
    3. forms the vocabulary for an expressive language
2. Design for convenience of the caller, not of the implementor.
3. 💡Don't design API like a puzzle, but rather like LEGO Duplo (by Sofya Dorozhanskaya)*.

### 20. Deploy Early and Often (Steve Berczuk)

1. ❗ Do not put deployment process off until it may be too late to make changes.
2. ❗ Until you can demonstrate your application on the target environment, there is a lot of work to do before you can deliver business value.
3. 💡 Start your project with an installation/deployment process and evolve it as you go.
4. 💡 Test and refactor this process as you do the source code.

### 21. Distinguish Business Exceptions from Technical (Dan Bergh Johnsson)

1. 📖 Technical exceptions are programmer error. Bubble up technical exceptions to the general exception-handling mechanism.
2. 📖 Business exceptions are alternative return paths. Clients should handle them on their own terms.
3. 💡 Create a specific exception type or a separate exception hierachy and make it part of contract.
4. 💡 Don't mix technical and business exception in the same 

### 23. Domain-Specific Languages (Mickael Hunger)

1. 📖 Domain-specific language (DLS) is a specific vocabulary to describe the things that are paricular to that domain.
2. 📖 There two types of DLSs:
    1. Internal - written in a general-purpose programming language, e.g. HTML builder in Kotlin.
    2. External - textual or graphical expressions of the language, e.g. DOT for graphs, PantUML for UML.
3. 💡 Build or/and use DSL(s).
4. 💡 Always take target audience of your DSL into account.
5. 💡 Do not expose technical implementation details.

### 24. Don't Be Afraid to Break Things (Mike Lewis)

1. ❗ A paralyzing fear of change is what got your project into precarious at best state to begin with.
2. ❗ Working on a system you hate is not how anybody should have to spend his time.
3. 💡 Slowly refactor your code, testing along the the way. Don't try to accomplish a large refactoring in "one big shebang".
4. 💡 Be the sergeon who isn't afraid to cut out the sick parts to make room for healing.
5. 💡 Track refactroing tasks. Convince management that even though these tasks may not produce visisble results, they will reduce expenses and expedite future releases.
6. ❗ **Never stop caring about the general health of the code.**

### 27. Don't Just Learn the Language, Understand Its Culture (Anders Noras)

1. 💡 Learn a new programming language every year. ❗ But it takes more than just learning the syntax: you need to understand its culture.
2. 💡 Once you've learned the ropes of a new language, you'll be surprised how you'll start using languages you already know in a new ways.
3. 💡 Explore new languages to expand your mind and get fresh ideas on how you can solve things in different ways.

### 30. Don't Repeat Yourself (Steve Smith)

1. ❗ One piece of knowledge - one representatino within a system.
2. 💡 Dry your code with removing duplications.
3. 💡 Dry your process with automation.
4. 💡 Dry your logic with abstractions and and patterns.
5. 💡 Dry only actual rather than an imagined problems.

### 31. Don't Touch That Code! (Cal Evans)

1. ❗Never fix bugs directly on staging or production servers.
2. ❗Nobody should never have access beyond the development servers.
3. 💡A bug identified on production should be:
    1. Fixed locally
    2. Deployed on development server
    3. Tested on QA server
    4. Acceoted on staging server
    5. And only after that deployed on production server
4. ❗The release manager is the only person who should have an access to production server.

### 32. Encapsulate Behavior, Not Just State (Einar Landre)

1. Domain object should encapsulate state and behaviour.
2. Behaviour is defined by the state.
3. Using CustomerService to manipulate state of Order record that is not OO desing, but rather just procedual one.
4. Use the power of your language to implement and maintain encapsulation withing objects.

### 33. Floating-Point Numbers Aren't Real (Chuck Allison)

1. ❗ Floating-point numbers have limited precision, so they are (1) finit and (2) not evenly spaced throughout their range.
2. 📖 Since floating-point numbers are approximations of real numbers, there is inevitable a little error present called _roundoff_.
3. ❗ You shouldn't use floating-point numbers for financial applications.
4. ❗ Floating-point numbers are intended for efficient scientific computation, but it's worthless without accuracy, so remember the source of rounding errors, and code accordingly.
 
### 35. The Golden Rule of API Design (Michael Feathers)

1. 💡Test not only your API, but also it's clients to make it easer to use.
2. Write test clients to your API.

### 36. The Guru Myth (Ryan Brush)

1. ❗ When asking others for help privde the full context and don't expect them to be guru and don't expect magic.
2. 📖 A "guru" is a simply smart person with relentless curiousity and who spent years learning and refining throught process.
3. 💡 We don't need gurus. We need experts willing to develop other experts in their field. 

### 38. How to Use a Bug Tracker (Matt Doar)

1. ❗ A good bug tracker report needs to convey:
    1. How to reproduce the bug
    2. What should happen
    3. What actually happens
2. 💡 A bug with plenty of context to make it easier to reproduce earns the respect of everyone, even if it stops a release.
3. ❗ Exmplain in comments why you think the bug should be closed or the priority changed.
4. 💡 A bug is _not_ a standard unit of work any more than a line of code is a precise measurement of effort.

### 39. Improve Code by Removing It (Pete Goodliffe)

1. ❗ A small, extra bit of code snowballs over time into a large piece of work that needs maintenance.
2. 💡 Remember YAGNI: You Aren't Gonna Need It. In order words, if you don't need it right now, you don't write it right now.
3. 💡 Write code because it adds value, not because it amuses you.
4. ❓ What are you working on right now? Is it all needed?

### 41. Interprocess Communication Affects Application Response Time (Randy Stafford)

1. ❗ Data structures and algorithms related issues are far less likely to dominate performance in modern multitier enterprise applications.
2. ❗ Response time depends most strongly on the number of remote interprocess communications.
3. 💡 Reduce the number of remote IPCs by:
    1. Principle of parsimony: only the right data at hand is exchanged with the minimum amount of interaction.
    2. Parallalize IPCs.
    3. Use cache.

### 42. Keep the Build Clean (Johannes Broadwall)

1. ❗ Keeping the build clean is not just about keeping it free of compilation errors or test failures: warnings are also an important and critical part of code hygiene.
2. ❗ Warnings are useful: you just need to get rid of the noise to start noticing them. 
3. ❗ Otherwise you will have to decide that a warning is irrelevant every time you encounter it. Ignoring things is mental work, and you need to get rid of all of the unnecessary mental work you can.
4. 💡 Use a zero-tolerance policy for warnings. When they appear, deal with them right away: fix the source of the warning or supress the warning.

### 43. Know How to User Command-Line Tools (Carroll Robinson)

1. ❗If an IDE is the only programming environment that you ever use, you may never fully understand what your tools are actually doing.
2. 💡Look under the hood and understand what your IDE is doing for you learning to use command-line tools.
3. 💡Automate repetitive tasks using command-line tools and stepping out of IDE.

### 44. Know Well More Than Two Programming Languages (Russel Winder)

1. ❗ Programming expertise is related directly to the number of different programming paradigms that a programmer is comfortable and can genuinely program with.
2. 📖 Paradigms are: procedual, object-oriented, functional, logic, dataflow, etc.
3. ❗ Trying to port the idioms from one language to another teaches us about both languages and about the problem being solved.
4. ❗ Be well skilled in programming in at least two different paradigms and ideally at least the aforementioned five.

### 45. Know Your IDE (Heinz Kabutz)

1. ❗ Modern IDE's do not require us to invest effort to learn how to use them so we never progress beyond the most basic usage of the tool.
2. ❗ Know and use automated refactoring features provided by your IDE.
3. ❗ Know shortcuts of your IDE not to switch the context while coding.
4. 💡 We expect plumber coming to our house to be able to use his blowtortch. Let's spend a bit of time to study how to become more effective with our IDE.

### 46. Know Your Limits (Greg Colvin)

1. ❗ Your resources are limited (e.g. you only have so much time and money to do your work, your tools and machines are only so powerful).
2. ❗ Respect those limits: know yourself, know your people, know your budgets, and know your stuff.
3. ❗ Know the space and time complexity of your data structures and algorithms.
4. ❗ Know the architecture and performance charactiristics of your systems.
5. 💡 Do testing and measuring to know the limits.

### 47. Know Your Next Commit (Dan Bergh Johnsson)

1. ❗ Know your next commit or a task are we able to finish within next 2 hours.
2. ❗ Do not commit guesswork into your repository.
3. 💡 If you cannot finish, throw away your changes, then define a new task you believe in with the insights you have gained.
4. 💡 Do speculative experimentation whenever needed, but do not let yourself slip into speculative mode without noticing.

### 48. Large, Interconnected Data Belongs to a Database (Diomidis Spinellis)

1. ❗ Don't hesitate to store a large, persistent, interconnected set of data elements in a relational database.
2. 💡 Embedded database systems can be linked as libraries directly into your application, requiring almost no setup or management (SQLite, HSQLDB).
3. 💡 With database you can describe consistency constraints on your data in a declarative way, avoiding the risk of the dangling pointers you get if you forget to update your data in an edge case.
4. 💡 RDBMS will sweat hard to optimize your SQL commands, allowing you to concentrate on your application's functinoality rather than on algorithmic tuning.

### 49. Learn Foreign Languages (Klaus Marquardt)

1. ❗ Learn programming languages: stand outside your daily routine and be aware of other languages that are expressive for other purposes.
2. ❗ Learn people foreign languages: speaking a language well leads to a clarity of thought that is indispensable when abstracting a problem.
3. ❗ Learn language of your domain and non-technical users, master domain specific languages.

### 51. Learn to Say, "Hello, World" (Thomas Guest)

1. 💡 It's never too late to run a simple program that does a simple task to reason about the big one.

### 52. Let Your Project Speak for Itself (Danial Lindner)

1. ❗ Delegate checking build metrics (test coverage, static code analysis) to the project itself and rely on it to report when things get worse.
2. 💡 Give you project a voice to complain to or praise developers according to the rules the team has chosen.
3. 💡 Embody the project in your office by using an _extreme feedback device_.

### 53. The Linker Is Not a Magical Program (Walter Bright)

1. All linker does is
    1. Concatenate together the code and data sections of the object files
    2. Connect the references to symbols with their definitions
    3. Pull unresolved symbols out of the library
    4. Write out an executable
2. [Details](https://courses.engr.illinois.edu/cs232/sp2009/lectures/Examples/lecture6/lecture6.html)

### 54. The Longevity of Interim Solutions (Klaus Marquardt)

1. ❗ Interim solutions are ultimately useful with a problem at hand, but when system contains too many of them, its entropy or internal complexity grows and its maintainability decreases.
2. 💡 Try to avoid creating an interim solution in the first place.
3. 💡 If you can not, then have:
    1.  Serenity to accept things you can not change.
    2.  Courage to change things you can.
    3.  Wisdom to know the different between 1 and 2.
4. 💡 Make interim solutions superflous providing a more elegant and useful solution.

### 55. Make Interfaces Easy to Use Correctly and Hard to Use Incorrectly (Scott Meyers)

1. Right interface is a pleasure to use and will boost others' productivity. Poor interface is a source of frustration and errors.
2. Make interface easy to use correctly.
3. Anticipate mistakes and make them difficult (better impossible) to commit.
4. Excercise interfaces first using mockups, client tests (remember Golden Rule of API Design).
5. If users or clients keep passing the wrong value to an API, do your best to modify the API to take the values that users want to pass.
6. Observe interfaces misuse on early stages.

### 56. Make the Invisible More Visible (Jon Jagger)

1. ❗ Software and the process of software development are the mostly invisible. invisibility can be dengerous. 
2. 💡 We think more clearly when we have something concrete to tie your thinking with.
3. 💡 We manage things better when we can see them and see them constantly changing:   
    1. Write unit tests to make developmental qualities of the code visible.
    2. Run unit tests to make runtime qualities visible.
    3. Use bulletin boards and cards to make progress visible.
    4. Do incremental development to make the development progress visible.

### 57. Message Passing Leads to Better Scalability in Parallel Systems (Russel Winder)

1. ❗What makes concurrent computing hard is shared memory.
2. Forgoing concurrency is not an option, because we want to harness true parallelism to improve application performance.
3. 💡Don't programm with shared memory, but instead use message passing.

### 58. A Message to the Future (Linda Rising)

1. ❗ Most of the programmers think that since the problems they are striggling with are difficult, the solutions should be just as difficult for everyone to understand and maintain. 
2. 💡 But they shouldn't.
3. 💡 Think of every line of code you write as a message for someone in the future - someone who might be your younger brother.
 
### 59. Missing Opportunities for Polymorphism (Kirk Pepperdine)

1. The word, taken from Greek, means many (poly) forms (morph). In the context of programming, polymorphism refers to many forms of a particular class of objects or method.
2. Use polymorphism to reduce verbose if-then-else blocks.
3. Use polymorphism to create tiny localized execution contexts in order to do the right thing directly.

### 60. News of the Weird: Testers Are Your Friends (Burk Hufnagel).

1. ❗ Programmers often have an adversarial relationship with the people who test their software.
2. 💡 Testers are not developers' enemies, they are friends.
3. 💡 Let a bug be found by QA, not customer.
4. 💡 Even more, picky testers are your best friends.

### 62. Only the Code Tells the Truth (Peter Sommerlad)

1. ❗ Documentation, comments, requirements can not express the ultimate semantics of a program as the code can.
2. 💡 Communicate your intention through the code directly.
3. 💡 If your code needs comments, consider refactoring it so it doesn't.
4. 💡 Strive for good names.
5. 💡 Decouple your code to achieve orthogonality.
6. 💡 Refactor mercilessly.

### 63. Own (and Refactor) the Build (Steve Berczuk)

1. ❗ Do not neglect build scripts. 
2. ❗ Unmaintainable build scripts with duplication and errors cause problems of the same magnitude as those in poorly factored code.
3. ❗ The build process needs to be owned by the development team to deliver value predictably.
4. ❗ The job of programming is not complete until we have delivered working software.
5. 💡 Apply the same idioms and practises for build scripts as you do for your source code.

### 65. Prefer Domain Specific Types to Primitive Types (Einar Landre)

1. 💡 The code becomes more readable, as it expresses concepts of a domain, not just Float and String.
2. 💡 The code becomes more testable, as the code encapsulates behaviour that is easily testable.
3. 💡 The code facilitates reuse across applications and systems.

### 66. Prevent Errors (Giles Colborne)

1. ❗ Prevent errors early rather than fix them later.
2. 💡 Respect user's preference to enter information, not your data.
3. 💡 Give cues in the appropriate contexts.
4. 💡 Be tolerant of errors providing multiple levels of _undo_ functionality.
5. 💡 Log and analyze undo actions.

### 67. The Professional Programmer (Robert C. Martin)

1. ❗ Take personal responsibility for your workmanship.
2. ❗ Leave nothing for QA to find.
3. ❗ Never ever rush.
4. ❗ Do not abandon your principles when deadlines loom.

### 68. Put Everything Under Version Control (Diomidis Spinellis)

1. ❗ Place all the project's asets under a version control system.
2. ❗ Commit each logical change in a separate operation.
3. ❗ Accompany each commit with an explanatory message.
4. ❗ Never commit code that will break a project's build.

### 71. Read the Humanities (Keith Braithwaite).

1. ❗ Learn how to deal with people we work for and with.
2. 💡 Be on the guard against misunderstanding when gather requirements.
3. 💡 A tool becomes an invisible thing understood only in use. For users, tools become objects of interest when they don't work.

### 73. Resist the Temptation of the Singleton Pattern (Sam Saariste)

1. Experience shows that most singletones really do more harm than good.
2. Singletons cause implicit dependencies between conceptually independent units of code.
3. Singletons carry implicit persistent state.
4. Singletons doesn't fit well into multithreaded execution environment.
5. Even if you use singletones, don't access it from global static context, instead depend on interfaces via dependency injection mechanism.

### 74. The Road to Performance Is Littered with Dirty Code Bombs (Kirk Pepperdine)

1. ❗ Performance tuning a system requires you to alter code. Every chunk that is overly complex or highly coupled is a dirty code bomb lying in wait to derail the effort.
2. 💡 Measure and control the degree and depth of coupling and complexy of code.
3. 💡 Use _fan-in_ and _fan-out_ metrics for a class:
    1. Fan-in _Fi_ - number of classes referenced either directly or indirectly from a class of interest;
    2. Fan-out _Fo_ - number of all classes that depend upon the class of interest.
    3. Instability _I_ = Fo / (Fi + Fo)
4. 💡 The goal of refactoring is to move _I_ closer to 0 with some balance applied.

### 75. Simplicity Comes from Reduction (Paul W.Homer)

1. ❗Once something becomes a resource sink, it needs to be discarded. Quickly.
2. 💡 The best approach to fixing bad code is to flip into a mode where the code is mercilessly refactored, shifted around, or deleted.
3. 💡 Extra lines, extra variables...extra _anything_ should be purged immediatly.
4. 💡 If you can not refactor the code, delete it all and type again. 

### 78. Step Back and Automate, Automate, Automate (Cay Horstmanm)

1. ❗ Step back and take the time to automate tasks, instead of doing them over and over again.
2. 💡 Automation makes executing tedious tasks faster and more reliable.
3. 💡 Automation systems give control and repeatability.
4. 💡 If a task is challenging to automate, make a slight tweak in the process. For example, intead of working with Word files, use plain text.
5. 💡 Start with small things and learn as you go. Once you have been successful, you will see that it makes sense to invest in automation.

### 79. Take Advantage of Code Analysis Tools (Sarah Mount)

1. ❗ Don't let testing be the end of your quality assurance - take advantage of analysis tools.
2. 💡 Don't be afraid to roll your own code analysis tool.

### 82. Test While You Sleep (and over Weekends)

1. ❗ How much computer power do we have at our disposal that we are not harnessing to make our lives as programmers a little easier?
2. 💡 Break down tests into two or more profiles:
    1. A smaller, mandatory test profile that is quick to run before each commit.
    2. A bigger, long-running test profile that is automated to run overnight.
3. 💡 Long running tests that keep the system under ther load will help to identify specific issues like memory leaks.
3. 💡 Run such automated tests during the night and over weekends.

### 84. Thinking in States (Niclas Nilsson)

1. ❗ There is a need for good state handling.
2. 💡 Understand [state machine](https://en.wikipedia.org/wiki/Finite-state_machine).
3. 💡 Use [State](https://refactoring.guru/design-patterns/state) pattern.
4. 💡 Read up on [Design by Contract](https://en.wikipedia.org/wiki/Design_by_contract) to ensure a valid state by validating incoming data and the object itself on entry and exit of each public method.

### 87. Ubuntu Coding for Your Friends (Aslam Khan)

1. ❗ Lift the head more often.
2. ❗ Think about others working with your code: the quality of code you write affects the quality of the code you write.
3. ❗ Code for your team or friends.
4. ❗ Know Ubuntu/Zen principles.

### 88. The Unix Tools Are Your Friends (Diomidis Spinellis)

1. ❗ You should become proficient with Unix tools, not only IDE.
2. 💡 IDEs target specific languages, while Unix tools can work with anything that appears in textual form.
3. 💡 Sharpening your Unix tool skills makes you more effective at any task.
4. 💡 Unix commands executing as pipelines will naturally distribute their load among the many processing units of modern multicore CPUs.
5. 💡 The small-is-beautiful provenance and open source implementations of the Unix tools make them ubiquitiously available.

### 89. Use the Right Algorithm and Data Structure (Jan Christiaan "JC" van Winkel)

1. ❗ Have knowledge of the problem domain and of algoritms and data structures.
2. ❗ Know when, what and how to reuse.
3. ❗ Know when to use an abominal algorithm depending on a problem domain (e.g. the number of dice in a Yahtzee game can never be more than five).

### 90. Verbose Logging Will Disturb Your Sleep (Johannes Broadwall)

1. ❗ Make sure from day one that errors are in noise-free error log.
2. ❗ Make sure that your logging policy takes into account external dependency failing.
3. ❗ Write about one INFO-level log message for every significant application event.
4. 💡 If you don't expect anything to show up in the error log, it will be much easier to know what to do when something does show up.

### 91. WET Dilutes Performance Bottlenecks (Kirk Pepperdine)

1. ❗ Every piece of knowledge in a system should have a singular representation (DRY).
2. 📖 Code is WET (write every time) when knowledge is codified in several different implementations.
3. 💡 With WET, we have 10 different implementations that we need to find and fix. With DRY, we would have a tenth of the code to fix.

### 93. Write Code As If You Had to Suport It for the Rest of Your Life (Yuriy Zubarev)

1. ❗ Care about your career and every body around you (devlopers, QAs, users, etc) with every line of code. 
2. ❗ People form opinions about you based on the code that they see.
3. 💡 Gradually improve toward becoming an expert programmer.

### 94. Write Small Functions Using Examples (Keith Braithwaite)

1. ❗ We would like to write code that is correct, and have evidence on hand that it is correct.
2. 💡 Use smaller functions, but it's not about lines of code, but rather about the size of mathematical function that it manifests.
3. 💡 Use concrete types to decrease Cartesian product of the sets of the function's input and output parameters.
4. 💡 Find the examples to check in problem domain terms.

### 96. You Gotta Care About the Code (Pete Goodliffe)

1. ❗ Good code is not free. You have to work at it. Hard.
2. ❗ The real difference between adequate programmers and great programmers is this: _attitude_.
3. ❗ Attitude implies:
    1. Writing discoverable maintainable, correct and clean code;
    2. Team collaboration;
    3. Boy scout rule;
    4. Continious learning.

### 97. Customers don't mean what they say (Nate Jackson)

1. ❗ Customers don't always tell us the truth, because they speak in their own terms and contexts, they don't provide significate details.
2. 💡 Challange your customers early and often.
3. 💡 Don't start your crafting before yoy hash out all uncovered and contradictive topics.
4. 💡 Use visual aids - it helps to lengthen our attention span and increases the retention rate of the information.
