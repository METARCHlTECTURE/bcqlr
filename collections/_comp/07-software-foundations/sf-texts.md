---
title: Texts of Software Foundations
---

原书地址：https://softwarefoundations.cis.upenn.edu/；版本：Version 6.6 (2024-01-03 15:03, Coq 8.17 or later)；翻译来自 ChatGPT-4o；释义来自于必应词典；本页面仅供个人学习，不对外开放，无法被搜索引擎收录。

# Volume 1 Logical Foundations 逻辑基础

## Preface 前言

### Welcome 欢迎

This is the entry point to a series of electronic textbooks on various aspects of Software Foundations, the mathematical underpinnings of reliable software. Topics in the series include basic concepts of logic, computer-assisted theorem proving, the Coq proof assistant, functional programming, operational semantics, logics and techniques for reasoning about programs, static type systems, property-based random testing, and verification of practical C code. The exposition is intended for a broad range of readers, from advanced undergraduates to PhD students and researchers. No specific background in logic or programming languages is assumed, though a degree of mathematical maturity will be helpful.

这是《软件基础》系列电子教材的入口，涵盖了可靠软件的数学基础。该系列的主题包括逻辑基本概念、计算机辅助定理证明、Coq证明助手、函数式编程、操作语义、程序推理的逻辑和技术、静态类型系统、基于属性的随机测试，以及实际C代码的验证。本系列旨在面向广泛的读者群体，从高年级本科生到博士生及研究人员。尽管不需要具备特定的逻辑或编程语言背景，但具备一定的数学成熟度会有所帮助。

  - underpinning [ˈʌndə(r)ˌpɪnɪŋ] n.支柱；〈口〉加支柱；墙基；支援
    - underpin [ˌʌndə(r)ˈpɪn] v.巩固；加固（墙）基
  - `计算机辅助定理证明（Computer-Assisted Theorem Proving, 简称 CATP）`是指使用计算机软件来帮助验证数学定理的真伪。在计算机辅助定理证明中，计算机程序被用来检查定理证明的每一个步骤，确保所有逻辑推理都是正确的。与传统的手工证明相比，计算机辅助定理证明能够处理更加庞大和复杂的证明，减少人工错误，提高证明的可靠性。Coq、Isabelle、HOL Light 和 Lean 是一些常见的定理证明器。它们提供了一个框架，用户可以在其中构建和验证证明。`模型检测（Model Checking）`是另一种形式的计算机辅助证明，主要用于验证有限状态系统的性质。通过遍历系统的所有可能状态，模型检测可以验证系统是否满足特定的逻辑性质。
  - `函数式编程（Functional Programming）`是一种编程范式，它强调使用函数来构建和组合程序，尤其注重不可变性和纯函数的使用。纯函数是指那些在相同输入下始终产生相同输出、且不产生任何副作用（如修改全局变量或执行I/O操作）的函数。
  - `操作语义（Operational Semantics）`是计算机科学中的一种形式化方法，用于定义编程语言的行为。它描述了程序的执行方式，即程序的每个操作或语句在特定语境下的运行步骤。这种方法通过给出一个程序在计算机上逐步执行的规则，来描述程序的语义。操作语义通常用一种数学化的方式来表达，常见的方法包括大步语义（big-step semantics）和小步语义（small-step semantics）。
  - exposition [.ekspə'zɪʃ(ə)n] n.阐述；（产品的）展销；商品交易会；产品博览会

The principal novelty of the series is that it is one hundred percent formalized and machine-checked: each text is literally a script for Coq. The books are intended to be read alongside (or inside) an interactive session with Coq. All the details in the text are fully formalized in Coq, and most of the exercises are designed to be worked using Coq.

本系列的主要创新之处在于其内容完全形式化且经过机器验证：每本书实际上都是一个Coq脚本。这些书籍需要与Coq的交互会话一起阅读，或者在会话中进行阅读。书中所有细节都在Coq中完全形式化，且大部分练习设计为使用Coq来完成。

  - principal ['prɪnsəp(ə)l] n.本金；委托人；资本；主角 adj.最重要的；主要的（与 principle 同音）
  - novelty [ˈnɒv(ə)lti] n.新颖；新奇；新鲜；新奇的事物（或人、环境） adj.新奇的；风格独特的

The files in each book are organized into a sequence of core chapters, covering about one semester's worth of material and organized into a coherent linear narrative, plus a number of "offshoot" chapters covering additional topics. All the core chapters are suitable for both upper-level undergraduate and graduate students.

每本书的文件分为一系列核心章节，涵盖大约一个学期的内容，并按照连贯的线性叙事组织起来，此外还有一些“分支”章节，涵盖额外的主题。所有核心章节都适合本科高年级和研究生。

  - coherent [kəʊˈhɪərənt] adj.合乎逻辑的；有条理的；清楚易懂的；有表达能力的
  - narrative [ˈnærətɪv] n.叙述；讲故事；叙事技巧 adj.叙述的；故事体的；善于叙述的
  - offshoot [ˈɒfˌʃuːt] n.分支；（尤指）分支机构；蘗枝；分枝

This book, Logical Foundations, lays groundwork for the others, introducing the reader to the basic ideas of functional programming, constructive logic, and the Coq proof assistant.

本书《逻辑基础》为其他书奠定基础，向读者介绍了函数式编程、构造逻辑和Coq证明助手的基本思想。

  - groundwork [ˈɡraʊn(d)ˌwɜː(r)k] n.基础工作；准备工作
  - `构造性逻辑（Constructive Logic）`，也称为`直觉主义逻辑（Intuitionistic Logic）`，是一种逻辑体系，强调证明的构造性和可计算性。在构造性逻辑中，要证明一个命题成立，必须明确地构造出一个证明，而不仅仅是通过排除所有其他可能性来证明其存在。与经典逻辑不同，构造性逻辑拒绝使用排中律（Law of Excluded Middle），即命题 \( P \) 或其否定 \( \neg P \) 必有一个成立。在构造性逻辑中，只有当我们能够构造出 \( P \) 的证明时，才能断定 \( P \) 为真。构造性逻辑在计算机科学中有广泛的应用，尤其是在形式化证明、类型理论和编程语言设计领域。例如，Coq这样的定理证明器基于构造性逻辑，允许用户通过构造性的方式来编写程序和证明数学命题。因为每个证明都具有计算内容，构造性逻辑也与可计算性理论密切相关。

### Overview 概述

Building **reliable software** is really hard -- really hard. The scale and complexity of modern systems, the number of people involved, and the range of demands placed on them make it challenging to build software that is even more-or-less correct, much less 100% correct. At the same time, the increasing degree to which information processing is woven into every aspect of society greatly amplifies the cost of bugs and insecurities.

构建**可靠的软件**非常困难——非常困难。现代系统的规模和复杂性、涉及人员的数量以及对系统的广泛需求，使得构建即使是“基本正确”的软件都很具有挑战性，更不用说100%正确的软件了。同时，信息处理在社会各个方面的渗透程度不断提高，放大了软件漏洞和安全问题的代价。

  - still/much/even less 更不用说；更何况
  - weave wove woven 编织；交织
  - amplify ['æmplɪ.faɪ] v.放大；阐发

Computer scientists and software engineers have responded to these challenges by developing a host of techniques for improving software reliability, ranging from recommendations about managing software projects teams (e.g., extreme programming) to design philosophies for libraries (e.g., model-view-controller, publish-subscribe, etc.) and programming languages (e.g., object-oriented programming, aspect-oriented programming, functional programming, ...) to **mathematical techniques for specifying and reasoning about properties of software and tools for helping validate these properties**. The Software Foundations series is focused on this last set of tools.

计算机科学家和软件工程师通过开发一系列技术来应对这些挑战，这些技术包括关于如何管理软件项目团队的建议（如极限编程）、库的设计理念（如模型-视图-控制器、发布-订阅等）以及编程语言的设计理念（如面向对象编程、面向方面编程、函数式编程等），以及**数学技术来指定和推理软件的性质并帮助验证这些性质**。《软件基础》系列主要集中在最后一类工具上。

  - a host of 许多的，大量的
  - `极限编程（Extreme Programming，简称XP）`是一种敏捷软件开发方法，由Kent Beck在20世纪90年代提出。它是一种以提高软件质量和增强开发团队的响应能力为目标的方法，核心理念包括：客户参与、持续反馈、简单设计、持续集成、测试驱动开发（TDD）、结对编程、持续重构、小型发布、集体代码所有权、40小时工作周。
  - `Model-View-Controller（MVC）`是一种软件架构模式，用于分离应用程序的逻辑、用户界面和数据模型。它通过将应用程序的不同部分分开管理，使得代码更加模块化、易于维护和扩展。MVC 广泛应用于图形用户界面应用程序以及Web应用程序的设计和开发。
  - `面向对象编程（Object-Oriented Programming, OOP）`是一种编程范式，它将程序设计任务分解为一个个对象，而每个对象都是一个类的实例。对象封装了数据（属性）和行为（方法），这样可以更好地组织代码，使其更易于管理和扩展。
  - `面向方面编程（Aspect-Oriented Programming, AOP）`是一种编程范式，旨在提高代码的模块化，特别是**关注点的分离**。AOP通过将那些跨越多个模块的关注点（如日志记录、安全性、事务管理等）从核心业务逻辑中分离出来，使代码更加清晰和可维护。在面向对象编程中，有些功能（如日志记录或错误处理）往往会在多个类或方法中重复出现，这些功能被称为`横切关注点（Cross-Cutting Concerns）`。AOP的目标就是将这些横切关注点提取出来，并将其与核心业务逻辑分离。

This volume weaves together three conceptual threads:
  1. basic tools from logic for making and **justifying precise claims about programs**;
  2. the use of proof assistants to **construct rigorous logical arguments**;
  3. functional programming, both as **a method of programming that simplifies reasoning about programs** and as **a bridge between programming and logic**.

本书将三条概念线索交织在一起：
1. 逻辑中的基本工具，用于**对程序进行精确的断言和证明**。
2. 使用证明助手来构建**严谨的逻辑论证**。
3. 函数式编程，既作为**简化程序推理的一种编程方法**，也作为**连接编程与逻辑的桥梁**。

  - rigorous ['rɪɡərəs] adj.谨慎的；细致的；彻底的；严格的

#### Logic 逻辑

`Logic` is the field of study whose **subject matter is proofs** -- *unassailable arguments for the truth of particular propositions*. Volumes have been written about the central role of logic in computer science. Manna and Waldinger called it "the calculus of computer science," while Halpern et al.'s paper On the *Unusual Effectiveness of Logic in Computer Science* catalogs scores of ways in which logic offers critical tools and insights. Indeed, they observe that, "As a matter of fact, logic has turned out to be significantly more effective in computer science than it has been in mathematics. This is quite remarkable, especially since much of the impetus for the development of logic during the past one hundred years came from mathematics."

`逻辑`是**研究证明**的学科——*对特定命题的不可争辩的真理性论证*。关于逻辑在计算机科学中的核心作用已经有许多著作。Manna 和 Waldinger 称其为“计算机科学的微积分”，而 Halpern 等人的论文《逻辑在计算机科学中的非同寻常的有效性》列举了逻辑在计算机科学中提供关键工具和洞察力的诸多方式。实际上，他们指出，“已经成为事实的是，逻辑在计算机科学中的有效性明显超过了在数学中的有效性。这非常引人注目，特别是因为过去一百年间逻辑的发展动力主要来自数学。”

  - unassailable [.ʌnə'seɪləb(ə)l] adj.无法摧毁的；不可战胜的；不容置疑的
    - assail [ə'seɪl] v.攻击；困扰；袭击；抨击
    - assailant [ə'seɪlənt] n.攻击者；行凶者 adj.攻击的
  - (play a) central role (in) 在……中起着核心作用
  - scores of 许多，大量
  - impetus [ˈɪmpɪtəs] n.动力；推动；促进；刺激

In particular, *the fundamental tools of **inductive proof** are ubiquitous in all of computer science*. You have surely seen them before, perhaps in a course on discrete math or analysis of algorithms, but in this course we will examine them more deeply than you have probably done so far.

尤其是，归纳证明的基本工具在整个计算机科学中无处不在。你以前可能在离散数学或算法分析课程中见过它们，但在本课程中，我们将比你以前所做的更深入地研究它们。

  - ubiquitous  [juːˈbɪkwɪtəs] adj.似乎无所不在的；十分普遍的

#### Proof Assistants 证明助手

The flow of ideas between logic and computer science has not been unidirectional: CS has also made important contributions to logic. One of these has been the development of **software tools for helping construct proofs of logical propositions**. These tools fall into two broad categories:

逻辑与计算机科学之间的思想流动并非单向：计算机科学也对逻辑做出了重要贡献。其中之一就是开发了**帮助构建逻辑命题证明的软件工具**。这些工具大致分为两类：

  - the flow of ideas 思绪；思维的流动；灵感；源源不断的想法
  - unidirectional 单向性的；单向关联；单方向

`Automated theorem provers` provide "push-button" operation: **you give them a proposition and they return either true or false (or, sometimes, don't know: ran out of time)**. Although their capabilities are still limited to specific domains, they have matured tremendously in recent years and are used now in a multitude of settings. Examples of such tools include `SAT solvers`, `SMT solvers`, and `model checkers`.

`自动定理证明器`提供“按下按钮”操作：**你给它一个命题，它返回真或假（有时会返回“未知：超时”）**。尽管它们的能力仍限于特定领域，但近年来已经大大成熟，并且现在被广泛应用于各种场合。此类工具的例子包括`SAT求解器`、`SMT求解器`和`模型检查器`。

  - `自动定理证明器（Automated Theorem Provers，简称ATP）`是用于自动证明或反驳数学定理的软件工具。这些工具在形式逻辑的领域中操作，定理被表示为形式化的语句，目标是通过逻辑推理规则来判断这些语句的有效性，而无需人为干预。其步骤为：
    - 定理的形式化：定理和假设被表示为形式化语言，通常是谓词逻辑的一种形式。这需要精确的定义和表达，以避免歧义。
    - 使用算法来探索可能的证明空间。它们应用逻辑推理规则，从现有的语句生成新的语句，寻找从假设到定理的一系列步骤。
    - 如果找到了一系列有效的逻辑步骤能够得出定理，自动定理证明器就会宣布定理得到证明。
  - tremendous(ly) [trə'mendəs] adj.巨大的；极大的；极好的；精彩的 adv.非常
  - `SAT求解器（SAT Solvers）`是一类专门用于解决`布尔可满足性问题（Boolean Satisfiability Problem，简称SAT）`的算法或工具。SAT问题中的布尔公式由布尔变量和逻辑运算符（如与、或、非）组成。SAT问题的目标是找到一种布尔变量的赋值，使得整个公式为真。
  - `SMT求解器（SMT Solvers）`是用于解决`可满足性模理论问题（Satisfiability Modulo Theories，简称SMT）`的工具。SMT问题是布尔可满足性问题（SAT问题）的推广，涉及在特定理论下判断一个逻辑公式是否可满足。
    - `模理论（Modulo ['mɒdjʊləʊ] Theories）`：SMT问题不仅涉及布尔逻辑，还包含各种理论，如算术（整数和实数）、数组、位向量、数据结构（如列表、集合）、以及线性整数或实数约束等。这些理论为变量赋值提供了更复杂的约束。
  - `模型检验器（Model Checker）`是一种自动化工具，用于验证系统模型（通常是硬件或软件系统）是否符合某些规范或属性。模型检验器通过系统地检查所有可能的状态和状态转移来确保模型的行为符合预期，*特别是在并发系统或嵌入式系统的验证中*，模型检验器被广泛应用。

`Proof assistants` are hybrid tools that automate the more routine aspects of building proofs while depending on human guidance for more difficult aspects. Widely used proof assistants include Isabelle, Agda, Twelf, ACL2, PVS, and Coq, among many others.

`证明助手`是混合工具，能够自动化构建证明过程中较为常规的部分，同时依赖人类的指导来处理较难的部分。广泛使用的证明助手包括Isabelle、Agda、Twelf、ACL2、PVS和Coq等。

  - `证明辅助工具（Proof Assistants）`，也称为`交互式定理证明器`，是一类软件工具，帮助用户在数学和逻辑领域中构建和验证形式化证明。**与自动定理证明器不同**，证明辅助工具通常**需要用户提供更多的指导**，用户通过与工具的交互**逐步构建证明**。

This course is based around Coq, a proof assistant that has been under development since 1983 and that in recent years has attracted a large community of users in both research and industry. Coq **provides a rich environment for interactive development of machine-checked formal reasoning**. The kernel of the Coq system is a simple proof-checker, which guarantees that only correct deduction steps are ever performed. On top of this kernel, the Coq environment provides high-level facilities for proof development, including a large library of common definitions and lemmas, powerful tactics for constructing complex proofs semi-automatically, and a special-purpose programming language for defining new proof-automation tactics for specific situations.

本课程围绕Coq展开，这是一款自1983年以来一直在开发的证明助手，近年来吸引了大量研究和工业用户。Coq**为`机器验证的形式化推理`提供了一个丰富的交互式开发环境**。Coq系统的**内核是一个简单的证明检查器**，确保只执行正确的推理步骤。在此内核之上，Coq环境提供了高层次的**证明开发工具**，包括一个庞大的**常见定义和引理库、强大的策略**，用于半自动地构建复杂的证明，以及一个**专用的编程语言**，用于为特定情况定义新的自动化证明策略。

  - `形式化推理（Formal Reasoning）`是指使用**严格定义的逻辑和数学规则**来进行**推理**的过程。它涉及将问题、陈述或系统的行为表达为精确的形式化语言，并通过应用逻辑推理规则来得出结论或证明某个陈述的真伪。
  - `机器验证的形式化推理（Machine-Checked Formal Reasoning）`是指通过计算机辅助工具进行的形式化推理过程，其中推理的所有步骤和结论都由机器自动检查和验证。与传统的手工形式化推理不同，这种方法利用自动化工具确保推理的每一步都是逻辑上正确的，极大地提高了验证的可靠性和效率。

Coq has been a critical enabler for a huge variety of work across computer science and mathematics:
  - As **a platform for modeling programming languages**, it has become **a standard tool for researchers who need to describe and reason about complex language definitions**. It has been used, for example, to check the security of the JavaCard platform, obtaining the highest level of common criteria certification, and for formal specifications of the x86 and LLVM instruction sets and programming languages such as C.
  - As **an environment for developing formally certified software and hardware**, Coq has been used, for example, to build CompCert, a fully-verified optimizing compiler for C, and CertiKOS, a fully verified hypervisor, for proving the correctness of subtle algorithms involving floating point numbers, and as the basis for CertiCrypt, an environment for reasoning about the security of cryptographic algorithms. It is also being used to build verified implementations of the open-source RISC-V processor architecture.
  - As a realistic environment for **functional programming with dependent types**, it has inspired numerous innovations. For example, the Ynot system embeds "relational Hoare reasoning" (an extension of the Hoare Logic we will see later in this course) in Coq.
  - As a proof assistant for higher-order logic, it has been used to validate a number of important results in mathematics. For example, its ability to include complex computations inside proofs made it possible to develop the first formally verified proof of the `4-color theorem`. This proof had previously been controversial among mathematicians because it required checking a large number of configurations using a program. In the Coq formalization, everything is checked, including the correctness of the computational part. More recently, an even more massive effort led to a Coq formalization of the Feit-Thompson Theorem, the first major step in the classification of finite simple groups.

Coq为计算机科学和数学的众多工作提供了重要支持：
  - 作为一种**编程语言建模的平台**，它已**成为需要描述和推理复杂语言定义的研究人员的标准工具**。例如，它被用来检查JavaCard平台的安全性，从而获得了最高级别的通用标准认证，还用于x86和LLVM指令集、编程语言（如C）的形式化规范。
  - 作为一种**用于开发形式认证软件和硬件的环境**，Coq已被用于构建CompCert（一个完全验证的C优化编译器）、CertiKOS（一个完全验证的虚拟机监视器）、用于证明涉及浮点数的复杂算法的正确性，并作为CertiCrypt的基础（一个用于推理加密算法安全性的环境）。它还被用于构建开源RISC-V处理器架构的验证实现。
  - 作为具有依赖类型的函数式编程的现实环境，它启发了许多创新。例如，Ynot系统在Coq中嵌入了“关系Hoare推理”（Hoare逻辑的扩展，我们将在本课程后面看到）。
  - 作为高阶逻辑的证明助手，它被用来验证数学中的许多重要结果。例如，它将复杂计算包含在证明中的能力，使得开发`四色定理`的第一个正式验证成为可能。该证明曾在数学家中引发争议，因为它需要使用程序检查大量配置。在Coq形式化中，一切都得到了验证，包括计算部分的正确性。最近，一项更为庞大的努力导致了Feit-Thompson定理的Coq形式化，这是分类有限单群的第一步。

  - `JavaCard平台`是一种微型平台，允许智能卡和其他小型嵌入式设备运行Java程序。
  - `Common Criteria Certification（通用准则认证）`是一种国际公认的标准，用于评估和认证信息技术（IT）产品和系统的安全性。Common Criteria (CC) 是一个框架，允许用户、开发者和测试实验室使用统一的标准来评估产品的安全属性，确保产品能够满足特定的安全需求。
    - criteria [kraɪˈtɪəriən] n.标准；尺度
    - certification  [ˌsɜ:tɪfɪ'keɪʃn] n.证书；证明；检定；合格证
  - `Formal Specifications（形式化规范）`是用数学方法精确定义系统或软件行为的描述方式。形式化规格通过使用形式化语言（如逻辑、集合论、代数等），为系统的设计、开发和验证提供了一个精确且无二义性的基础。
  - `x86指令集架构（ISA, Instruction Set Architecture）`属于CISC架构，是由英特尔开发的计算机处理器指令集架构，规定了处理器可以执行的指令、寄存器的使用、内存地址模式以及与操作系统和应用程序的交互方式。x86指令集具有很强的向后兼容性，从最早的8086处理器到现代的x86-64处理器，新的处理器可以执行旧的x86指令。
  - `LLVM（Low-Level Virtual Machine）指令集`是LLVM编译器基础设施项目中的一种`中间表示（IR, Intermediate Representation）`，用于描述程序的逻辑和操作。在编译器中，LLVM IR**起着桥梁作用，将高级语言代码转换为底层机器代码**。LLVM IR被设计为一个`面向静态单赋值（SSA, Static Single Assignment）`的语言，是一种**高级的、平台无关的中间表示形式**。
  - `CompCert`是一个用于编写高可靠性软件的C编译器，主要用于需要高度安全性和准确性的系统中，例如航空航天、军事和医疗设备。它由法国Inria研究所开发，独特之处在于其编译器的正确性得到了形式化验证。
  - `CertiKOS`是一个经过形式化验证的微内核操作系统，旨在为高安全性和高可靠性系统提供基础。它是由耶鲁大学的计算机科学团队开发的，其核心部分通过Coq证明助手，使用了形式化方法来验证操作系统的正确性。CertiKOS的主要目标是确保内核代码的安全性、可靠性和正确性，特别是在并发执行环境中。
  - hypervisor ['haɪpəvaɪzə] n.管理程序
  - subtle ['sʌt(ə)l] adj.不易察觉的；不明显的；微妙的；机智的
  - `Cryptographic Algorithms（加密算法）`是用于保护信息安全的数学方法和技术。它们通过加密和解密过程确保数据的机密性、完整性和真实性。加密算法可以分为对称加密、非对称加密、哈希函数和数字签名等几类，每一类算法都有其特定的用途和特点。
    - cryptographic ['krɪptəʊ'græfɪk] adj.关于暗号的 n.隐晶文象状
  - `Ynot`是一个基于Coq证明助手的系统，旨在形式化地描述和验证具有副作用的程序。它提供了一个框架，使得开发者能够在Coq中编写和验证具有副作用的程序，比如那些涉及状态变更、I/O操作或并发的程序。
  - `Hoare Reasoning`，也称为`Hoare Logic`，是一种**用于形式化验证程序正确性的逻辑系统**。它以C.A.R. Hoare在1969年提出的`Hoare三元组（Hoare Triple）`为基础，帮助开发者证明程序在特定条件下的正确性。Hoare Logic 被广泛应用于程序验证和编译器优化等领域。
    - 其核心概念Hoare三元组，通常表示为：{𝑃} 𝐶 {𝑄}。P（前置条件）：程序 𝐶 执行之前应满足的条件。C（程序）：待验证的程序片段或语句。Q（后置条件）：程序 𝐶 执行完成后应满足的条件。
    - `Relational Hoare Reasoning` 是一种扩展的 Hoare 逻辑，用于形式化验证两个程序之间的关系。传统的 Hoare 逻辑（Hoare Logic）通常用于验证一个程序的前置条件（precondition）和后置条件（postcondition），而 Relational Hoare Logic (RHL) 则将这种思路推广到比较两个程序的行为。
  - `四色定理（Four Color Theorem）`是图论中的一个著名定理，涉及地图的着色问题。它断言，对于任何一个平面地图，只需要使用不超过四种颜色，就可以使得地图上的相邻区域（即有共同边界的区域）着色不同。 
    - 四色定理最早由英格兰数学家弗朗西斯·古斯里（Francis Guthrie）在1852年提出，但正式的证明在一个多世纪内都未能成功。
    - Kenneth Appel 和 Wolfgang Haken 在1976年首次使用计算机辅助证明了四色定理。他们的方法通过将问题分解成大量的特殊情况，然后使用计算机验证每一种情况都满足四色定理。这个证明非常复杂，涉及上千小时的计算机计算，虽然产生了一些争议，但最终被数学界接受。*它成为了数学史上第一个通过计算机辅助证明的重要定理。*

By the way, in case you're wondering about the name, here's what the official Coq web site at INRIA (the French national research lab where Coq has mostly been developed) says about it: "Some French computer scientists have a tradition of naming their software as animal species: Caml, Elan, Foc or Phox are examples of this tacit convention. In French, 'coq' means rooster, and it sounds like the initials of the Calculus of Constructions (CoC) on which it is based." The rooster is also the national symbol of France, and C-o-q are the first three letters of the name of Thierry Coquand, one of Coq's early developers.

顺便说一下，如果你对Coq的名字感到好奇，以下是INRIA（主要开发Coq的法国国家研究实验室）官方网站上的解释：“一些法国计算机科学家有一个将他们的软件命名为动物种类的传统：Caml、Elan、Foc或Phox就是这种默许惯例的例子。在法语中，‘coq’的意思是公鸡，它听起来像CoC（构造微积分）的首字母缩写，这是其基础。公鸡也是法国的国家象征，C-o-q也是Coq早期开发者之一Thierry Coquand的名字的前三个字母。”

#### Functional Programming 函数式编程

The term functional programming refers both to a collection of programming idioms that can be used in almost any programming language and to a family of programming languages designed to emphasize these idioms, including Haskell, OCaml, Standard ML, F#, Scala, Scheme, Racket, Common Lisp, Clojure, Erlang, and Coq.

函数式编程这个术语既指可以在几乎任何编程语言中使用的一组编程习惯，也指一组强调这些习惯的编程语言，包括Haskell、OCaml、Standard ML、F#、Scala、Scheme、Racket、Common Lisp、Clojure、Erlang和Coq。

Functional programming has been developed over many decades -- indeed, its roots go back to Church's lambda-calculus, which was invented in the 1930s, well before the first electronic computers! But since the early '90s it has enjoyed a surge of interest among industrial engineers and language designers, playing a key role in high-value systems at companies like Jane Street Capital, Microsoft, Facebook, Twitter, and Ericsson.

函数式编程已经发展了数十年——实际上，其根源可以追溯到1930年代Church发明的λ演算，远早于第一台电子计算机的出现！但是，自90年代初以来，它在工业工程师和语言设计者中重新引起了极大的兴趣，成为像Jane Street Capital、微软、Facebook、Twitter和爱立信等公司关键系统中的核心部分。

The most basic tenet of functional programming is that, as much as possible, computation should be pure, in the sense that the only effect of execution should be to produce a result: it should be free from side effects such as I/O, assignments to mutable variables, redirecting pointers, etc. For example, whereas an imperative sorting function might take a list of numbers and rearrange its pointers to put the list in order, a pure sorting function would take the original list and return a new list containing the same numbers in sorted order.

函数式编程最基本的原则是，尽可能地，使计算纯粹化，意味着执行的唯一效果应当是生成结果：它应当避免诸如I/O、可变变量赋值、指针重定向等副作用。例如，一个命令式的排序函数可能会接受一个数字列表并重新排列其指针以使列表有序，而一个纯排序函数则会接受原列表并返回一个包含相同数字的有序新列表。

A significant benefit of this style of programming is that it makes programs easier to understand and reason about. If every operation on a data structure yields a new data structure, leaving the old one intact, then there is no need to worry about how that structure is being shared and whether a change by one part of the program might break an invariant relied on by another part of the program. These considerations are particularly critical in concurrent systems, where every piece of mutable state that is shared between threads is a potential source of pernicious bugs. Indeed, a large part of the recent interest in functional programming in industry is due to its simpler behavior in the presence of concurrency.

这种编程风格的一个显著好处是，它使程序更易于理解和推理。如果对数据结构的每个操作都会产生一个新的数据结构，并且保持旧的数据结构不变，那么就不需要担心该结构是如何被共享的，也不需要担心程序的某个部分进行的更改会破坏另一个部分依赖的不变量。这些考虑在并发系统中特别关键，因为每一个在线程间共享的可变状态都是可能导致严重错误的潜在来源。实际上，业界对函数式编程的兴趣大部分是因为它在并发情况下表现出更简单的行为。

Another reason for the current excitement about functional programming is related to the first: functional programs are often much easier to parallelize and physically distribute than their imperative counterparts. If running a computation has no effect other than producing a result, then it does not matter where it is run. Similarly, if a data structure is never modified destructively, then it can be copied freely, across cores or across the network. Indeed, the "Map-Reduce" idiom, which lies at the heart of massively distributed query processors like Hadoop and is used by Google to index the entire web is a classic example of functional programming.

对函数式编程的当前兴奋点的另一个原因也与第一个原因相关：函数式程序通常比命令式程序更容易并行化和物理分布。如果运行一个计算除了产生结果之外没有其他影响，那么它在哪里运行并不重要。同样地，如果数据结构从未被破坏性修改，那么它可以自由地复制，无论是在不同的处理器核心之间还是在网络上。实际上，Map-Reduce这种模式正是函数式编程的经典示例，它在Hadoop等大规模分布式查询处理器中起到了核心作用，并被Google用来索引整个互联网。

For purposes of this course, functional programming has yet another significant attraction: it serves as a bridge between logic and computer science. Indeed, Coq itself can be viewed as a combination of a small but extremely expressive functional programming language plus a set of tools for stating and proving logical assertions. Moreover, when we come to look more closely, we find that these two sides of Coq are actually aspects of the very same underlying machinery -- i.e., proofs are programs.

对于本课程的目的，函数式编程还有另一个显著的吸引力：它可以作为逻辑与计算机科学之间的桥梁。实际上，Coq本身可以被视为一个小而非常表达力强的函数式编程语言与一组用于陈述和证明逻辑断言的工具的结合体。此外，当我们仔细观察时，我们会发现Coq的这两个方面实际上是同一个基础机制的两个方面——即证明就是程序。

#### Further Reading 延伸阅读

This text is intended to be self contained, but readers looking for a deeper treatment of particular topics will find some suggestions for further reading in the Postscript chapter. Bibliographic information for all cited works can be found in the file Bib.

本文旨在自成一体，但对于希望深入探讨特定主题的读者，可以在附录章节找到进一步阅读的建议。所有引用作品的书目信息都可以在 Bib 文件中找到。

### Practicalities 实践操作指南

#### System Requirements 系统需求

Coq runs on Windows, Linux, and macOS. The files in this book have been tested with Coq 8.17.

Coq 可以在 Windows、Linux 和 macOS 上运行。本书中的文件已在 Coq 8.17 版本上进行过测试。

You will need:
  - A current installation of Coq, available from the Coq home page. The "Coq Platform" usually offers the smoothest installation experience.
  - If you use the VSCode + Docker option described below, you don't need to install Coq separately.
  - An IDE for interacting with Coq. There are several choices:
    - The VSCoq extension for Visual Studio Code offers a simple interface via a familiar IDE. This option is the recommended default.
    - VSCoq can be used as an ordinary IDE or it can be combined with Docker (see below) for a lightweight installation experience.
    - Proof General is an Emacs-based IDE. It tends to be preferred by users who are already comfortable with Emacs. It requires a separate installation (google "Proof General").
    - Adventurous users of Coq within Emacs may want to check out extensions such as company-coq and control-lock.
    - CoqIDE is a simpler stand-alone IDE. It is distributed with Coq, so it should be available once you have Coq installed. It can also be compiled from scratch, but on some platforms this may involve installing additional packages for GUI libraries and such.
    - Users who like CoqIDE should consider running it with the "asynchronous" and "error resilience" modes disabled:

你需要：
  - 当前版本的 Coq 安装，可以从 Coq 官方主页下载。“Coq 平台”通常提供最流畅的安装体验。
  - 如果你使用下面描述的 VSCode + Docker 选项，则不需要单独安装 Coq。
  - 用于与 Coq 交互的 IDE。有几个选择：
    - Visual Studio Code 的 VSCoq 扩展：通过一个熟悉的 IDE 提供了一个简单的界面。这个选项是推荐的默认选择。
    - VSCoq 可以作为普通 IDE 使用，或与 Docker 结合使用（见下文），以实现轻量级的安装体验。
    - Proof General 是一个基于 Emacs 的 IDE。通常被已经熟悉 Emacs 的用户所青睐。它需要单独安装（请搜索 "Proof General"）。
    - 喜欢在 Emacs 中使用 Coq 的高级用户可能想试试诸如 company-coq 和 control-lock 这样的扩展。
    - CoqIDE 是一个更简单的独立 IDE。它与 Coq 一起发布，因此一旦安装了 Coq，就应该可用。它也可以从头开始编译，但在某些平台上可能需要安装额外的 GUI 库等软件包。
    - 喜欢 CoqIDE 的用户可以考虑在禁用“异步”和“错误弹性”模式的情况下运行：

```
          coqide -async-proofs off \
          -async-proofs-command-error-resilience off Foo.v & ]] *)
```

#### Using Coq with VSCode and Docker

The Visual Studio Code IDE can cooperate with the Docker virtualization platform to compile Coq scripts without the need for any separate Coq installation. To get things set up, follow these steps:
  - Install Docker from https://www.docker.com/get-started/ or make sure your existing installation is up to date.
  - Make sure Docker is running.
  - Install VSCode from https://code.visualstudio.com and start it running.
  - Install VSCode's Remote Containers Extention from https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
  - Set up a directory for this SF volume by downloading the provided .tgz file. Besides the .v file for each chapter, this directory will contain a .devcontainer subdirectory with instructions for VSCode about where to find an appropriate Docker image and a _CoqProject file, whose presence triggers the VSCoq extension.
  - In VSCode, use File > Open Folder to open the new directory. VSCode should ask you whether you want to run the project in the associated Docker container. (If it does not ask you, you can open the command palette by pressing F1 and run the command “Dev Containers: Reopen in Container”.)
  - Check that VSCoq is working by double-clicking the file Basics.v from the list on the left (you should see a blinking cursor in the window that opens; if not you can click in that window to select it), and pressing alt+downarrow (on MacOS, control+option+downarrow) a few times. You should see the cursor move through the file and the region above the cursor get highlighted.
  - To see what other key bindings are available, press F1 and then type Coq:, or visit the VSCoq web pages: https://github.com/coq-community/vscoq/tree/vscoq1.

Visual Studio Code IDE 可以与 Docker 虚拟化平台协作，编译 Coq 脚本，而无需单独安装 Coq。要设置环境，请按照以下步骤操作：
  - 从 Docker 网站 安装 Docker，或确保现有安装是最新的。
  - 确保 Docker 正在运行。
  - 从 Visual Studio Code 网站 安装 VSCode，并启动。
  - 从 VSCode 扩展市场 安装 VSCode 的 Remote Containers 扩展。
  - 为本书的 SF 卷设置一个目录，方法是下载提供的 .tgz 文件。除了每个章节的 .v 文件外，这个目录还包含一个 .devcontainer 子目录，其中包含 VSCode 关于在何处查找适当 Docker 镜像的说明，以及一个 _CoqProject 文件，其存在触发 VSCoq 扩展。
  - 在 VSCode 中，使用“文件 > 打开文件夹”来打开新目录。VSCode 应该会询问你是否要在关联的 Docker 容器中运行该项目。（如果它没有询问，你可以按下 F1 打开命令面板，并运行命令“Dev Containers: Reopen in Container”）。
  - 通过双击左侧列表中的 Basics.v 文件来检查 VSCoq 是否正常工作（你应该看到在打开的窗口中有一个闪烁的光标；如果没有，你可以点击该窗口以选中它），然后多次按下 alt+下箭头（在 macOS 上，按 control+option+下箭头）。你应该看到光标在文件中移动，光标上方的区域被高亮显示。
  - 要查看其他可用的快捷键，请按 F1 然后输入 Coq:，或者访问 VSCoq 的网页：VSCoq GitHub。

#### Exercises 练习说明

Each chapter includes numerous exercises. Each is marked with a "star rating," which can be interpreted as follows:
  - One star: easy exercises that underscore points in the text and that, for most readers, should take only a minute or two. Get in the habit of working these as you reach them.
  - Two stars: straightforward exercises (five or ten minutes).
  - Three stars: exercises requiring a bit of thought (ten minutes to half an hour).
  - Four and five stars: more difficult exercises (half an hour and up).

每个章节包含大量练习。每个练习都标有“星级评分”，可以解释如下：
  - 一星：简单的练习，强调文本中的要点，对于大多数读者来说，只需一两分钟即可完成。养成在遇到它们时立即练习的习惯。
  - 二星：直接的练习（五到十分钟）。
  - 三星：需要一些思考的练习（十分钟到半小时）。
  - 四星和五星：更困难的练习（半小时及以上）。



Those using SF in a classroom setting should note that the autograder assigns extra points to harder exercises:
  - 1 star  = 1 point
  - 2 stars = 2 points
  - 3 stars = 3 points
  - 4 stars = 6 points
  - 5 stars = 10 points

那些在课堂环境中使用 SF 的用户应注意，自动评分程序会为难度较大的练习分配额外的分数：
  - 1 星 = 1 分
  - 2 星 = 2 分
  - 3 星 = 3 分
  - 4 星 = 6 分
  - 5 星 = 10 分

Some exercises are marked "advanced," and some are marked "optional." Doing just the non-optional, non-advanced exercises should provide good coverage of the core material. Optional exercises provide a bit of extra practice with key concepts and introduce secondary themes that may be of interest to some readers. Advanced exercises are for readers who want an extra challenge and a deeper cut at the material.

有些练习被标记为“高级”，有些被标记为“可选”。仅完成非可选、非高级的练习应该可以很好地覆盖核心材料。可选练习提供了对关键概念的额外练习，并介绍了一些可能对某些读者感兴趣的次要主题。高级练习适合那些想要额外挑战和更深入学习材料的读者。

**Please do not post solutions to the exercises in a public place**. Software Foundations is widely used both for self-study and for university courses. Having solutions easily available makes it much less useful for courses, which typically have graded homework assignments. We especially request that readers not post solutions to the exercises anyplace where they can be found by search engines.

**请不要在公共场所发布习题的解答**。《软件基础》广泛用于自学和大学课程。如果解答轻易可以获得，将大大降低其在课程中的价值，特别是那些有评分作业的课程。我们特别请求读者不要在可以被搜索引擎找到的地方发布习题解答。

#### Downloading the Coq Files 下载 Coq 文件

A tar file containing the full sources for the "release version" of this book (as a collection of Coq scripts and HTML files) is available at https://softwarefoundations.cis.upenn.edu.

包含本书“发布版本”完整源码的 tar 文件（作为 Coq 脚本和 HTML 文件的集合）可以在 Software Foundations 网站 获取。

If you are using the book as part of a class, your professor may give you access to a locally modified version of the files; you should use that one instead of the public release version, so that you get any local updates during the semester.

如果你正在课堂上使用这本书，你的教授可能会给你提供访问本地修改版本文件的权限；你应该使用该版本，而不是公开发布版本，以便在学期内获得本地更新。

#### Chapter Dependencies 章节依赖关系

A diagram of the dependencies between chapters and some suggested paths through the material can be found in the file deps.html.

章节之间依赖关系的图表以及一些材料的建议路径可以在 deps.html 文件中找到。

![deps](https://coq-zh.github.io/SF-zh/lf-current/deps.gif)

#### Recommended Citation Format 推荐引用格式

If you want to refer to this volume in your own writing, please do so as follows:

如果你想在自己的写作中引用本卷，请按以下格式进行：

```
    @book            {Pierce:SF1,
    author       =   {Benjamin C. Pierce and
                      Arthur Azevedo de Amorim and
                      Chris Casinghino and
                      Marco Gaboardi and
                      Michael Greenberg and
                      Cătălin Hriţcu and
                      Vilhelm Sjöberg and
                      Brent Yorgey},
    editor       =   {Benjamin C. Pierce},
    title        =   "Logical Foundations",
    series       =   "Software Foundations",
    volume       =   "1",
    year         =   "2023",
    publisher    =   "Electronic textbook",
    note         =   {Version 6.5, \URL{http://softwarefoundations.cis.upenn.edu}}
    }
```
### Resources 资源

#### Sample Exams 考试样本

A large compendium of exams from many offerings of CIS5000 ("Software Foundations") at the University of Pennsylvania can be found at https://www.seas.upenn.edu/~cis5000/current/exams/index.html. There has been some drift of notations over the years, but most of the problems are still relevant to the current text.

样本考试：可以在 University of Pennsylvania 网站找到许多 CIS5000 (“Software Foundations”) 课程的考试样本。

#### Lecture Videos 视频课程

Lectures for two intensive summer courses based on Logical Foundations (part of the DeepSpec summer school series) can be found at https://deepspec.org/event/dsss17and https://deepspec.org/event/dsss18/. The video quality in the 2017 lectures is poor at the beginning but gets better in the later lectures.

讲座视频：基于《逻辑基础》的两门密集型暑期课程的讲座可以在 DeepSpec Summer School 2017 和 DeepSpec Summer School 2018 找到。2017 年讲座的视频质量在开始时较差，但在后来的讲座中有所改善。

#### Note for Instructors and Contributors 对讲师和贡献者的说明

If you plan to use these materials in your own teaching, or if you are using software foundations for self study and are finding things you'd like to help add or improve, your contributions are welcome! You are warmly invited to join the private SF git repo.

如果你计划在自己的教学中使用这些材料，或者你在自学 Software Foundations 时发现了你想要添加或改进的内容，欢迎你贡献！我们热情邀请你加入 SF 的私人 Git 仓库。

In order to keep the legalities simple and to have a single point of responsibility in case the need should ever arise to adjust the license terms, sublicense, etc., we ask all contributors (i.e., everyone with access to the developers' repository) to assign copyright in their contributions to the appropriate "author of record," as follows:
   - I hereby assign copyright in my past and future contributions to the Software Foundations project to the Author of Record of each volume or component, to be licensed under the same terms as the rest of Software Foundations. I understand that, at present, the Authors of Record are as follows: For Volumes 1 and 2, known until 2016 as "Software Foundations" and from 2016 as (respectively) "Logical Foundations" and "Programming Foundations," and for Volume 4, "QuickChick: Property-Based Testing in Coq," the Author of Record is Benjamin C. Pierce. For Volume 3, "Verified Functional Algorithms," and volume 5, "Verifiable C," the Author of Record is Andrew W. Appel. For Volume 6, "Separation Logic Foundations," the author of record is Arthur Chargueraud. For components outside of designated volumes (e.g., typesetting and grading tools and other software infrastructure), the Author of Record is Benjamin Pierce.

为了使法律问题简单化，并在需要时调整许可证条款、再许可等情况下有一个单一的责任点，我们要求所有贡献者（即拥有开发者仓库访问权限的每个人）将其贡献的版权分配给相应的“记录作者”，并按照与 Software Foundations 其余部分相同的条款进行许可。我理解目前“记录作者”如下：
  - 对于卷 1 和卷 2，分别称为“Logical Foundations”和“Programming Foundations”：记录作者为 Benjamin C. Pierce。
  - 对于卷 3“Verified Functional Algorithms” 和卷 5“Verifiable C”：记录作者为 Andrew W. Appel。
  - 对于卷 4“QuickChick: Property-Based Testing in Coq” 和卷 6“Separation Logic Foundations”：记录作者为 Arthur Chargueraud。
  - 对于超出指定卷（例如排版和评分工具及其他软件基础设施）的组件：记录作者为 Benjamin Pierce。

To get started, please send an email to Benjamin Pierce, describing yourself and how you plan to use the materials and including (1) the above copyright transfer text and (2) your github username.

要开始，请发送电子邮件至 Benjamin Pierce，描述你自己以及你计划如何使用这些材料，并包括：1. 上述版权转让文本 2. 你的 GitHub 用户名。

We'll set you up with access to the git repository and developers' mailing lists. In the repository you'll find the files INSTRUCTORS and CONTRIBUTING with further instructions.

我们将为你设置访问 Git 仓库和开发者邮件列表的权限。在仓库中，你会找到 INSTRUCTORS 和 CONTRIBUTING 文件，里面有进一步的说明。

#### Translations 翻译

Thanks to the efforts of a team of volunteer translators, Software Foundations can be enjoyed in Japanese at http://proofcafe.org/sf. A Chinese translation is also underway; you can preview it at https://coq-zh.github.io/SF-zh/.

感谢志愿翻译团队的努力，Software Foundations 可以在 ProofCafe 网站上以日语阅读。中文翻译也正在进行中；你可以在 Coq 中文网站 预览。

#### Thanks 鸣谢
Development of the Software Foundations series has been supported, in part, by the National Science Foundation under the NSF Expeditions grant 1521523, The Science of Deep Specification.

《软件基础》系列的开发部分得到了国家科学基金会（National Science Foundation）NSF Expeditions 1521523 号项目“深度规范科学”的支持。

(* 2023-12-29 17:12 *)