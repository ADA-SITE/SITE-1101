# 10. Systems Development Life Cycle

:material-account: Rahida Asadli, Rumiyya Alili, Ismayil Shahaliyev  
:material-calendar: Dec 15 2025 :material-calendar-edit: Jan 31, 2026

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

These labels describe roles, not fixed job titles. A role represents a set of responsibilities that must be performed for a system to be successfully developed, regardless of who performs them. In practice, organizations rarely use these exact titles. Instead, job titles emerge based on company size, structure, industry, and methodology. One person may carry out several roles under a single title, or a single role may be shared across multiple people. What matters is that the functions - decision-making, requirement definition, technical design, implementation, testing, and user adoption - are covered, even if the titles used in the organization are different or change over time.

## Phases of SDLC

The SDLC typically consists of four fundamental phases - planning, analysis, design, and implementation - each with its own steps, techniques, and deliverables.

!!! note
    Think of it like building a house. First, you decide why you need the house and what problems it must solve - how many rooms it should have, who will live in it, and how much you can spend (planning). Next, you write down exact requirements: the number of floors, room sizes, plumbing, electricity, heating, and safety rules (analysis). Then you turn these requirements into precise drawings and technical plans that builders can follow, showing layouts, measurements, and materials (design). Finally, the house is built according to these plans, utilities are installed, and everything is checked to make sure it works as expected before people move in (implementation). Each step produces concrete results that guide the next step, and earlier decisions may be adjusted as new issues are discovered.

### Planning Phase

The main goal of the _planning phase_ is to understand **why** an information system should be built and to decide how the project will be organized and managed. Before any system is designed or built, the organization must be sure that the project is necessary, realistic, and valuable.

During _project initiation,_ a business need or problem is identified. This need usually comes from a business department rather than the IT department. The idea for the new system is written in a document called a _system request_, which briefly explains the problem, the reason a system is needed, and how it is expected to help the organization. The person or department that proposes the system is known as the _project sponsor_.

After the system request is prepared, a [feasibility analysis](https://en.wikipedia.org/wiki/Feasibility_study) is conducted. This analysis checks whether the project should move forward by examining three important areas.

_Technical feasibility_ asks whether the system can actually be built using the organization's current technology, skills, and resources: _Can we build it?_

!!! note
    If a company wants to develop a mobile banking application, it must check whether it has developers with mobile programming skills, secure servers, and the ability to connect the app to existing banking systems. If these resources are missing, the project may not be technically feasible.

Economic feasibility focuses on whether the system is worth its cost. It compares the expected benefits with the total costs of development, operation, and maintenance: _Should we build it?_

!!! note
    If a supermarket plans to install self-checkout machines, it must consider whether the reduction in staff costs and faster checkout times will save more money than the cost of purchasing and maintaining the machines. If the benefits are greater than the costs, the project is economically feasible.

Organizational feasibility examines how the system will fit within the organization and whether people will accept and use it. A system can fail even if it is technically and economically sound, simply because users resist it. _If we build it, will users demand it?_

!!! note
    If a university introduces a new online attendance system, it must ensure that lecturers and students are willing to use it and that proper training is provided. Strong management support is also essential for organizational feasibility.

Once the feasibility analysis is completed, the system request and analysis results are reviewed by an approval committee, often called a _steering committee_. This committee decides whether the project should be approved, changed, or rejected.

If the project is approved, it moves into [project management](https://en.wikipedia.org/wiki/Project_management), which is the second step of the planning phase. At this stage, the focus shifts from deciding whether to build the system to deciding **how** the work will be carried out. The project manager breaks the project into specific tasks, estimates how long each task will take, identifies required resources, and assigns responsibilities to team members. A detailed schedule is created, showing task order, dependencies, milestones, and deadlines. The project manager also prepares a budget, identifies major risks, and defines how progress will be monitored and reported. This project plan becomes the roadmap for the entire system development effort and is used throughout the SDLC to track progress, control costs, and manage changes.

### Analysis Phase

_Analysis phase_ focuses on understanding the system in detail before it is designed or built. In this phase, the project team answers three key questions: **_who_** _will use the system_**,** **_what_** _the system must do, and_ **_where_** _and_ **_when_** _it will be used._ The goal is to clearly understand the current situation and define what the new system should achieve.

During the analysis phase, the team first studies any existing system that is already in use. The team looks for problems, weaknesses, delays, errors, or user complaints. At the same time, they imagine how a better system could work in the future.

!!! note
    If a company currently uses paper forms to track employee leave requests, the analysis phase would study how this process works now and then imagine a future system where requests are submitted and approved online.

The next part of the analysis phase is _requirements gathering_. This means collecting information about what users and managers actually need from the system. The project team talks to users, managers, and other _stakeholders_ to understand their expectations and daily work.

!!! note
    When developing a university course registration system, analysts may talk to students, instructors, and administrative staff to understand how courses are selected, approved, and recorded. From this information, the team defines requirements, which clearly describe what the system must be able to do, such as allowing students to register for courses or enabling instructors to view class lists.

Based on these requirements, the team develops a _system concept_. The system concept is a high-level description of how the new system will work and how it will support the business or organization. To explain this concept, analysts create simple models that show how users interact with the system and how information flows inside it. These models do not show technical details; instead, they help everyone understand the system in an easy and visual way.

In the final step of the analysis phase, all findings are combined into a document called the _system proposal._ This document includes the analysis results, the system concept, the requirements, and the models. The system proposal is presented to the project sponsor and other decision makers, such as an approval committee. They use this document to decide whether the project should continue, be changed, or be stopped.

The system proposal is the main output of the analysis phase. It is important to understand that this document does not only analyze the problem but also provides a high-level design idea for the new system. For this reason, some experts say this phase could be called "analysis and initial design." However, it is commonly referred to as the analysis phase, and its result guides all later stages of system development.

### Design Phase

_Design phase_ focuses on deciding **how** the system will actually work. In this phase, the project team defines the technical details of the system, including the hardware and software to be used, the network setup, the user interface, the database structure, and the programs that must be created.

One of the first tasks in the design phase is choosing a _design strategy_. This decision determines how the system will be developed. The organization may decide to build the system using its own programmers, outsource the development to an external company, or buy an existing software package and adapt it to its needs.

After the design strategy is chosen, the team creates the [_system architecture_](https://en.wikipedia.org/wiki/Systems_architecture) _design_. This design describes the overall technical structure of the system, including the hardware, software, and network infrastructure. In many cases, the new system does not replace everything but instead connects to existing systems.

At the same time, the team designs the [_user interface_](https://en.wikipedia.org/wiki/User_interface)_,_ which defines how users interact with the system. This includes screens, menus, buttons, forms, and reports. The goal is to make the system easy to use and understandable.

The design phase also includes creating _database and file specifications._ These specifications clearly define what data will be stored, how it will be organized, and where it will be saved.

Finally, the analyst team prepares the _program design,_ which describes the programs that need to be written and what each program will do. This does not involve writing code yet; instead, it provides clear instructions for programmers.

!!! note
    Consider the design of an online student registration system. During the design phase, the team decides whether to build the system internally or purchase and customize an existing solution. They define the system architecture, such as web servers for student access and database servers for storing course and enrollment data. The user interface design specifies how students search for courses, add or drop classes, and receive confirmation messages. Database specifications define tables for students, courses, enrollments, and prerequisites. Program designs describe modules for authentication, course validation, enrollment processing, and report generation.

All design outputs are combined into a single document called the _system specification_. This document includes the architecture design, interface design, database specifications, and program design. It serves as the main guide for programmers during the next - implementation phase. At the end of the design phase, the feasibility analysis and project plan are reviewed again, and the project sponsor and approval committee decide whether the project should continue or be stopped.

### Implementation Phase

In the _implementation phase_ phase, the system is actually built and put into use. If the organization decided to buy an existing software package during the design phase, implementation includes installing and configuring that software instead of building it from scratch. This phase usually receives the most attention because it is often the longest and most expensive part of system development.

The first step of implementation is _system construction_. During system construction, programmers write the code, databases are created, and system components are connected. At the same time, the system is carefully _tested_ to make sure it works as expected. **Testing is extremely important** because fixing errors after the system is already in use can be very costly and disruptive. For example, if an online banking system has an error in transaction processing, it could lead to financial losses and loss of customer trust. For this reason, organizations often spend more time testing the system than writing the actual code.

Once the system is built and tested, the next step is _system installation_. Installation is the process of switching from the old system to the new one. This may involve turning off the old system completely or running both systems at the same time for a short period. A key part of installation is _user training_. Users must learn how to use the new system correctly and confidently. For example, when a hospital installs a new patient record system, doctors, nurses, and administrative staff must be trained so that daily work is not interrupted and mistakes are avoided.

The final step of the implementation phase is creating a _maintenance (support) plan_ for the new system. This plan explains how the system will be supported after it goes live. It often includes a post-implementation review, where the project team checks whether the system meets its goals and whether users are satisfied. The support plan also defines who will fix problems, how updates will be handled, and how users can get help when they face difficulties.

Together, these steps ensure that the system is not only built correctly but also successfully adopted and supported within the organization.

!!! success "Exercise"
    Why follow a system development life cycle with phases described above?

## Approaches to SDLC

The basic phases of the SDLC described above can be organised in different ways. Here we compare several common approaches, highlighting advantages and disadvantages.

### Waterfall Development

[Waterfall life cycle model](https://en.wikipedia.org/wiki/Waterfall_model) is a traditional approach to systems development that follows a linear and sequential process. In this model, development moves step by step through clearly defined stages such as _systems analysis → design → construction → testing → maintenance (support)._

!!! warning "Important"
    Different textbooks often describe the SDLC phases and its approaches differently. In reality, there is no single official SDLC - it is a general framework, not a fixed standard. Authors adapt it to their teaching goals, historical context, and methodology preferences. As a result, phase names, the number of phases, and what is included in each phase can vary.

    Some textbooks describe four phases (planning, analysis, design, implementation). Others use five or six phases, separating implementation into construction and testing, or adding deployment and maintenance as separate phases. For example, maintenance may appear as part of implementation in one book and as its own phase in another.

    What stays consistent is the logic, not the labels: first understand the problem, then define requirements, then design a solution, then build it, test it, and put it into use. The ordering and purpose remain the same even when terminologies and boundaries differ.

Each phase must be completed before the next one begins, and there is very little overlap between stages. A key assumption of the waterfall model is that **system requirements remain stable** after they are defined. This means that once the analysis phase is finished, changes are difficult and usually discouraged. Because of this, the waterfall model is most suitable for projects where requirements are well understood from the beginning and are unlikely to change. It is commonly used when risk must be tightly controlled and when strict documentation and formal approvals are required.

The waterfall approach is often applied in large-scale and high-cost projects, where complexity is high and mistakes can be very expensive. The rigid structure helps ensure that every deliverable is carefully planned, documented, and reviewed. It is also useful for IT projects that do not involve software development, such as upgrading network equipment like routers and switches to support new technologies such as VoIP phones.

One major advantage of the waterfall model is its clarity and structure. Because each phase has specific outputs, it is easy to manage, track progress, and control costs. However, a major disadvantage is its lack of flexibility. If requirements change later in the project, it can be costly and time-consuming to go back and make adjustments. This makes the waterfall model less suitable for projects where requirements are uncertain or evolving.

!!! success "Exercise"
    What other advantages and disadvantages of the waterfall model can you define?

### System Prototyping

[System prototyping model](https://en.wikipedia.org/wiki/Software_prototyping) performs analysis, design, and implementation concurrently to quickly produce a working [prototype](https://en.wikipedia.org/wiki/Prototype) that users can evaluate. The first prototype is often a "quick and dirty" version with basic features. Users review it, provide feedback, and developers revise it. This cycle continues until the prototype has enough functionality to become the final system. This approach provides quick visible progress and helps users clarify requirements by interacting with a working system, which increases user confidence and involvement. However, because development starts quickly, there may be insufficient careful analysis early in the project, which can result in fundamental design weaknesses if requirements are not fully understood before implementation.

!!! note
    A university develops a course registration prototype with simple search and enrollment features. Students test it, suggest improvements, and developers iteratively refine it until it becomes the production system.


The _throwaway prototyping_ uses prototypes as a learning tool that are discarded after serving their purpose, not evolved into the final system. After initial requirements analysis, the team builds quick design prototypes to explore alternatives, clarify uncertainties, and test technical feasibility. These may be simple mock-up screens or small [proof-of-concept](https://en.wikipedia.org/wiki/Proof_of_concept) components. Once major questions are answered, prototypes are discarded and full development begins. This approach reduces risk and leads to more stable and reliable final systems because important problems are solved before real development begins. However, it can take longer to deliver since the prototypes themselves are not reused.

!!! note
    Before developing a new hospital patient management system, the team builds a quick prototype that simulates patient registration, appointment scheduling, and record lookup using mock data and simple screens. The prototype is shown to doctors, nurses, and administrative staff to discover missing requirements, confusing workflows, and unrealistic assumptions. After this feedback is collected and the requirements are clarified, the prototype is discarded and the real system is designed and implemented using proper architecture, security, and performance standards.

### Minimum Viable Product (MVP)

[Minimum Viable Product (MVP)](https://en.wikipedia.org/wiki/Minimum_viable_product) is a special form of prototyping used in startups and innovation projects. It is the simplest version of a product that delivers value to early users and allows the team to test assumptions. The MVP includes just enough features to solve the core problem; other features are deferred. By releasing an MVP, teams learn what customers really need, reduce waste and iterate quickly.

!!! note
    Imagine designing an online bookstore. A system prototype might include simple screens to search for books and add them to a cart. Users try it and suggest improvements. A design prototype might be a set of static HTML pages showing how the checkout process could look; the pages do not process actual orders but help clarify layout and wording.

Although prototyping and MVP development both involve iterative refinement, they differ in purpose. The system prototyping model is used primarily to refine and stabilize system requirements within an organization, with the prototype gradually evolving into the final system. An MVP, in contrast, is used to validate a product's value and business viability with real users in a market setting. While prototyping focuses on building the _right system_, an MVP focuses on determining whether the system is _worth building at all_.

!!! success "Exercise"
    Describe advantages and disadvantages of prototyping and MVP approaches over the waterfall model.

### Agile Development

[Agile development approach](https://en.wikipedia.org/wiki/Agile_software_development) was created in response to the limitations of traditional models like waterfall, especially in environments where requirements are unclear or change frequently. Agile emphasizes flexibility, collaboration, and continuous improvement rather than rigid planning. In agile projects, requirements and solutions evolve through close cooperation between developers and users.

Agile development focuses on delivering working software in small parts, rather than delivering everything at the end of the project. User feedback is collected regularly, and changes are welcomed, even late in development. This makes agile particularly suitable for software development, mobile applications, and systems where **customer needs are expected to change**.

A key idea behind agile is described in the [Agile Manifesto](https://agilemanifesto.org/), which values people and communication over strict processes, working software over extensive documentation, customer collaboration over rigid contracts, and responding to change over following a fixed plan. These values guide how agile is applied, but each organization is responsible for interpreting and using them in practice.

One popular agile method is [Scrum](https://en.wikipedia.org/wiki/Scrum_%28project_management%29), which organizes work into short time periods called _sprints_, usually lasting two to four weeks. During each sprint, a small set of features is developed, tested, and prepared for delivery. At the end of each sprint, the team reviews progress and reflects on how to improve in the next cycle. This repeating process continues until the project goals are met, the budget is exhausted, or a deadline is reached.

The main advantages of agile development are its flexibility, strong user involvement, and ability to deliver value quickly. Agile helps ensure that the most important features are completed first and that the system stays aligned with customer needs. However, agile development requires active user participation, experienced team members, and a [cultural shift](https://en.wikipedia.org/wiki/Culture_change) within the organization. Without proper coordination, agile projects can suffer from unclear scope and difficulty in long-term planning.

!!! success "Exercise"
    What other advantages and disadvantages of agile development can you define?

## Unified Modeling Language (UML)

[Unified Modeling Language (UML)](https://en.wikipedia.org/wiki/Unified_Modeling_Language) is a **standardized** visual language used to analyze, design, and communicate how an information system should work. Its main purpose is to make system requirements and design decisions clear and unambiguous for both technical and non-technical stakeholders. UML is used mainly during the analysis and design phases of the SDLC, where it helps teams reason about system scope, structure, and behavior before implementation begins.

<figure class="w100 float-left">
  <img src="../../assets/images/lecture10/class.png" alt="UML Class diagram.">
  <figcaption>
    A UML class diagram of a library system.
  </figcaption>
</figure>

[Class diagram](https://en.wikipedia.org/wiki/Class_diagram) is used mainly during system design to describe the static structure of the system. It shows **classes**, their **attributes**, and the **relationships** between them. For example, in a library system, classes such as Book, Member, and Loan are defined. The Book class may be specialized into PrintedBook and EBook, both inheriting common attributes such as title and identifier. The diagram also shows how a Loan connects a Member to a Book, providing a clear basis for database design and program structure.

[Sequence diagram](https://en.wikipedia.org/wiki/Sequence_diagram) is used to describe how objects interact over time to complete a specific use case. It shows the order of messages exchanged between objects during execution. For example, a sequence diagram for the "Borrow Book" use case can show how the user interface sends a request, the system checks book availability, creates a loan record, updates the book's status, and confirms the transaction. This diagram helps developers understand control flow and responsibilities during runtime.

!!! success "Exercise"
    Create a use case diagram, class diagram, and sequence diagram for an online course registration system that allows students to enroll in courses, drop courses, view schedules, and allows administrators to manage courses and student records.

## Software Testing

[Software testing](https://en.wikipedia.org/wiki/Software_testing) is the process of evaluating a system to determine whether it functions correctly and meets specified requirements. The main goals of testing are to detect defects, verify that requirements are satisfied, and reduce the risk of failure after deployment. Testing is performed throughout the SDLC, with different types of testing focusing on different levels of the system.

[Unit testing](https://en.wikipedia.org/wiki/Unit_testing) focuses on testing individual units of code, such as functions, methods, or classes, in isolation. It is usually performed by developers during the implementation phase. The purpose of unit testing is to ensure that each small component behaves correctly before it is integrated with others. For example, a unit test may verify that a function calculating late fees returns the correct amount for various inputs.

[Integration testing](https://en.wikipedia.org/wiki/Integration_testing) examines how different modules or components work together. Even if individual units pass unit tests, errors can occur when components interact. Integration testing focuses on data flow, interfaces, and communication between modules and is typically performed after unit testing. For example, integration testing can verify that borrowing a book correctly updates both the loan records and inventory data.

[System testing](https://en.wikipedia.org/wiki/System_testing) evaluates the complete and integrated system as a whole. It checks whether the system meets its functional and non-functional requirements, such as performance, security, and reliability. System testing is often performed by a testing team or quality assurance (QA) group before the system is delivered to users.

[User Acceptance Testing (UAT)](https://en.wikipedia.org/wiki/Acceptance_testing) is performed by end users or customer representatives to confirm that the system supports real business tasks and is ready for operational use. UAT focuses on business correctness rather than technical details. For example, librarians may perform UAT to ensure that all daily library operations can be completed correctly using the new system.

[Regression testing](https://en.wikipedia.org/wiki/Regression_testing) ensures that recent changes or bug fixes have not broken existing functionality. It involves re-running previously executed tests and is especially important in systems that evolve over time. Regression testing helps maintain system stability as new features are added.

## Extreme Programming (XP)

[Extreme programming (XP)](https://en.wikipedia.org/wiki/Extreme_programming) is an agile development approach that emphasizes close collaboration, continuous feedback, and high-quality code. Its goal is to deliver useful software quickly while remaining flexible to changing requirements. XP encourages frequent interaction between developers and users so that misunderstandings are identified early.

Short iterations deliver working functionality regularly. [_Pair programming_](https://en.wikipedia.org/wiki/Pair_programming) improves code quality and knowledge sharing by having two developers work together. _Unit testing_ is central, ensuring that every component behaves correctly and enabling safe changes. _Continuous integration_ ensures that new code is frequently combined and tested to avoid late-stage failures.

## Joint Application Development (JAD)

[Joint Application Development (JAD)](https://en.wikipedia.org/wiki/Joint_application_design) is a structured technique used to gather and define system requirements through intensive, facilitated workshops. Instead of collecting requirements through long sequences of interviews, JAD brings users, managers, analysts, and developers together to reach shared understanding and quick decisions.

JAD is typically used during the analysis phase, especially for systems with many stakeholders or complex business rules. A trained facilitator guides the sessions, keeps discussions focused, and ensures that all viewpoints are heard. The outcome is a clearer, more complete set of requirements and stronger user ownership of the system.

!!! note
    For example, when developing a company-wide reporting system, representatives from finance, operations, and management participate in JAD sessions together with systems analysts. During these sessions, they agree on required reports, data definitions, and business rules. This shared understanding early in the project reduces later changes and increases acceptance of the system.

## Additional Material

- [Software Development Life Cycle: Explained](https://www.youtube.com/watch?v=SaCYkPD4_K0)
- [Estimate Software Development Costs](https://www.youtube.com/watch?v=Byz0Aj2t3bk)
- [Software Planning and Technical Documentation](https://www.youtube.com/watch?v=2qlcY9LkFik)
- [What is Agile?](https://www.youtube.com/watch?v=Z9QbYZh1YXY)
- [UML use case diagrams](https://www.youtube.com/watch?v=4emxjxonNRI&t=446)
- [UML class diagrams](https://www.youtube.com/watch?v=6XrL5jXmTwM)
- [Sotware Testing Explained in 100 Seconds](https://www.youtube.com/watch?v=u6QfIXgjwGQ)
