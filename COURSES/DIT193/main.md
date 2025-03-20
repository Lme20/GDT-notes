# AGILE DEVELOPMENT PROCESSES

## LEC 0 - INTRO

### V-model

### claimed benefits of Agile

- Responsiveness
- Transparency
- Business
- Team
- Speed
- Quality

**Challenges with agile: 'Transformation':**

- transitioning from one mode of work  to Agile
- core company values at odds with Agile practices
- Lack of experience with agile methods
- Insufficient training
- Lack of management support

### core principles of agile

'You get what you test'

- backlog handling
- empowered team
- continous integration

We develop in protected and dedicated cross-
functional teams picking work from ONE
prioritized backlog and testing it continuously.

We are transparent with what we do and the
team is trusted to take every needed action to
deliver value in small steps.

- Values:
- Principles:
- Roles:
- Practices:
- Artifcacts:

read 4 (agile principles), 6(agile principles: managerial), 7 (agile principles: technical)

## LEC 1 - Agile basics

**Other non-agile methodologies**

- v-model
- waterfall

**agile methodologies**

- Scrum
- Lean
- Extreme Programming (XP)
- Kanban
- Future-Driven Development (FDD)

### Requirements

### group project

- user friendly UI
- at least 3 different features
- 3 sprints, 2 weeks each (at least 1 functionality per sprint)
- deliverables: project document, DoD, social contract
- project document: primary features and functionalities, initial backlog, user stories, MVP criteria, define coding standards and architecture, establish communication channels, establish timeline for project
- scrum practices: sprint planning, meetings, sprint reviews, sprint retrospectives, sprint backlog, story point estimations, burndown chart
- grading crtieria: sprint reports (brief, concise), satisying MVP, quality of final product, test strategy, KPIs, presentation, discussion with opponent

# AGILE NOTES

- stakeholder representation:
- team roles:
- how practices interplay:
- multitasking is considered wasteful and a source of delays in agile/lean
- agile emphasises frequent testing at multiple levels (unit, integration, system, and acceptance)
- continious delivery: the ability to release software whenever we want
- continous deployment: the ability to release and install software in a running system whenever we want

**Challenge:**

- agile teams often have issues finding a domain expert customer proxy
- time availability + domain expertise are both needed

**Advantages:**

**Basics**

- sprint planning:
- sprint retrospectives:
- standups:
- sprint reviews
- sprint backlogs:
- story point estimation techniques:
- burndown chart:
- product backlog:
- DoD:
- Agile roles:
- Velocity:
- Backlog refinement (grooming):
- INVEST criteria:
- Iterative & Incremental delivery:
- Continious Integration/Continous Delivery (CI/CD):
- release planning:

- Agile mindset/principles: embrace change, collaboration, transparency, continous improvement, simplicity, continous delivery, interdesciplinary collaboration between developers and business people, emphasis on individual support and trust, emphasis on face-to-face meetings, sustainable development, self-improvement of teams.

## Agile methodologies and practices

### Extreme programming (XP)

### Scrum

### Lean

- deliver value while minimizing waste

- **value stream mapping**
- visualise entire production or delivery process
- identify which steps add value and which do not
- spotting bottlenecks, waste, and opportunities for improvement

### Kanban

### Scrumban

### Future-Driven Development (FDD)

## Agile prioritization

### Decomposing user stories

decomposing allows for:

- better estimations
- reduces risk with early feedback
- ensures each slice delivers actual value to users
- simplifies understanding of requirements
- distributes workload more evenly

**vertical decomposition**

- slices the user story into complete pieces that span all necessary layers
- each slice delivers a functional increment

**horizontal decomposition**

- breaks up user stories by technical layers
- each slice covers one layer and does not deliver functionality on its own

### WSJF (Weighted Shortest Job First)

## Product Planning

### Kano model -- impact on user satisfaction

Classifies product features based on how they impact user satisfaction.

- **must-be (basic) features:** essential elements that users take for granted
- **performance (one dimensional) features:** features where improvements result in directly proportional increases in satisfaction
- **Excitment (Attractive) features:** Unexpected features that delight the users.
- **indifferent features:** Features which have little to no effect on the users, or even features that reduce user satisfaction

**used in:**

- early stages of product development, particularly in product requirements
- Prioritizes features on a product map according to how likely these are to satisfy a customer based on their absence or presence

## Agile simulations/miniatures

- short condensed exercises to mimick full agile project lifecycles in a limited time frame

**How they work:**

1. Teams go through planning, iterative development, testing and feedback cycles in quick succession

- This involves using paper prototypes or lego bricks to simulate the development of a product

2. Through this process, user stories, sprints and retrospectives are simulated

**Used for:**

- Training or onboarding to help teams experience how agile practices work together

**limitations:**

- basic exposure does not replicate real-life complexities
- best seen as complementary to ongoing real project work

## Agile manifesto

- Individuals and interactions over processes and tools
- Working software over comprehensive documentation
- Customer collaboration over contract negotiation
- Responding to change over following a plan

That is, while there is value in the items on
the right, we value the items on the left more.

**12 Agile principles:**

1. Our highest priority is to satisfy the customer
through early and continuous delivery
of valuable software.

2. Welcome changing requirements, even late in
development. Agile processes harness change for
the customer's competitive advantage.

3. Deliver working software frequently, from a
couple of weeks to a couple of months, with a
preference to the shorter timescale.

4. Business people and developers must work
together daily throughout the project.

5. Build projects around motivated individuals.
Give them the environment and support they need,
and trust them to get the job done.

6. The most efficient and effective method of
conveying information to and within a development
team is face-to-face conversation.

7. Working software is the primary measure of progress.

8. Agile processes promote sustainable development.
The sponsors, developers, and users should be able
to maintain a constant pace indefinitely.

9. Continuous attention to technical excellence
and good design enhances agility.

10. implicity--the art of maximizing the amount
of work not done--is essential.

11. The best architectures, requirements, and designs
emerge from self-organizing teams.

12. At regular intervals, the team reflects on how
to become more effective, then tunes and adjusts
its behavior accordingly.

## Testing practices in Agile

**prioritise test cases:**

- prioritise tets based on *heatmap* (graph) where:
  - you collect changed components
  - sort tests based on frequency that failed based on collected changes
  - cut off list by some critieria

**stairway to heaven:**

-

### Levels of testing

#### unit/component testing

*Tests the smallest parts* of the software in isolation

#### Integration testing

*Assess how different units or components work together*, ensuring that integrated parts function corectly as a group

#### system testing

*Evaluates the complete, integrated system* to verify that it meets the specified requirements.

#### Acceptance testing

Confirms that the *system satisfies business requirements* and is acceptable to the end users. Often involves the customer or stakeholder feedback.

#### Regression testing (not a level of testing)

- Ensure that no unexpected effects result from changes

Rerun functiona and non-functional tests to verify that recent code changes haven't adversely affected affected existing functionality.

Applicable on *all testing levels*

- unit testing: reruns tests on each unit of a component
- integration testing: test whether the integrations between components remain stable
- system testing: validates the complete integration of the system based on specified requirements
- acceptance testing: validates that the overall application continues to satisfy user requirements and acceptance criteria

#### Unit vs Regression testing

Unit testing: Proves that the code is doing what it is expected

Regression testing: Ensure that no unexpected effects result from changes

**regression test suite:**
collection of pre-validated test cases. Ensures the most critical failure-prone tests run first, enabling faster feedback

- rerun every time there are changes in the software

Example:
a team might rank test cases based on historical failure rates and the significance of the functionalities they cover. For instance, test for core features or recently modified modules are executed before tests for less critical, stable features.  

#### non-function testing

Covers the non-functional aspects of development, such as performance, security, usability, risk assessment, portability, maintanability, reliability, scalability, etc

We can define these categories more closely as:

- performance testing: *evaluate* system's responsiveness, stability and scalability under various load conditions

- usability testing: *measures* how intuitive the UI is to the user

- compatibility testing: *verifies* that the system remains usable and performant across multiple operating systems and devices

- security testing: *Assess* vulnerabilities in the system

### CI testing

**basic principles:**

1. maintain a single source repository
2. small and frequent commits
3. fail fast, fix fast
4. follow your commit
5. automate the flow
6. everyone can see what's happening

- CI uses version control guidelines, such as git

**basic CI practices:**

- don't check in a broken build
- always run all commit tests locally before committing
- wait for commit tests to pass before moving on
- test driven development

### TestFirst

**description:**

- Design and write tests before writing the actual production code.
- Forms the basis for TDD but can be used more broadly in agile practices.

**How it works:**

1. *Design tests:* Design and define expected code behaviour through tests
    - these tests can serve as a specification that the code must fulfill

2. *Write minimal code:* Enough for the code to pass the test

3. *Refactor:* and optimize the code to ensure while ensuring all tests continue to pass

4. *Iterate:* over the process for additional features or functionality

**Where to use it:**

- best used when requirements are well-understood and stable.
- quite useful in critical components where reliability and maintenance are a priority
- Allows for continous integration which makes it a good strategy in more broad agile practices where rapid feedback and integration is emphasised
- Provides a basis for documentation and maintenance

**limitations:**

#### TestDrivenDevelopment (TDD)

Originated in XP. Usually adopted by other methodologies

**description:**

- *Red:* Write a test for a new feature/functionality that initially fails because the feature doesn't exist
at this stage, your tests should outline the expected behaviors for the code that is meant to be written.

- *Green:* Write minimal amount of code that makes the test pass.

- *Refactor:* Clean up code while keeping the tests passing.

**advantages:**

- supports iterative development
- improves code quality
- documentation
- enhanced feedback
- clear testable requirements

**Limitations:**

- limits flexibility in early design
- initial development speed
- aplication scope (can be difficult to apply in some undefined areas)

**when to use:**

- Clearly defined and stable requirements
- Best used in areas where maintainability and reliability are essential
- Ideal for long-term projects expected to require frequent refactoring

## DevOps

- development + operations

**goals:**

- increase frequency and quality of deployments
- improve risk taking and innovation by making it safer
- faster time to market
- improves solution quality and time for fixes
- reduces the severity and frequency of release failures
- improves mean time to recovery (MTTR)

**basics:**

- automate everything
- identical production and deployment environments
- source control system
- measure everything

### Continious Deployment practices

- automated deployment: making software available to end-users automatically
- automated testing: automated techniques to perform various testing activities
- code review: the process of reviewing code for comment and approval
- dark launching: deploying changes by keeping the functional aspect of the software changes hidden from end-users
- end-user communication: communicating to end-users in order to receive direct feedback on the software
- feature flag: technique to facilitate triggering a specific branch amongst several branches of the software to ensble or disable (parts of ) features
- intercommunication: sharing all necessary documentation on deplyoment and development between developers
- monitoring: collecting deployment related information, producing performance metrics
- software repository: where all the software artefacts are stored
- staging: specific set of techniques executed after software changes are written
- dogfooding: when a team uses their own software as part of their software development
- gradual rollout: deploying software changes step-by-step to fractions of end-users

### Deployment strategies

- helps reducing risks, and allows for specific approaches on how to minimise the impact of issues.

#### canary rollout

**description:**

- deploy new version to small, representative subset of users or servers first.
- monitor performance, catch issues and bugs.
- allows for a rollout to the entire environment with possible bugs, errors and performance issues already solved.

**When to be used:**

- Ideal when you need to quickly gather feedback and monitor critical issues.
- Probably the best strategy if time constraints are involved.
- good for big rollouts

#### gradual rollout

**description:**

- gradually increase the number or porcentage of users served by the new version over time
- controlled approach to minimise impact of errors, bugs or performance issues.
- ensures smooth scalling of deployment

**When to be used:**

- Effective for managing risk in cases where ramping up deployment is possible
- Allows for continous monitoring and quick rollback if necessary
- good for big rollouts

## Scaling and SAFe practices

- cross-functional teams
- Agile release trains (ART)
- solutions
- business/portfolios

SAFe is based on 3 core bodies of knowledge:

1. Agile development
2. Lean product development
3. systems thinking

**ART lead roles:**

- Product management
- System architect
- Release train engineer
- business owner

## Ethics
