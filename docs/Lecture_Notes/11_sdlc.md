# 11. Systems Development Life Cycle

!!! info
    - Rahida Asadli, Rumiyya Alili, Ismayil Shahaliyev
    - Dec 15 2025 / Dec 24 2025

[Systems Development Life Cycle (SDLC)](https://en.wikipedia.org/wiki/Systems_development_life_cycle) is a framework that guides the creation of an information system from initial idea to a working product. It describes the process of identifying system requirements, designing the system, building it, and deploying it to users.

## Participants of SDLC

Developing an information system is not just a technical task. It is a coordinated effort involving business decision-makers, technical specialists, and end-users, each with distinct responsibilities.

**Stakeholders** are individuals or groups who are affected by the system or have an interest in its outcome. This includes managers, department heads, users, IT staff, and executives. Stakeholders provide input, set expectations, and evaluate whether the system delivers value.

**Project sponsor** is a senior business representative who initiates the project by identifying a business need. The sponsor secures funding, supports the project at the executive level, and acts as the main business authority. Without a sponsor, a project usually lacks direction and protection.

**Steering committee** (or approval committee) is a small group of senior managers and stakeholders. This group reviews major decisions, evaluates feasibility, approves budgets, and decides whether the project should start, continue, change direction, or be stopped. Their role is governance, not day-to-day work.

**Project manager** is responsible for planning and controlling the project. This role creates schedules, manages costs, assigns tasks, tracks progress, and resolves risks. The project manager coordinates all participants and ensures that work across phases stays aligned with time, budget, and scope.

**Systems analyst** focuses on how the information system supports the organization. This role studies current workflows, identifies problems, translates business needs into system requirements, and helps design the overall solution. Systems analysts bridge the gap between business and technology.

**Business analyst** concentrates on business value and process improvement. This role examines how work is done today, identifies inefficiencies, defines new business rules, and ensures the system delivers measurable benefits. Business analysts speak the language of management and operations.

**Requirements analyst** is responsible for gathering, documenting, and validating detailed system requirements. This role works closely with users and stakeholders to ensure requirements are clear, complete, and unambiguous. Good communication is critical here, because unclear requirements lead to system failure.

**Infrastructure analyst** handles the technical foundation of the system. This includes servers, networks, databases, operating systems, and integration with existing systems. The infrastructure analyst ensures the system is reliable, scalable, and compliant with organizational standards.

**Change management analyst** focuses on people, not technology. This role prepares users for the new system through training, documentation, communication, and support. The goal is to reduce resistance, ensure adoption, and help the organization adjust to new ways of working.

**Programmers and developers** build the system based on the approved design. They write code, integrate components, and implement system functionality.

**Testers** verify that the system works correctly. They check for errors, validate that requirements are met, and ensure the system behaves as expected under real conditions.

**Users (end-users)** are the people who will use the system daily. They provide requirements, review designs, test early versions, and ultimately determine whether the system is successful. _A system that users do not accept or trust will fail, regardless of technical quality._

These labels describe roles, not fixed job titles. A role represents a set of responsibilities that must be performed for a system to be successfully developed, regardless of who performs them. In practice, organizations rarely use these exact titles. Instead, job titles emerge based on company size, structure, industry, and methodology. One person may carry out several roles under a single title, or a single role may be shared across multiple people. What matters is that the functions—decision-making, requirement definition, technical design, implementation, testing, and user adoption—are covered, even if the titles used in the organization are different or change over time.

## Phases of SDLC

The SDLC typically consists of four fundamental phases—planning, analysis, design, and implementation—each with its own steps, techniques, and deliverables.

!!! note
    Think of it like building a house. First, you decide why you need the house and what problems it must solve—how many rooms it should have, who will live in it, and how much you can spend (planning). Next, you write down exact requirements: the number of floors, room sizes, plumbing, electricity, heating, and safety rules (analysis). Then you turn these requirements into precise drawings and technical plans that builders can follow, showing layouts, measurements, and materials (design). Finally, the house is built according to these plans, utilities are installed, and everything is checked to make sure it works as expected before people move in (implementation). Each step produces concrete results that guide the next step, and earlier decisions may be adjusted as new issues are discovered.

### Planning Phase

The main goal of the _planning phase_ is to understand **why** an information system should be built and to decide how the project will be organized and managed. Before any system is designed or built, the organization must be sure that the project is necessary, realistic, and valuable.

During _project initiation_, a business need or problem is identified. This need usually comes from a business department rather than the IT department. The idea for the new system is written in a document called a _system request_, which briefly explains the problem, the reason a system is needed, and how it is expected to help the organization. The person or department that proposes the system is known as the _project sponsor_.

After the system request is prepared, a [feasibility analysis](https://en.wikipedia.org/wiki/Feasibility_study) is conducted. This analysis checks whether the project should move forward by examining three important areas.

_Technical feasibility_ asks whether the system can actually be built using the organization's current technology, skills, and resources: _Can we build it?_

!!! note
    If a company wants to develop a mobile banking application, it must check whether it has developers with mobile programming skills, secure servers, and the ability to connect the app to existing banking systems. If these resources are missing, the project may not be technically feasible.

_Economic feasibility_ focuses on whether the system is worth its cost. It compares the expected benefits with the total costs of development, operation, and maintenance: _Should we build it?_

!!! note
    If a supermarket plans to install self-checkout machines, it must consider whether the reduction in staff costs and faster checkout times will save more money than the cost of purchasing and maintaining the machines. If the benefits are greater than the costs, the project is economically feasible.

_Organizational feasibility_ examines how the system will fit within the organization and whether people will accept and use it. A system can fail even if it is technically and economically sound, simply because users resist it: _If we build it, will users accept it?_

!!! note
    If a university introduces a new online attendance system, it must ensure that lecturers and students are willing to use it and that proper training is provided. Strong management support is also essential for organizational feasibility.

Once the feasibility analysis is completed, the system request and analysis results are reviewed by an approval committee, often called a _steering committee_. This committee decides whether the project should be approved, changed, or rejected.

If the project is approved, it moves into [project management](https://en.wikipedia.org/wiki/Project_management), which is the second step of the planning phase. At this stage, the focus shifts from deciding whether to build the system to deciding **how** the work will be carried out. The project manager breaks the project into specific tasks, estimates how long each task will take, identifies required resources, and assigns responsibilities to team members. A detailed schedule is created, showing task order, dependencies, milestones, and deadlines. The project manager also prepares a budget, identifies major risks, and defines how progress will be monitored and reported. This project plan becomes the roadmap for the entire system development effort and is used throughout the SDLC to track progress, control costs, and manage changes.

### Analysis Phase

The _analysis phase_ focuses on understanding the system in detail before it is designed or built. In this phase, the project team answers three key questions: who will use the system, what the system must do, and where and when it will be used. The goal is to clearly understand the current situation and define what the new system should achieve.

During the analysis phase, the team first studies any existing system that is already in use. The team looks for problems, weaknesses, delays, errors, or user complaints. At the same time, they imagine how a better system could work in the future.

!!! note
    If a company currently uses paper forms to track employee leave requests, analysis would study how this process works now and then imagine a future system where requests are submitted and approved online.

The next part of the analysis phase is _requirements gathering_. This means collecting information about what users and managers actually need from the system. The project team talks to users, managers, and other stakeholders to understand their expectations and daily work.

!!! note
    When developing a university course registration system, analysts may talk to students, instructors, and administrative staff to understand how courses are selected, approved, and recorded. From this, the team defines requirements such as allowing students to register for courses or enabling instructors to view class lists.

Based on these requirements, the team develops a _system concept_. The system concept is a high-level description of how the new system will work and how it will support the organization. Analysts often create simple models showing how users interact with the system and how information flows inside it. These models focus on clarity, not implementation details.

In the final step of the analysis phase, findings are combined into a document called the _system proposal_. This document includes the analysis results, the system concept, the requirements, and the models. It is presented to the project sponsor and other decision makers. They use it to decide whether the project should continue, be changed, or be stopped.

The system proposal is the main output of the analysis phase. It may include a preliminary solution concept, but it does not contain the detailed technical blueprint. That is the purpose of the design phase.

### Design Phase

The _design phase_ focuses on deciding how the system will work. The project team defines technical details, including hardware and software choices, network setup, user interface, database structure, and the programs that must be created.

One of the first tasks in the design phase is choosing a _design strategy_. The organization may build the system internally, outsource development, or buy an existing software package and adapt it.

After the design strategy is chosen, the team creates the [_system architecture_](https://en.wikipedia.org/wiki/Systems_architecture) design, describing the overall structure of hardware, software, and network infrastructure, including how the new system connects to existing systems.

At the same time, the team designs the [_user interface_](https://en.wikipedia.org/wiki/User_interface), defining screens, menus, buttons, forms, and reports, aiming for clarity and usability.

The design phase also includes _database and file specifications_, which define what data will be stored and how it will be organized.

Finally, the team prepares the _program design_, describing what programs need to be written and what each program will do. This is not coding; it is a specification for developers.

!!! note
    In an online student registration system, design includes architecture (web servers for student access and database servers for enrollment data), user interface behavior (search, add, drop, confirmations), database tables (students, courses, enrollments, prerequisites), and program modules (authentication, validation, enrollment processing, reporting).

All design outputs are combined into a single document called the _system specification_. This includes architecture design, interface design, database specifications, and program design. It is the main guide for programmers in the next phase. At the end of the design phase, feasibility and the project plan are reviewed again, and the sponsor and approval committee decide whether the project should continue.

### Implementation Phase

In the _implementation phase_, the system is built and put into use. If the organization decided to buy an existing software package, implementation includes installing and configuring it instead of building everything from scratch.

The first step is _system construction_. Programmers write code, databases are created, and components are integrated. At the same time, the system is tested to ensure it behaves as expected. Testing is critical because fixing errors after deployment can be expensive and disruptive.

Once the system is built and tested, the next step is _system installation_, which switches from the old system to the new one. This may involve shutting down the old system, or running both in parallel for a short period. A key part of installation is _user training_ so users can work confidently and correctly.

The final step is creating a _maintenance (support) plan_. This explains how the system will be supported after it goes live. It often includes a post-implementation review to check whether goals were met and whether users are satisfied. The plan also defines how problems will be fixed, how updates will be handled, and how users can get help.

Together, these steps ensure the system is built correctly, adopted by users, and supported over time.

!!! note
    Fixing errors after deployment is often far more expensive than fixing them during development. A failure in an online banking transaction system is not just a bug; it can cause direct financial loss and destroy trust.

**Exercise.** Why follow a system development life cycle with phases described above?

## Approaches to SDLC

The phases above can be organized in different ways. Below are several common approaches, with typical advantages and disadvantages.

### Waterfall Development

The [waterfall model](https://en.wikipedia.org/wiki/Waterfall_model) is a traditional approach that follows a linear sequence. Each phase is intended to be completed before the next one begins, with minimal overlap.

!!! note
    Different textbooks describe SDLC phases and approaches differently. There is no single official SDLC. Some describe four phases (planning, analysis, design, implementation). Others separate construction and testing, or add deployment and maintenance as separate phases. What stays consistent is the logic: understand the problem, define requirements, design the solution, build it, test it, and put it into use.

A key assumption of waterfall is that requirements remain stable after they are defined. Because changes late in the project are costly, waterfall fits projects where requirements are well understood from the beginning and formal approvals and documentation are required.

One advantage is its clarity and structure, which makes planning, budgeting, and progress tracking easier. A major disadvantage is its inflexibility: if requirements change, rework can be expensive.

**Exercise.** What other advantages and disadvantages of the waterfall model can you identify?

### System Prototyping

The [prototyping model](https://en.wikipedia.org/wiki/Software_prototyping) produces a working [prototype](https://en.wikipedia.org/wiki/Prototype) quickly. Users evaluate it, provide feedback, and developers iterate until it becomes the final system. This approach clarifies requirements through direct user interaction, but if rushed, it can lead to weak architecture.

!!! note
    A university can start with a basic course registration prototype. Students test it, request changes, and developers iterate until the system becomes stable enough for real use.

_Throwaway prototyping_ uses prototypes as a learning tool. The team builds prototypes to explore alternatives, clarify uncertainties, and test technical feasibility, then discards them and builds the real system using proper architecture and standards.

!!! note
    Before building a hospital patient management system, a team may prototype registration and appointment scheduling with mock data. After discovering missing requirements and confusing workflows, the prototype is discarded and the real system is designed and implemented properly.

### Minimum Viable Product (MVP)

A [Minimum Viable Product (MVP)](https://en.wikipedia.org/wiki/Minimum_viable_product) is the simplest version of a product that delivers value to early users and allows a team to test assumptions. It includes only the core features, with everything else deferred, so the team can learn quickly and avoid waste.

Although prototyping and MVP development are both iterative, they differ in purpose. Prototyping is usually aimed at clarifying requirements for building the right system inside an organization. An MVP is aimed at validating whether the product is worth building in a market setting.

**Exercise.** Describe advantages and disadvantages of prototyping and MVP approaches compared to the waterfall model.

### Agile Development

[Agile development](https://en.wikipedia.org/wiki/Agile_software_development) was created in response to waterfall limitations, especially where requirements change frequently. Agile emphasizes flexibility, collaboration, and continuous improvement. Work is delivered in small increments, user feedback is collected regularly, and changes are welcomed even late in development.

A key reference is the [Agile Manifesto](https://agilemanifesto.org/), which prioritizes individuals and interactions, working software, customer collaboration, and responding to change.

One popular agile method is [Scrum](https://en.wikipedia.org/wiki/Scrum_%28project_management%29), which organizes work into short cycles called _sprints_ (often 2–4 weeks). Each sprint delivers a set of features that are designed, built, tested, and reviewed.

Agile’s advantages include flexibility, strong user involvement, and quicker delivery of value. Its disadvantages include the need for active user participation, strong team coordination, and difficulty in long-term planning if scope is not controlled.

**Exercise.** What other advantages and disadvantages of agile development can you identify?

## Unified Modeling Language (UML)

[Unified Modeling Language (UML)](https://en.wikipedia.org/wiki/Unified_Modeling_Language) is a standardized visual language used to analyze, design, and communicate how an information system should work. It is used mainly during the analysis and design phases to make requirements and design decisions clear for both technical and non-technical stakeholders.

<img src="../../assets/images/lecture13/image.png" alt="UML diagram example" style="max-width: 100%; height: auto;">

A [class diagram](https://en.wikipedia.org/wiki/Class_diagram) describes the static structure of a system: classes, attributes, and relationships.

A [sequence diagram](https://en.wikipedia.org/wiki/Sequence_diagram) shows how objects interact over time to complete a use case.

**Exercise.** Create a use case diagram, class diagram, and sequence diagram for an online course registration system. The system should allow students to enroll in courses, drop courses, and view schedules. It should allow administrators to manage courses and student records.

## Software Testing

[Software testing](https://en.wikipedia.org/wiki/Software_testing) is the process of evaluating a system to determine whether it functions correctly and meets specified requirements. Testing is performed throughout the SDLC, with different types of testing focusing on different levels of the system.

[Unit testing](https://en.wikipedia.org/wiki/Unit_testing) tests individual functions, methods, or classes in isolation, usually by developers.

[Integration testing](https://en.wikipedia.org/wiki/Integration_testing) checks how modules work together, focusing on interfaces and data flow.

[System testing](https://en.wikipedia.org/wiki/System_testing) evaluates the complete system against functional and non-functional requirements such as performance, security, and reliability.

[User acceptance testing (UAT)](https://en.wikipedia.org/wiki/Acceptance_testing) is performed by end users or customer representatives to confirm the system supports real business tasks and is ready for operational use.

[Regression testing](https://en.wikipedia.org/wiki/Regression_testing) ensures that changes or bug fixes have not broken existing functionality by re-running previously executed tests.

## Extreme Programming (XP)

[Extreme programming (XP)](https://en.wikipedia.org/wiki/Extreme_programming) is an agile approach that emphasizes close collaboration, continuous feedback, and high-quality code. Short iterations deliver working functionality regularly. [Pair programming](https://en.wikipedia.org/wiki/Pair_programming) supports code quality and knowledge sharing. Unit testing and continuous integration enable safe changes and reduce late-stage integration problems.

## Joint Application Development (JAD) {#jad}

[Joint Application Development (JAD)](https://en.wikipedia.org/wiki/Joint_application_design) is a structured technique for gathering and defining system requirements through facilitated workshops. Users, managers, analysts, and developers work together to reach shared understanding and make decisions quickly.

JAD is typically used during the analysis phase, especially for systems with many stakeholders or complex business rules. A trained facilitator keeps sessions focused and ensures all viewpoints are heard. The outcome is a clearer set of requirements and stronger user ownership.

!!! note
    When developing a company-wide reporting system, representatives from finance, operations, and management join JAD workshops with analysts. They agree on required reports, data definitions, and business rules early, which reduces later change requests and increases acceptance.

## Additional Material

- [Software Development Life Cycle: Explained](https://www.youtube.com/watch?v=SaCYkPD4_K0)
- [Estimate Software Development Costs](https://www.youtube.com/watch?v=Byz0Aj2t3bk)
- [Software Planning and Technical Documentation](https://www.youtube.com/watch?v=2qlcY9LkFik)
- [What is Agile?](https://www.youtube.com/watch?v=Z9QbYZh1YXY)
- [UML use case diagrams](https://www.youtube.com/watch?v=4emxjxonNRI&t=446)
- [UML class diagrams](https://www.youtube.com/watch?v=6XrL5jXmTwM)
- [Software Testing Explained in 100 Seconds](https://www.youtube.com/watch?v=u6QfIXgjwGQ)
