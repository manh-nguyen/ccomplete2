**Code Complete**

    	SPECIAL OFFER: Upgrade this ebook with O’Reilly
    	Preface
       	Who Should Read This Book?
          	Experienced Programmers
          	Technical Leads
          	Self-Taught Programmers
          	Students
       	Where Else Can You Find This Information?
       	Key Benefits of This Handbook
       	Why This Handbook Was Written
          	The Topic of Construction Has Been Neglected
          	Construction Is Important
          	No Comparable Book Is Available
       	Author Note
    	Acknowledgments
    	About the Author
       	Steve McConnell
    	I. Laying the Foundation
       	1. Welcome to Software Construction
          	1.1. What Is Software Construction?
          	1.2. Why Is Software Construction Important?
          	1.3. How to Read This Book
          	Key Points
       	2. Metaphors for a Richer Understanding of Software Development
          	2.1. The Importance of Metaphors
          	2.2. How to Use Software Metaphors
          	2.3. Common Software Metaphors
             	Software Penmanship: Writing Code
             	Software Farming: Growing a System
             	Software Oyster Farming: System Accretion
             	Software Construction: Building Software
             	Applying Software Techniques: The Intellectual Toolbox
             	Combining Metaphors
             	Additional Resources
          	Key Points
       	3. Measure Twice, Cut Once: Upstream Prerequisites
          	3.1. Importance of Prerequisites
             	Do Prerequisites Apply to Modern Software Projects?
             	Causes of Incomplete Preparation
             	Utterly Compelling and Foolproof Argument for Doing Prerequisites Before Construction
                	Appeal to Logic
                	Appeal to Analogy
                	Appeal to Data
                	Boss-Readiness Test
          	3.2. Determine the Kind of Software You're Working On
             	Iterative Approaches' Effect on Prerequisites
             	Choosing Between Iterative and Sequential Approaches
          	3.3. Problem-Definition Prerequisite
          	3.4. Requirements Prerequisite
             	Why Have Official Requirements?
             	The Myth of Stable Requirements
             	Handling Requirements Changes During Construction
          	3.5. Architecture Prerequisite
             	Typical Architectural Components
                	Program Organization
                	Major Classes
                	Data Design
                	Business Rules
                	User Interface Design
                	Resource Management
                	Security
                	Performance
                	Scalability
                	Interoperability
                	Internationalization/Localization
                	Input/Output
                	Error Processing
                	Fault Tolerance
                	Architectural Feasibility
                	Overengineering
                	Buy-vs.-Build Decisions
                	Reuse Decisions
                	Change Strategy
                	General Architectural Quality
          	3.6. Amount of Time to Spend on Upstream Prerequisites
          	Additional Resources
             	Requirements
             	Software Architecture
             	General Software-Development Approaches
          	Key Points
       	4. Key Construction Decisions
          	4.1. Choice of Programming Language
             	Language Descriptions
                	Ada
                	Assembly Language
                	C
                	C++
                	C#
                	Cobol
                	Fortran
                	Java
                	JavaScript
                	Perl
                	PHP
                	Python
                	SQL
                	Visual Basic
          	4.2. Programming Conventions
          	4.3. Your Location on the Technology Wave
             	Example of Programming into a Language
          	4.4. Selection of Major Construction Practices
          	Key Points
    	II. Creating High-Quality Code
       	5. Design in Construction
          	5.1. Design Challenges
             	Design Is a Wicked Problem
             	Design Is a Sloppy Process (Even If it Produces a Tidy Result)
             	Design Is About Tradeoffs and Priorities
             	Design Involves Restrictions
             	Design Is Nondeterministic
             	Design Is a Heuristic Process
             	Design Is Emergent
          	5.2. Key Design Concepts
             	Software's Primary Technical Imperative: Managing Complexity
                	Accidental and Essential Difficulties
                	Importance of Managing Complexity
                	How to Attack Complexity
             	Desirable Characteristics of a Design
             	Levels of Design
                	Level 1: Software System
                	Level 2: Division into Subsystems or Packages
                	Level 3: Division into Classes
                	Level 4: Division into Routines
                	Level 5: Internal Routine Design
          	5.3. Design Building Blocks: Heuristics
             	Find Real-World Objects
             	Form Consistent Abstractions
             	Encapsulate Implementation Details
             	Inherit—When Inheritance Simplifies the Design
             	Hide Secrets (Information Hiding)
                	Secrets and the Right to Privacy
                	An Example of Information Hiding
                	Two Categories of Secrets
                	Barriers to Information Hiding
                	Value of Information Hiding
             	Identify Areas Likely to Change
                	Anticipating Different Degrees of Change
             	Keep Coupling Loose
                	Coupling Criteria
                	Kinds of Coupling
             	Look for Common Design Patterns
             	Other Heuristics
                	Aim for Strong Cohesion
                	Build Hierarchies
                	Formalize Class Contracts
                	Assign Responsibilities
                	Design for Test
                	Avoid Failure
                	Choose Binding Time Consciously
                	Make Central Points of Control
                	Consider Using Brute Force
                	Draw a Diagram
                	Keep Your Design Modular
             	Summary of Design Heuristics
             	Guidelines for Using Heuristics
          	5.4. Design Practices
             	Iterate
             	Divide and Conquer
             	Top-Down and Bottom-Up Design Approaches
                	Argument for Top Down
                	Argument for Bottom Up
                	No Argument, Really
             	Experimental Prototyping
             	Collaborative Design
             	How Much Design Is Enough?
             	Capturing Your Design Work
          	5.5. Comments on Popular Methodologies
          	Additional Resources
             	Software Design, General
             	Software Design Theory
             	Design Patterns
             	Design in General
             	Standards
          	Key Points
       	6. Working Classes
          	6.1. Class Foundations: Abstract Data Types (ADTs)
             	Example of the Need for an ADT
             	Benefits of Using ADTs
             	More Examples of ADTs
             	Handling Multiple Instances of Data with ADTs in Non-Object-Oriented Environments
             	ADTs and Classes
          	6.2. Good Class Interfaces
             	Good Abstraction
             	Good Encapsulation
          	6.3. Design and Implementation Issues
             	Containment ("has a" Relationships)
             	Inheritance ("is a" Relationships)
                	Multiple Inheritance
                	Why Are There So Many Rules for Inheritance?
             	Member Functions and Data
             	Constructors
          	6.4. Reasons to Create a Class
             	Classes to Avoid
             	Summary of Reasons to Create a Class
          	6.5. Language-Specific Issues
          	6.6. Beyond Classes: Packages
          	Additional Resources
             	Classes in General
             	C++
             	Java
             	Visual Basic
          	Key Points
       	7. High-Quality Routines
          	7.1. Valid Reasons to Create a Routine
             	Operations That Seem Too Simple to Put Into Routines
             	Summary of Reasons to Create a Routine
          	7.2. Design at the Routine Level
          	7.3. Good Routine Names
          	7.4. How Long Can a Routine Be?
          	7.5. How to Use Routine Parameters
          	7.6. Special Considerations in the Use of Functions
             	When to Use a Function and When to Use a Procedure
             	Setting the Function's Return Value
          	7.7. Macro Routines and Inline Routines
             	Limitations on the Use of Macro Routines
             	Inline Routines
          	Key Points
       	8. Defensive Programming
          	8.1. Protecting Your Program from Invalid Inputs
          	8.2. Assertions
             	Building Your Own Assertion Mechanism
             	Guidelines for Using Assertions
          	8.3. Error-Handling Techniques
             	Robustness vs. Correctness
             	High-Level Design Implications of Error Processing
          	8.4. Exceptions
          	8.5. Barricade Your Program to Contain the Damage Caused by Errors
             	Relationship Between Barricades and Assertions
          	8.6. Debugging Aids
             	Don't Automatically Apply Production Constraints to the Development Version
             	Introduce Debugging Aids Early
             	Use Offensive Programming
             	Plan to Remove Debugging Aids
          	8.7. Determining How Much Defensive Programming to Leave in Production Code
          	8.8. Being Defensive About Defensive Programming
          	Additional Resources
             	Security
             	Assertions
             	Exceptions
          	Key Points
       	9. The Pseudocode Programming Process
          	9.1. Summary of Steps in Building Classes and Routines
             	Steps in Creating a Class
             	Steps in Building a Routine
          	9.2. Pseudocode for Pros
          	9.3. Constructing Routines by Using the PPP
             	Design the Routine
             	Code the Routine
             	Check the Code
             	Clean Up Leftovers
             	Repeat Steps as Needed
          	9.4. Alternatives to the PPP
          	Key Points
    	III. Variables
       	10. General Issues in Using Variables
          	10.1. Data Literacy
             	The Data Literacy Test
             	Additional Resources on Data Types
          	10.2. Making Variable Declarations Easy
             	Implicit Declarations
          	10.3. Guidelines for Initializing Variables
          	10.4. Scope
             	Localize References to Variables
             	Keep Variables "Live" for as Short a Time as Possible
                	Measuring the Live Time of a Variable
             	General Guidelines for Minimizing Scope
             	Comments on Minimizing Scope
          	10.5. Persistence
          	10.6. Binding Time
          	10.7. Relationship Between Data Types and Control Structures
          	10.8. Using Each Variable for Exactly One Purpose
          	Key Points
       	11. The Power of Variable Names
          	11.1. Considerations in Choosing Good Names
             	The Most Important Naming Consideration
             	Problem Orientation
             	Optimum Name Length
             	The Effect of Scope on Variable Names
             	Computed-Value Qualifiers in Variable Names
             	Common Opposites in Variable Names
          	11.2. Naming Specific Types of Data
             	Naming Loop Indexes
             	Naming Status Variables
             	Naming Temporary Variables
             	Naming Boolean Variables
             	Naming Enumerated Types
             	Naming Constants
          	11.3. The Power of Naming Conventions
             	Why Have Conventions?
             	When You Should Have a Naming Convention
             	Degrees of Formality
          	11.4. Informal Naming Conventions
             	Guidelines for a Language-Independent Convention
             	Guidelines for Language-Specific Conventions
                	C Conventions
                	C++ Conventions
                	Java Conventions
                	Visual Basic Conventions
             	Mixed-Language Programming Considerations
             	Sample Naming Conventions
          	11.5. Standardized Prefixes
             	User-Defined Type Abbreviations
             	Semantic Prefixes
             	Advantages of Standardized Prefixes
          	11.6. Creating Short Names That Are Readable
             	General Abbreviation Guidelines
             	Phonetic Abbreviations
             	Comments on Abbreviations
          	11.7. Kinds of Names to Avoid
          	Key Points
       	12. Fundamental Data Types
          	12.1. Numbers in General
          	12.2. Integers
          	12.3. Floating-Point Numbers
          	12.4. Characters and Strings
             	Strings in C
          	12.5. Boolean Variables
          	12.6. Enumerated Types
             	If Your Language Doesn't Have Enumerated Types
          	12.7. Named Constants
          	12.8. Arrays
          	12.9. Creating Your Own Types (Type Aliasing)
             	Why Are the Examples of Creating Your Own Types in Pascal and Ada?
             	Guidelines for Creating Your Own Types
          	Key Points
       	13. Unusual Data Types
          	13.1. Structures
          	13.2. Pointers
             	Paradigm for Understanding Pointers
                	Location in Memory
                	Knowledge of How to Interpret the Contents
             	General Tips on Pointers
             	C++-Pointer Pointers
             	C-Pointer Pointers
          	13.3. Global Data
             	Common Problems with Global Data
             	Reasons to Use Global Data
             	Use Global Data Only as a Last Resort
             	Using Access Routines Instead of Global Data
                	Advantages of Access Routines
                	How to Use Access Routines
             	How to Reduce the Risks of Using Global Data
          	Additional Resources
          	Key Points
    	IV. Statements
       	14. Organizing Straight-Line Code
          	14.1. Statements That Must Be in a Specific Order
          	14.2. Statements Whose Order Doesn't Matter
             	Making Code Read from Top to Bottom
             	Grouping Related Statements
          	Key Points
       	15. Using Conditionals
          	15.1. if Statements
             	Plain if-then Statements
             	Chains of if-then-else Statements
          	15.2. case Statements
             	Choosing the Most Effective Ordering of Cases
             	Tips for Using case Statements
          	Key Points
       	16. Controlling Loops
          	16.1. Selecting the Kind of Loop
             	When to Use a while Loop
                	Loop with Test at the Beginning
                	Loop with Test at the End
             	When to Use a Loop-With-Exit Loop
                	Normal Loop-With-Exit Loops
                	Abnormal Loop-With-Exit Loops
             	When to Use a for Loop
             	When to Use a foreach Loop
          	16.2. Controlling the Loop
             	Entering the Loop
             	Processing the Middle of the Loop
             	Exiting the Loop
                	Exiting Loops Early
             	Checking Endpoints
             	Using Loop Variables
             	How Long Should a Loop Be?
          	16.3. Creating Loops Easily—From the Inside Out
          	16.4. Correspondence Between Loops and Arrays
          	Key Points
       	17. Unusual Control Structures
          	17.1. Multiple Returns from a Routine
          	17.2. Recursion
             	Example of Recursion
             	Tips for Using Recursion
          	17.3. goto
             	The Argument Against gotos
             	The Argument for gotos
             	The Phony goto Debate
             	Error Processing and gotos
                	Comparison of the Approaches
             	gotos and Sharing Code in an else Clause
             	Summary of Guidelines for Using gotos
          	17.4. Perspective on Unusual Control Structures
          	Additional Resources
             	Returns
             	gotos
          	Key Points
       	18. Table-Driven Methods
          	18.1. General Considerations in Using Table-Driven Methods
             	Two Issues in Using Table-Driven Methods
          	18.2. Direct Access Tables
             	Days-in-Month Example
             	Insurance Rates Example
             	Flexible-Message-Format Example
             	Logic-Based Approach
             	Object-Oriented Approach
             	Table-Driven Approach
             	Fudging Lookup Keys
          	18.3. Indexed Access Tables
          	18.4. Stair-Step Access Tables
          	18.5. Other Examples of Table Lookups
          	Key Points
       	19. General Control Issues
          	19.1. Boolean Expressions
             	Using true and false for Boolean Tests
             	Making Complicated Expressions Simple
             	Forming Boolean Expressions Positively
             	Using Parentheses to Clarify Boolean Expressions
             	Knowing How Boolean Expressions Are Evaluated
             	Writing Numeric Expressions in Number-Line Order
             	Guidelines for Comparisons to 0
             	Common Problems with Boolean Expressions
          	19.2. Compound Statements (Blocks)
          	19.3. Null Statements
          	19.4. Taming Dangerously Deep Nesting
             	Summary of Techniques for Reducing Deep Nesting
          	19.5. A Programming Foundation: Structured Programming
             	The Three Components of Structured Programming
                	Sequence
                	Selection
                	Iteration
          	19.6. Control Structures and Complexity
             	How Important Is Complexity?
             	General Guidelines for Reducing Complexity
                	How to Measure Complexity
                	What to Do with Your Complexity Measurement
             	Other Kinds of Complexity
          	Key Points
    	V. Code Improvements
       	20. The Software-Quality Landscape
          	20.1. Characteristics of Software Quality
          	20.2. Techniques for Improving Software Quality
             	Development Process
             	Setting Objectives
          	20.3. Relative Effectiveness of Quality Techniques
             	Percentage of Defects Detected
             	Cost of Finding Defects
             	Cost of Fixing Defects
          	20.4. When to Do Quality Assurance
          	20.5. The General Principle of Software Quality
          	Additional Resources
             	Relevant Standards
          	Key Points
       	21. Collaborative Construction
          	21.1. Overview of Collaborative Development Practices
             	Collaborative Construction Complements Other Quality-Assurance Techniques
             	Collaborative Construction Provides Mentoring in Corporate Culture and Programming Expertise
             	Collective Ownership Applies to All Forms of Collaborative Construction
             	Collaboration Applies As Much Before Construction As After
          	21.2. Pair Programming
             	Keys to Success with Pair Programming
             	Benefits of Pair Programming
          	21.3. Formal Inspections
             	What Results Can You Expect from Inspections?
             	Roles During an Inspection
             	General Procedure for an Inspection
                	Fine-Tuning the Inspection
             	Egos in Inspections
             	Inspections and Code Complete
             	Inspection Summary
          	21.4. Other Kinds of Collaborative Development Practices
             	Walk-Throughs
                	What Results Can You Expect from a Walk-Through?
             	Code Reading
             	Dog-and-Pony Shows
          	Comparison of Collaborative Construction Techniques
          	Additional Resources
             	Pair Programming
             	Inspections
             	Relevant Standards
          	Key Points
       	22. Developer Testing
          	22.1. Role of Developer Testing in Software Quality
             	Testing During Construction
          	22.2. Recommended Approach to Developer Testing
             	Test First or Test Last?
             	Limitations of Developer Testing
          	22.3. Bag of Testing Tricks
             	Incomplete Testing
             	Structured Basis Testing
             	Data-Flow Testing
                	Combinations of Data States
             	Equivalence Partitioning
             	Error Guessing
             	Boundary Analysis
                	Compound Boundaries
             	Classes of Bad Data
             	Classes of Good Data
             	Use Test Cases That Make Hand-Checks Convenient
          	22.4. Typical Errors
             	Which Classes Contain the Most Errors?
             	Errors by Classification
             	Proportion of Errors Resulting from Faulty Construction
             	How Many Errors Should You Expect to Find?
             	Errors in Testing Itself
          	22.5. Test-Support Tools
             	Building Scaffolding to Test Individual Classes
             	Diff Tools
             	Test-Data Generators
             	Coverage Monitors
             	Data Recorder/Logging
             	Symbolic Debuggers
             	System Perturbers
             	Error Databases
          	22.6. Improving Your Testing
             	Planning to Test
             	Retesting (Regression Testing)
             	Automated Testing
          	22.7. Keeping Test Records
             	Personal Test Records
             	Additional Resources
             	Testing
             	Test Scaffolding
             	Test First Development
             	Relevant Standards
          	Key Points
       	23. Debugging
          	23.1. Overview of Debugging Issues
             	Role of Debugging in Software Quality
             	Variations in Debugging Performance
             	Defects as Opportunities
             	An Ineffective Approach
                	The Devil's Guide to Debugging
                	Debugging by Superstition
          	23.2. Finding a Defect
             	The Scientific Method of Debugging
                	Stabilize the Error
                	Locate the Source of the Error
             	Tips for Finding Defects
                	Brute-Force Debugging
             	Syntax Errors
          	23.3. Fixing a Defect
          	23.4. Psychological Considerations in Debugging
             	How "Psychological Set" Contributes to Debugging Blindness
             	How "Psychological Distance" Can Help
          	23.5. Debugging Tools—Obvious and Not-So-Obvious
             	Source-Code Comparators
             	Compiler Warning Messages
             	Extended Syntax and Logic Checking
             	Execution Profilers
             	Test Frameworks/Scaffolding
             	Debuggers
          	Additional Resources
          	Key Points
       	24. Refactoring
          	24.1. Kinds of Software Evolution
             	Philosophy of Software Evolution
          	24.2. Introduction to Refactoring
             	Reasons to Refactor
             	Reasons Not to Refactor
          	24.3. Specific Refactorings
             	Data-Level Refactorings
             	Statement-Level Refactorings
             	Routine-Level Refactorings
             	Class Implementation Refactorings
             	Class Interface Refactorings
             	System-Level Refactorings
          	24.4. Refactoring Safely
             	Bad Times to Refactor
          	24.5. Refactoring Strategies
          	Additional Resources
          	Key Points
       	25. Code-Tuning Strategies
          	25.1. Performance Overview
             	Quality Characteristics and Performance
             	Performance and Code Tuning
                	Program Requirements
                	Program Design
                	Class and Routine Design
                	Operating-System Interactions
                	Code Compilation
                	Hardware
                	Code Tuning
          	25.2. Introduction to Code Tuning
             	The Pareto Principle
             	Old Wives' Tales
             	When to Tune
             	Compiler Optimizations
          	25.3. Kinds of Fat and Molasses
             	Common Sources of Inefficiency
             	Relative Performance Costs of Common Operations
          	25.4. Measurement
             	Measurements Need to Be Precise
          	25.5. Iteration
          	25.6. Summary of the Approach to Code Tuning
          	Additional Resources
             	Performance
             	Algorithms and Data Types
          	Key Points
       	26. Code-Tuning Techniques
          	26.1. Logic
             	Stop Testing When You Know the Answer
             	Order Tests by Frequency
             	Compare Performance of Similar Logic Structures
             	Substitute Table Lookups for Complicated Expressions
             	Use Lazy Evaluation
          	26.2. Loops
             	Unswitching
             	Jamming
             	Unrolling
             	Minimizing the Work Inside Loops
             	Sentinel Values
             	Putting the Busiest Loop on the Inside
             	Strength Reduction
          	26.3. Data Transformations
             	Use Integers Rather Than Floating-Point Numbers
             	Use the Fewest Array Dimensions Possible
             	Minimize Array References
             	Use Supplementary Indexes
                	String-Length Index
                	Independent, Parallel Index Structure
             	Use Caching
          	26.4. Expressions
             	Exploit Algebraic Identities
             	Use Strength Reduction
             	Initialize at Compile Time
             	Be Wary of System Routines
             	Use the Correct Type of Constants
             	Precompute Results
             	Eliminate Common Subexpressions
          	26.5. Routines
             	Rewrite Routines Inline
          	26.6. Recoding in a Low-Level Language
          	26.7. The More Things Change, the More They Stay the Same
          	Additional Resources
          	Key Points
    	VI. System Considerations
       	27. How Program Size Affects Construction
          	27.1. Communication and Size
          	27.2. Range of Project Sizes
          	27.3. Effect of Project Size on Errors
          	27.4. Effect of Project Size on Productivity
          	27.5. Effect of Project Size on Development Activities
             	Activity Proportions and Size
             	Programs, Products, Systems, and System Products
             	Methodology and Size
          	Additional Resources
          	Key Points
       	28. Managing Construction
          	28.1. Encouraging Good Coding
             	Considerations in Setting Standards
             	Techniques for Encouraging Good Coding
             	The Role of This Book
          	28.2. Configuration Management
             	What Is Configuration Management?
             	Requirements and Design Changes
             	Software Code Changes
             	Tool Versions
             	Machine Configurations
             	Backup Plan
             	Additional Resources on Configuration Management
          	28.3. Estimating a Construction Schedule
             	Estimation Approaches
             	Estimating the Amount of Construction
             	Influences on Schedule
             	Estimation vs. Control
             	What to Do If You're Behind
             	Additional Resources on Software Estimation
          	28.4. Measurement
             	Additional Resources on Software Measurement
          	28.5. Treating Programmers as People
             	How Do Programmers Spend Their Time?
             	Variation in Performance and Quality
                	Individual Variation
                	Team Variation
             	Religious Issues
             	Physical Environment
             	Additional Resources on Programmers as Human Beings
          	28.6. Managing Your Manager
             	Additional Resources on Managing Construction
             	Relevant Standards
          	Key Points
       	29. Integration
          	29.1. Importance of the Integration Approach
          	29.2. Integration Frequency—Phased or Incremental?
             	Phased Integration
             	Incremental Integration
             	Benefits of Incremental Integration
          	29.3. Incremental Integration Strategies
             	Top-Down Integration
             	Bottom-Up Integration
             	Sandwich Integration
             	Risk-Oriented Integration
             	Feature-Oriented Integration
             	T-Shaped Integration
             	Summary of Integration Approaches
          	29.4. Daily Build and Smoke Test
             	What Kinds of Projects Can Use the Daily Build Process?
             	Continuous Integration
          	Additional Resources
             	Integration
             	Incrementalism
          	Key Points
       	30. Programming Tools
          	30.1. Design Tools
          	30.2. Source-Code Tools
             	Editing
                	Integrated Development Environments (IDEs)
                	Multiple-File String Searching and Replacing
                	Diff Tools
                	Merge Tools
                	Source-Code Beautifiers
                	Interface Documentation Tools
                	Templates
                	Cross-Reference Tools
                	Class Hierarchy Generators
             	Analyzing Code Quality
                	Picky Syntax and Semantics Checkers
                	Metrics Reporters
             	Refactoring Source Code
                	Refactorers
                	Restructurers
                	Code Translators
             	Version Control
             	Data Dictionaries
          	30.3. Executable-Code Tools
             	Code Creation
                	Compilers and Linkers
                	Build Tools
                	Code Libraries
                	Code-Generation Wizards
                	Setup and Installation
                	Preprocessors
             	Debugging
             	Testing
             	Code Tuning
                	Execution Profilers
                	Assembler Listings and Disassemblers
          	30.4. Tool-Oriented Environments
          	30.5. Building Your Own Programming Tools
             	Project-Specific Tools
             	Scripts
          	30.6. Tool Fantasyland
          	Additional Resources
          	Key Points
    	VII. Software Craftsmanship
       	31. Layout and Style
          	31.1. Layout Fundamentals
             	Layout Extremes
             	The Fundamental Theorem of Formatting
             	Human and Computer Interpretations of a Program
             	How Much Is Good Layout Worth?
             	Layout as Religion
             	Objectives of Good Layout
                	How to Put the Layout Objectives to Use
          	31.2. Layout Techniques
             	White Space
             	Parentheses
          	31.3. Layout Styles
             	Pure Blocks
             	Emulating Pure Blocks
             	Using begin-end Pairs (Braces) to Designate Block Boundaries
             	Endline Layout
             	Which Style Is Best?
          	31.4. Laying Out Control Structures
             	Fine Points of Formatting Control-Structure Blocks
             	Other Considerations
          	31.5. Laying Out Individual Statements
             	Statement Length
             	Using Spaces for Clarity
             	Formatting Continuation Lines
             	Using Only One Statement Per Line
             	Laying Out Data Declarations
          	31.6. Laying Out Comments
          	31.7. Laying Out Routines
          	31.8. Laying Out Classes
             	Laying Out Class Interfaces
             	Laying Out Class Implementations
             	Laying Out Files and Programs
          	Additional Resources
          	Key Points
       	32. Self-Documenting Code
          	32.1. External Documentation
          	32.2. Programming Style as Documentation
          	32.3. To Comment or Not to Comment
          	32.4. Keys to Effective Comments
             	Kinds of Comments
                	Repeat of the Code
                	Explanation of the Code
                	Marker in the Code
                	Summary of the Code
                	Description of the Code's Intent
                	Information That Cannot Possibly Be Expressed by the Code Itself
             	Commenting Efficiently
             	Optimum Number of Comments
          	32.5. Commenting Techniques
             	Commenting Individual Lines
                	Endline Comments and Their Problems
                	When to Use Endline Comments
             	Commenting Paragraphs of Code
             	Commenting Data Declarations
             	Commenting Control Structures
             	Commenting Routines
             	Commenting Classes, Files, and Programs
                	General Guidelines for Class Documentation
                	General Guidelines for File Documentation
                	The Book Paradigm for Program Documentation
          	32.6. IEEE Standards
             	Software-Development Standards
             	Software Quality-Assurance Standards
             	Management Standards
             	Overview of Standards
          	Additional Resources
          	Key Points
       	33. Personal Character
          	33.1. Isn't Personal Character Off the Topic?
          	33.2. Intelligence and Humility
          	33.3. Curiosity
          	33.4. Intellectual Honesty
          	33.5. Communication and Cooperation
          	33.6. Creativity and Discipline
          	33.7. Laziness
          	33.8. Characteristics That Don't Matter As Much As You Might Think
             	Persistence
             	Experience
             	Gonzo Programming
          	33.9. Habits
          	Additional Resources
          	Key Points
       	34. Themes in Software Craftsmanship
          	34.1. Conquer Complexity
          	34.2. Pick Your Process
          	34.3. Write Programs for People First, Computers Second
          	34.4. Program into Your Language, Not in It
          	34.5. Focus Your Attention with the Help of Conventions
          	34.6. Program in Terms of the Problem Domain
             	Separating a Program into Levels of Abstraction
                	Level 0: Operating-System Operations and Machine Instructions
                	Level 1: Programming-Language Structures and Tools
                	Level 2: Low-Level Implementation Structures
                	Level 3: Low-Level Problem-Domain Terms
                	Level 4: High-Level Problem-Domain Terms
             	Low-Level Techniques for Working in the Problem Domain
          	34.7. Watch for Falling Rocks
          	34.8. Iterate, Repeatedly, Again and Again
          	34.9. Thou Shalt Rend Software and Religion Asunder
             	Software Oracles
             	Eclecticism
             	Experimentation
          	Key Points
       	35. Where to Find More Information
          	35.1. Information About Software Construction
          	35.2. Topics Beyond Construction
             	Overview Material
             	Software-Engineering Overviews
             	Other Annotated Bibliographies
          	35.3. Periodicals
             	Lowbrow Programmer Magazines
             	Highbrow Programmer Journals
             	Special-Interest Publications
                	Professional Publications
                	Popular-Market Publications
          	35.4. A Software Developer's Reading Plan
             	Introductory Level
             	Practitioner Level
             	Professional Level
          	35.5. Joining a Professional Organization
    	Bibliography
    	Index
    	SPECIAL OFFER: Upgrade this ebook with O’Reilly