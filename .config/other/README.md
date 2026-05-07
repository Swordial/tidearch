## horizon — project scope

`horizon` should be a from-source x86_64 UNIX-like distribution built around a deliberately minimal toolchain with a lot of flexibility and compatibility. every program should have a single purpose and do it well. It follows the `suckless` philosophy as well as the `UNIX` philosophy, meaning it should be lightweight/minimal and modular while continuing to allow compatibility with heavier, more robust applications (like proprietary drivers or maximum gaming compatibility) because of its modularity.

```
Suckless Philosophy
We are the home of quality software such as dwm, dmenu, st and plenty of other tools, with a focus on simplicity, clarity and frugality. Our philosophy is about keeping things simple, minimal and usable. We believe this should become the mainstream philosophy in the IT sector. Unfortunately, the tendency for complex, error-prone and slow software seems to be prevalent in the present-day software industry. We intend to prove the opposite with our software projects.

Our project focuses on advanced and experienced computer users. In contrast with the usual proprietary software world or many mainstream open source projects that focus more on average and non-technical end users, we think that experienced users are mostly ignored. This is particularly true for user interfaces, such as graphical environments on desktop computers, on mobile devices, and in so-called Web applications. We believe that the market of experienced users is growing continuously, with each user looking for more appropriate solutions for his/her work style.

Designing simple and elegant software is far more difficult than letting ad-hoc or over-ambitious features obscure the code over time. However one has to pay this price to achieve reliability and maintainability. Furthermore, minimalism results in reasonable and attainable goals. We strive to maintain minimalism and clarity to drive development to completion.

Manifest
Many (open source) hackers are proud if they achieve large amounts of code, because they believe the more lines of code they've written, the more progress they have made. The more progress they have made, the more skilled they are. This is simply a delusion.

Most hackers actually don't care much about code quality. Thus, if they get something working which seems to solve a problem, they stick with it. If this kind of software development is applied to the same source code throughout its entire life-cycle, we're left with large amounts of code, a totally screwed code structure, and a flawed system design. This is because of a lack of conceptual clarity and integrity in the development process.

Code complexity is the mother of bloated, hard to use, and totally inconsistent software. With complex code, problems are solved in suboptimal ways, valuable resources are endlessly tied up, performance slows to a halt, and vulnerabilities become a commonplace. The only solution is to scrap the entire project and rewrite it from scratch.

The bad news: quality rewrites rarely happen, because hackers are proud of large amounts of code. They think they understand the complexity in the code, thus there's no need to rewrite it. They think of themselves as masterminds, understanding what others can never hope to grasp. To these types, complex software is the ideal.

Ingenious ideas are simple. Ingenious software is simple. Simplicity is the heart of the Unix philosophy. The more code lines you have removed, the more progress you have made. As the number of lines of code in your software shrinks, the more skilled you have become and the less your software sucks.
```

```
Basics of the Unix Philosophy
The ‘Unix philosophy’ originated with Ken Thompson's early meditations on how to design a small but capable operating system with a clean service interface. It grew as the Unix culture learned things about how to get maximum leverage out of Thompson's design. It absorbed lessons from many sources along the way.

The Unix philosophy is not a formal design method. It wasn't handed down from the high fastnesses of theoretical computer science as a way to produce theoretically perfect software. Nor is it that perennial executive's mirage, some way to magically extract innovative but reliable software on too short a deadline from unmotivated, badly managed, and underpaid programmers.

The Unix philosophy (like successful folk traditions in other engineering disciplines) is bottom-up, not top-down. It is pragmatic and grounded in experience. It is not to be found in official methods and standards, but rather in the implicit half-reflexive knowledge, the expertise that the Unix culture transmits. It encourages a sense of proportion and skepticism — and shows both by having a sense of (often subversive) humor.

Doug McIlroy, the inventor of Unix pipes and one of the founders of the Unix tradition, had this to say at the time [McIlroy78]:

(i) Make each program do one thing well. To do a new job, build afresh rather than complicate old programs by adding new features.

(ii) Expect the output of every program to become the input to another, as yet unknown, program. Don't clutter output with extraneous information. Avoid stringently columnar or binary input formats. Don't insist on interactive input.

(iii) Design and build software, even operating systems, to be tried early, ideally within weeks. Don't hesitate to throw away the clumsy parts and rebuild them.

(iv) Use tools in preference to unskilled help to lighten a programming task, even if you have to detour to build the tools and expect to throw some of them out after you've finished using them.

He later summarized it this way (quoted in A Quarter Century of Unix [Salus]):

This is the Unix philosophy: Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface.

Rob Pike, who became one of the great masters of C, offers a slightly different angle in Notes on C Programming [Pike]:

Rule 1. You can't tell where a program is going to spend its time. Bottlenecks occur in surprising places, so don't try to second guess and put in a speed hack until you've proven that's where the bottleneck is.

Rule 2. Measure. Don't tune for speed until you've measured, and even then don't unless one part of the code overwhelms the rest.

Rule 3. Fancy algorithms are slow when n is small, and n is usually small. Fancy algorithms have big constants. Until you know that n is frequently going to be big, don't get fancy. (Even if n does get big, use Rule 2 first.)

Rule 4. Fancy algorithms are buggier than simple ones, and they're much harder to implement. Use simple algorithms as well as simple data structures.

Rule 5. Data dominates. If you've chosen the right data structures and organized things well, the algorithms will almost always be self-evident. Data structures, not algorithms, are central to programming.[9]

Rule 6. There is no Rule 6.

Ken Thompson, the man who designed and implemented the first Unix, reinforced Pike's rule 4 with a gnomic maxim worthy of a Zen patriarch:

When in doubt, use brute force.

More of the Unix philosophy was implied not by what these elders said but by what they did and the example Unix itself set. Looking at the whole, we can abstract the following ideas:

Rule of Modularity: Write simple parts connected by clean interfaces.

Rule of Clarity: Clarity is better than cleverness.

Rule of Composition: Design programs to be connected to other programs.

Rule of Separation: Separate policy from mechanism; separate interfaces from engines.

Rule of Simplicity: Design for simplicity; add complexity only where you must.

Rule of Parsimony: Write a big program only when it is clear by demonstration that nothing else will do.

Rule of Transparency: Design for visibility to make inspection and debuggingeasier.

Rule of Robustness: Robustness is the child of transparency and simplicity.

Rule of Representation: Fold knowledge into data so program logic can be stupid and robust.

Rule of Least Surprise: In interface design, always do the least surprising thing.

Rule of Silence: When a program has nothing surprising to say, it should say nothing.

Rule of Repair: When you must fail, fail noisily and as soon as possible.

Rule of Economy: Programmer time is expensive; conserve it in preference to machine time.

Rule of Generation: Avoid hand-hacking; write programs to write programs when you can.

Rule of Optimization: Prototype before polishing. Get it working before you optimize it.

Rule of Diversity: Distrust all claims for “one true way”.

Rule of Extensibility: Design for the future, because it will be here sooner than you think.

If you're new to Unix, these principles are worth some meditation. Software-engineering texts recommend most of them; but most other operating systems lack the right tools and traditions to turn them into practice, so most programmers can't apply them with any consistency. They come to accept blunt tools, bad designs, overwork, and bloated code as normal — and then wonder what Unix fans are so annoyed about.

Rule of Modularity: Write simple parts connected by clean interfaces.
As Brian Kernighan once observed, “Controlling complexity is the essence of computer programming” [Kernighan-Plauger]. Debugging dominates development time, and getting a working system out the door is usually less a result of brilliant design than it is of managing not to trip over your own feet too many times.

Assemblers, compilers, flowcharting, procedural programming, structured programming, “artificial intelligence”, fourth-generation languages, object orientation, and software-development methodologies without number have been touted and sold as a cure for this problem. All have failed as cures, if only because they ‘succeeded’ by escalating the normal level of program complexity to the point where (once again) human brains could barely cope. As Fred Brooks famously observed [Brooks], there is no silver bullet.

The only way to write complex software that won't fall on its face is to hold its global complexity down — to build it out of simple parts connected by well-defined interfaces, so that most problems are local and you can have some hope of upgrading a part without breaking the whole.

Rule of Clarity: Clarity is better than cleverness.
Because maintenance is so important and so expensive, write programs as if the most important communication they do is not to the computer that executes them but to the human beings who will read and maintain the source code in the future (includingyourself).

In the Unix tradition, the implications of this advice go beyond just commenting your code. Good Unix practice also embraces choosing your algorithms and implementations for future maintainability. Buying a small increase in performance with a large increase in the complexity and obscurity of your technique is a bad trade — not merely because complex code is more likely to harbor bugs, but also because complex code will be harder to read for future maintainers.

Code that is graceful and clear, on the other hand, is less likely to break — and more likely to be instantly comprehended by the next person to have to change it. This is important, especially when that next person might be yourself some years down the road.

Never struggle to decipher subtle code three times. Once might be a one-shot fluke, but if you find yourself having to figure it out a second time — because the first was too long ago and you've forgotten details — it is time to comment the code so that the third time will be relatively painless.

-- Henry Spencer	
Rule of Composition: Design programs to be connected with other programs.
It's hard to avoid programming overcomplicated monoliths if none of your programs can talk to each other.

Unix tradition strongly encourages writing programs that read and write simple, textual, stream-oriented, device-independent formats. Under classic Unix, as many programs as possible are written as simple filters, which take a simple text stream on input and process it into another simple text stream on output.

Despite popular mythology, this practice is favored not because Unix programmers hate graphical user interfaces. It's because if you don't write programs that accept and emit simple text streams, it's much more difficult to hook the programs together.

Text streams are to Unix tools as messages are to objects in an object-oriented setting. The simplicity of the text-stream interface enforces the encapsulation of the tools. More elaborate forms of inter-process communication, such as remote procedure calls, show a tendency to involve programs with each others' internals too much.

To make programs composable, make them independent. A program on one end of a text stream should care as little as possible about the program on the other end. It should be made easy to replace one end with a completely different implementation without disturbing the other.

GUIs can be a very good thing. Complex binary data formats are sometimes unavoidable by any reasonable means. But before writing a GUI, it's wise to ask if the tricky interactive parts of your program can be segregated into one piece and the workhorse algorithms into another, with a simple command stream or application protocol connecting the two. Before devising a tricky binary format to pass data around, it's worth experimenting to see if you can make a simple textual format work and accept a little parsing overhead in return for being able to hack the data stream with general-purpose tools.

When a serialized, protocol-like interface is not natural for the application, proper Unix design is to at least organize as many of the application primitives as possible into a library with a well-defined API. This opens up the possibility that the application can be called by linkage, or that multiple interfaces can be glued on it for differenttasks.

(We discuss these issues in detail in Chapter7.)

Rule of Separation: Separate policy from mechanism; separate interfaces from engines.
In our discussion of what Unix gets wrong, we observed that the designers of X made a basic decision to implement “mechanism, not policy”—to make X a generic graphics engine and leave decisions about user-interface style to toolkits and other levels of the system. We justified this by pointing out that policy and mechanism tend to mutate on different timescales, with policy changing much faster than mechanism. Fashions in the look and feel of GUI toolkits may come and go, but raster operations and compositing are forever.

Thus, hardwiring policy and mechanism together has two bad effects: It makes policy rigid and harder to change in response to user requirements, and it means that trying to change policy has a strong tendency to destabilize the mechanisms.

On the other hand, by separating the two we make it possible to experiment with new policy without breaking mechanisms. We also make it much easier to write good tests for the mechanism (policy, because it ages so quickly, often does not justify the investment).

This design rule has wide application outside the GUI context. In general, it implies that we should look for ways to separate interfaces from engines.

One way to effect that separation is, for example, to write your application as a library of C service routines that are driven by an embedded scripting language, with the application flow of control written in the scripting language rather thanC. Aclassic example of this pattern is the Emacs editor, which uses an embedded Lisp interpreter to control editing primitives written in C. We discuss this style of design in Chapter11.

Another way is to separate your application into cooperating front-end and back-end processes communicating through a specialized application protocol over sockets; we discuss this kind of design in Chapter5 and Chapter7. The front end implements policy; the back end, mechanism. The global complexity of the pair will often be far lower than that of a single-process monolith implementing the same functions, reducing your vulnerability to bugs and lowering life-cycle costs.

Rule of Simplicity: Design for simplicity; add complexity only where you must.
Many pressures tend to make programs more complicated (and therefore more expensive and buggy). One such pressure is technical machismo. Programmers are bright people who are (often justly) proud of their ability to handle complexity and juggle abstractions. Often they compete with their peers to see who can build the most intricate and beautiful complexities. Just as often, their ability to design outstrips their ability to implement and debug, and the result is expensive failure.

The notion of “intricate and beautiful complexities” is almost an oxymoron. Unix programmers vie with each other for “simple and beautiful” honors — apoint that's implicit in these rules, but is well worth making overt.

-- Doug McIlroy	
Even more often (at least in the commercial software world) excessive complexity comes from project requirements that are based on the marketing fad of the month rather than the reality of what customers want or software can actually deliver. Many a good design has been smothered under marketing's pile of “checklist features” — features that, often, no customer will ever use. And a vicious circle operates; the competition thinks it has to compete with chrome by adding more chrome. Pretty soon, massive bloat is the industry standard and everyone is using huge, buggy programs not even their developers can love.

Either way, everybody loses in the end.

The only way to avoid these traps is to encourage a software culture that knows that small is beautiful, that actively resists bloat and complexity: an engineering tradition that puts a high value on simple solutions, that looks for ways to break program systems up into small cooperating pieces, and that reflexively fights attempts to gussy up programs with a lot of chrome (or, even worse, to design programs around the chrome).

That would be a culture a lot like Unix's.

Rule of Parsimony: Write a big program only when it is clear by demonstration that nothing else will do.
‘Big’ here has the sense both of large in volume of code and of internal complexity. Allowing programs to get large hurts maintainability. Because people are reluctant to throw away the visible product of lots of work, large programs invite overinvestment in approaches that are failed or suboptimal.

(We'll examine the issue of the right size of software in more detail in Chapter13.)

Rule of Transparency: Design for visibility to make inspection and debugging easier.
Because debugging often occupies three-quarters or more of development time, work done early to ease debugging can be a very good investment. A particularly effective way to ease debugging is to design for transparency and discoverability.

A software system is transparent when you can look at it and immediately understand what it is doing and how. It is discoverable when it has facilities for monitoring and display of internal state so that your program not only functions well but can be seen to function well.

Designing for these qualities will have implications throughout a project. At minimum, it implies that debugging options should not be minimal afterthoughts. Rather, they should be designed in from the beginning — from the point of view that the program should be able to both demonstrate its own correctness and communicate to future developers the original developer's mental model of the problem it solves.

For a program to demonstrate its own correctness, it needs to be using input and output formats sufficiently simple so that the proper relationship between valid input and correct output is easy to check.

The objective of designing for transparency and discoverability should also encourage simple interfaces that can easily be manipulated by other programs — in particular, test and monitoring harnesses and debugging scripts.

Rule of Robustness: Robustness is the child oftransparency and simplicity.
Software is said to be robust when it performs well under unexpected conditions which stress the designer's assumptions, as well as under normal conditions.

Most software is fragile and buggy because most programs are too complicated for a human brain to understand all at once. When you can't reason correctly about the guts of a program, you can't be sure it's correct, and you can't fix it if it's broken.

It follows that the way to make robust programs is to make their internals easy for human beings to reason about. There are two main ways to do that: transparency and simplicity.

For robustness, designing in tolerance for unusual or extremely bulky inputs is also important. Bearing in mind the Rule of Composition helps; input generated by other programs is notorious for stress-testing software (e.g.,the original Unix C compiler reportedly needed small upgrades to cope well with Yacc output). The forms involved often seem useless to humans. For example, accepting empty lists/strings/etc., even in places where a human would seldom or never supply an empty string, avoids having to special-case such situations when generating the input mechanically.

-- Henry Spencer	
One very important tactic for being robust under odd inputs is to avoid having special cases in your code. Bugs often lurk in the code for handling special cases, and in the interactions among parts of the code intended to handle different special cases.

We observed above that software is transparent when you can look at it and immediately see what is going on. It is simple when what is going on is uncomplicated enough for a human brain to reason about all the potential cases without strain. The more your programs have both of these qualities, the more robust they will be.

Modularity (simple parts, clean interfaces) is a way to organize programs to make them simpler. There are other ways to fight for simplicity. Here's another one.

Rule of Representation: Fold knowledge into data, soprogram logic can be stupid and robust.
Even the simplest procedural logic is hard for humans to verify, but quite complex data structures are fairly easy to model and reason about. To see this, compare the expressiveness and explanatory power of a diagram of (say) a fifty-node pointer tree with a flowchart of a fifty-line program. Or, compare an array initializer expressing a conversion table with an equivalent switch statement. The difference in transparency and clarity is dramatic. See Rob Pike's Rule 5.

Data is more tractable than program logic. It follows that where you see a choice between complexity in data structures and complexity in code, choose the former. More: in evolving a design, you should actively seek ways to shift complexity from code to data.

The Unix community did not originate this insight, but a lot of Unix code displays its influence. The C language's facility at manipulating pointers, in particular, has encouraged the use of dynamically-modified reference structures at all levels of coding from the kernel upward. Simple pointer chases in such structures frequently do duties that implementations in other languages would instead have to embody in more elaborate procedures.

(We also cover these techniques in Chapter9.)

Rule of Least Surprise: In interface design, always do theleast surprising thing.
(This is also widely known as the Principle of Least Astonishment.)

The easiest programs to use are those that demand the least new learning from the user — or, to put it another way, the easiest programs to use are those that most effectively connect to the user's pre-existing knowledge.

Therefore, avoid gratuitous novelty and excessive cleverness in interface design. If you're writing a calculator program, ‘+’ should always mean addition! When designing an interface, model it on the interfaces of functionally similar or analogous programs with which your users are likely to be familiar.

Pay attention to your expected audience. They may be end users, they may be other programmers, or they may be system administrators. What is least surprising can differ among these groups.

Pay attention to tradition. The Unix world has rather well-developed conventions about things like the format of configuration and run-control files, command-line switches, and the like. These traditions exist for a good reason: to tame the learning curve. Learn and use them.

(We'll cover many of these traditions in Chapter5 and Chapter10.)

The flip side of the Rule of Least Surprise is to avoid making things superficially similar but really a little bit different. This is extremely treacherous because the seeming familiarity raises false expectations. It's often better to make things distinctly different than to make them almost the same.

-- Henry Spencer	
Rule of Silence: When a program has nothing surprising to say, it should say nothing.
One of Unix's oldest and most persistent design rules is that when a program has nothing interesting or surprising to say, it should shut up. Well-behaved Unix programs do their jobs unobtrusively, with a minimum of fuss and bother. Silence is golden.

This “silence is golden” rule evolved originally because Unix predates video displays. On the slow printing terminals of 1969, each line of unnecessary output was a serious drain on the user's time. That constraint is gone, but excellent reasons for terseness remain.

I think that the terseness of Unix programs is a central feature of the style. When your program's output becomes another's input, it should be easy to pick out the needed bits. And for people it is a human-factors necessity — important information should not be mixed in with verbosity about internal program behavior. If all displayed information is important, important information is easy to find.

-- Ken Arnold	
Well-designed programs treat the user's attention and concentration as a precious and limited resource, only to be claimed when necessary.

(We'll discuss the Rule of Silence and the reasons for it in more detail at the end of Chapter11.)

Rule of Repair: Repair what you can — but when you must fail, fail noisily and as soon as possible.
Software should be transparent in the way that it fails, as well as in normal operation. It's best when software can cope with unexpected conditions by adapting to them, but the worst kinds of bugs are those in which the repair doesn't succeed and the problem quietly causes corruption that doesn't show up until much later.

Therefore, write your software to cope with incorrect inputs and its own execution errors as gracefully as possible. But when it cannot, make it fail in a way that makes diagnosis of the problem as easy as possible.

Consider also Postel's Prescription:[10] “Be liberal in what you accept, and conservative in what you send”. Postel was speaking of network service programs, but the underlying idea is more general. Well-designed programs cooperate with other programs by making as much sense as they can from ill-formed inputs; they either fail noisily or pass strictly clean and correct data to the next program in the chain.

However, heed also this warning:

The original HTML documents recommended “be generous in what you accept”, and it has bedeviled us ever since because each browser accepts a different superset of the specifications. It is the specifications that should be generous, not their interpretation.

-- Doug McIlroy	
McIlroy adjures us to design for generosity rather than compensating for inadequate standards with permissive implementations. Otherwise, as he rightly points out, it's all too easy to end up in tag soup.

Rule of Economy: Programmer time is expensive; conserve it in preference to machine time.
In the early minicomputer days of Unix, this was still a fairly radical idea (machines were a great deal slower and more expensive then). Nowadays, with every development shop and most users (apart from the few modeling nuclear explosions or doing 3D movie animation) awash in cheap machine cycles, it may seem too obvious to need saying.

Somehow, though, practice doesn't seem to have quite caught up with reality. If we took this maxim really seriously throughout software development, most applications would be written in higher-level languages like Perl, Tcl, Python, Java, Lisp and even shell — languages that ease the programmer's burden by doing their own memory management (see [Ravenbrook]).

And indeed this is happening within the Unix world, though outside it most applications shops still seem stuck with the old-school Unix strategy of coding in C (orC++). Later in this book we'll discuss this strategy and its tradeoffs in detail.

One other obvious way to conserve programmer time is to teach machines how to do more of the low-level work of programming. This leads to...

Rule of Generation: Avoid hand-hacking; write programs to write programs when you can.
Human beings are notoriously bad at sweating the details. Accordingly, any kind of hand-hacking of programs is a rich source of delays and errors. The simpler and more abstracted your program specification can be, the more likely it is that the human designer will have gotten it right. Generated code (at every level) is almost always cheaper and more reliable than hand-hacked.

We all know this is true (it's why we have compilers and interpreters, after all) but we often don't think about the implications. High-level-language code that's repetitive and mind-numbing for humans to write is just as productive a target for a code generator as machine code. It pays to use code generators when they can raise the level of abstraction — that is, when the specification language for the generator is simpler than the generated code, and the code doesn't have to be hand-hacked afterwards.

In the Unix tradition, code generators are heavily used to automate error-prone detail work. Parser/lexer generators are the classic examples; makefile generators and GUI interface builders are newer ones.

(We cover these techniques in Chapter9.)

Rule of Optimization: Prototype before polishing. Get it working before you optimize it.
The most basic argument for prototyping first is Kernighan & Plauger's; “90% of the functionality delivered now is better than 100% of it delivered never”. Prototyping first may help keep you from investing far too much time for marginal gains.

For slightly different reasons, Donald Knuth (author of The Art Of Computer Programming, one of the field's few true classics) popularized the observation that “Premature optimization is the root of all evil”.[11] And he was right.

Rushing to optimize before the bottlenecks are known may be the only error to have ruined more designs than feature creep. From tortured code to incomprehensible data layouts, the results of obsessing about speed or memory or disk usage at the expense of transparency and simplicity are everywhere. They spawn innumerable bugs and cost millions of man-hours — often, just to get marginal gains in the use of some resource much less expensive than debugging time.

Disturbingly often, premature local optimization actually hinders global optimization (and hence reduces overall performance). A prematurely optimized portion of adesign frequently interferes with changes that would have much higher payoffs across the whole design, so you end up with both inferior performance and excessively complex code.

In the Unix world there is a long-established and very explicit tradition (exemplified by Rob Pike's comments above and Ken Thompson's maxim about brute force) that says: Prototype, then polish. Get it working before you optimize it. Or: Make it work first, then make it work fast. ‘Extreme programming' guru Kent Beck, operating in a different culture, has usefully amplified this to: “Make it run, then make it right, then make it fast”.

The thrust of all these quotes is the same: get your design right with an un-optimized, slow, memory-intensive implementation before you try to tune. Then, tune systematically, looking for the places where you can buy big performance wins with the smallest possible increases in local complexity.

Prototyping is important for system design as well as optimization — it is much easier to judge whether a prototype does what you want than it is to read a long specification. I remember one development manager at Bellcore who fought against the “requirements” culture years before anybody talked about “rapid prototyping” or “agile development”. He wouldn't issue long specifications; he'd lash together some combination of shell scripts and awk code that did roughly what was needed, tell the customers to send him some clerks for a few days, and then have the customers come in and look at their clerks using the prototype and tell him whether or not they liked it. If they did, he would say “you can have it industrial strength so-many-months from now at such-and-such cost”. His estimates tended to be accurate, but he lost out in the culture to managers who believed that requirements writers should be in control of everything.

-- Mike Lesk	
Using prototyping to learn which features you don't have to implement helps optimization for performance; you don't have to optimize what you don't write. The most powerful optimization tool in existence may be the delete key.

One of my most productive days was throwing away 1000 lines of code.

-- Ken Thompson	
(We'll go into a bit more depth about related ideas in Chapter12.)

Rule of Diversity: Distrust all claims for “one true way”.
Even the best software tools tend to be limited by the imaginations of their designers. Nobody is smart enough to optimize for everything, nor to anticipate all the uses to which their software might be put. Designing rigid, closed software that won't talk to the rest of the world is an unhealthy form of arrogance.

Therefore, the Unix tradition includes a healthy mistrust of “one true way” approaches to software design or implementation. It embraces multiple languages, open extensible systems, and customization hooks everywhere.

Rule of Extensibility: Design for the future, because it will be here sooner than you think.
If it is unwise to trust other people's claims for “one true way”, it's even more foolish to believe them about your own designs. Never assume you have the final answer. Therefore, leave room for your data formats and code to grow; otherwise, you will often find that you are locked into unwise early choices because you cannot change them while maintaining backward compatibility.

When you design protocols or file formats, make them sufficiently self-describing to be extensible. Always, always either include a version number, or compose the format from self-contained, self-describing clauses in such a way that new clauses can be readily added and old ones dropped without confusing format-reading code. Unix experience tells us that the marginal extra overhead of making data layouts self-describing is paid back a thousandfold by the ability to evolve them forward without breaking things.

When you design code, organize it so future developers will be able to plug new functions into the architecture without having to scrap and rebuild the architecture. This rule is not a license to add features you don't yet need; it's advice to write your code so that adding features later when you do need them is easy. Make the joints flexible, and put “If you ever need to...” comments in your code. You owe this grace to people who will use and maintain your code after you.

You'll be there in the future too, maintaining code you may have half forgotten under the press of more recent projects. When you design for the future, the sanity you save may be your own.


[9] Pike's original adds “(See Brooks p. 102.)” here. The reference is to an early edition of The Mythical Man-Month [Brooks]; the quote is “Show me your flow charts and conceal your tables and I shall continue to be mystified, show me your tables and I won't usually need your flow charts; they'll be obvious”.

[10] Jonathan Postel was the first editor of the Internet RFC series of standards, and one of the principal architects of the Internet. A tribute page is maintained by the Postel Center for Experimental Networking.

[11] In full: “We should forget about small efficiencies, say about 97% of the time: premature optimization is the root of all evil”. Knuth himself attributes the remark to C.A.R.Hoare.
```

in line with these philosophies, the most minimal alternatives to software should be used whenever possible. Some examples:

```
Stuff that rocks
Software on this page should have ideas similar to the suckless philosophy. The software must be FOSS licensed.

Libraries
This section is for small, usable development libraries, which can be used for writing software that sucks less. These should preferably be under the MIT/X consortium or BSD licenses, WTFPL, or public domain, or alternatively LGPL, because it makes them legally compatible with other suckless projects.

Libc Implementations
musl - standard C library that attempts to be even smaller than uClibc. See also: embedded libc comparison
uClibc - strives to be a minimalist C library suitable for embedded computing.

Compilers
cproc - frontend for C11 for QBE.
lacc - A simple, self-hosting C compiler.
qbe - compiler backend targeting AMD64 (Linux and OSX), ARM64, and RISC-V64.
scc - Simple C Compiler.
tcc - Tiny C Compiler git repo

Compression
liblzf - very fast, legally unencumbered compression library.
libz - ABI and API compatible zlib fork with focus on correctness, proper portability, auditability, simplification and opportunities to optimize (zlib license).
Lzip - Properly designed data compressor outperforming gzip and bzip2 (GPLv2+).
miniz - single C-file reimplementation of zlib (MIT License).
xz embedded - lightweight decompressor for the xz LZMA compressor (public domain).
zlib - the "standard" compression/decompression library, quite small, used in many applications (zlib license).

GUI
Nuklear - A single-header ANSI C immediate mode cross-platform GUI library.
Cryptography
LibreSSL - LibreSSL is a version of the TLS/crypto stack forked from OpenSSL in 2014.
Monocypher - Small and freestanding cryptographic library with relatively good performance written in C99.

Miscellaneous
baresip - barebone SIP stack (BSD licence).
ccv - C-based/Cached/Core Computer Vision Library, A Modern Computer Vision Library.
libev - high performance event-loop modelled after libevent but much smaller (dual licensed under 2-clause BSD and GPL).
mandoc - The mandoc UNIX manpage compiler toolset.
nhkd - nano hot key daemon.
pjsip - open-source SIP stack (GPL).
raycastlib - Single-header public domain C raycasting renderer with no dependencies, using only integer math.
sdhcp - IPv4 DHCP client.
small3dlib - Single-header public domain C software 3D renderer with no dependencies, using only integer math.
stb - single-file public domain (or MIT licensed) libraries for C/C++: various image, font, audio loaders etc.
sxhkd - Simple X hotkey daemon
termbox - simple ncurses-like library for creating TUIs.
TinyGL - free software-only subset of OpenGL 1.1 implemented in C

Distros
morpheus - A statically linked musl-based Linux distro. Unmaintained currently.
oasis - A small statically linked Linux system.
sxmo: simple X Mobile, Sxmo is a minimalist environment for Linux mobile devices, such as the pinephone.

Programs
Some programs work well with dwm. Some general rule of thumb for judging if a program is usable are:
The program will accept any window size.
The program consists of a single window (there are no nested windows, such as in Xpdf).
This covers most console-based programs and programs from plan9port.

Audio Players
C* Music Player - aka cmus, an ncurses music player that can be controlled with a UNIX socket.
moc - console audio player for Linux/UNIX.
mpd - A client/server based music player with console and graphical front-ends.
mpg123 - A console MPG player which doesn't use auto*hell or extra libraries.
mpg321 - A command-line MP3 player.
mus - Modular daemon/client CLI player consuming a plaintext album directory queue
vorbis-tools (Ogg/FLAC) - Command-line tools to play Ogg and FLAC files.

BitTorrent clients
btpd - The BitTorrent Protocol Daemon.
Feed aggregators / newsreaders
newsraft - feed reader with ncurses user interface.
sfeed - RSS and Atom parser, CLI programs and sfeed_curses UI.
snownews - Text mode RSS newsreader for Linux and Unix.
zs - Zeitungsschau RSS to email converter.

File managers
lf - ranger-like file manager written in Go.
mc - Midnight Commander is a free cross-platform orthodox file manager.
nnn - Nnn's Not Noice, a fork of noice with more features.
noice - Small and portable file browser.
ranger - ranger is a file manager with vi key bindings written in python but with an interface that rocks.
rover - Simple file browser for the terminal.
sff - Simple and fast terminal file manager inspired by nnn.
sfm - sfm is a simple file manager for unix-like systems.

Git
stagit - static git page generator (HTML).
stagit-gopher - static git page generator for gopher (geomyidae .gph pages).
stagit-gemini - static git page generator for gemini (gemtext .gmi pages).

Gopher clients
Lynx - text-mode web browser, supports the Gopher protocol.
sacc - terminal gopher client by quinq.

IRC clients
catgirl - is a TLS-only terminal IRC client.
hii - A file-based IRC client, inspired by ii, with a focus on easing frontend development
ii - A FIFO based IRC client which is part of the suckless.org project.
irc.c from mpu - A minimal curses IRC client.
Irc - IRC client for ACME.
ircrc - An rc-based IRC client similar to ircc. Needs minor modification to run on UNIX.
irssi - Text-mode IRC client.
jj - A rework of ii that offloads all the IRC protocol parsing to an awk script, permitting triggers.
kirc - A tiny IRC client written in POSIX C99.
quIRC - a lightweight console IRC client.
sic - Another suckless.org IRC client. Similar to ircc.

Image viewers
feh - A highly customizable image viewer that can also set a desktop background image.
imv - Simple X11/Wayland Image Viewer. Depends on SDL2 and FreeImage.
jpg/gif/bmp/png - Simple programs from Plan 9 to display images in no-frills windows. Included with plan9port.
lel - Farbfeld image viewer.
meh - image viewer using raw XLib, libjpeg, libpng and libgif.
page - Plan 9's image/document viewer program. Included with plan9port.
qiv - Quick Image Viewer.
nsxiv - Neo Simple X Image Viewer, a fork of now unmaintained sxiv. Depends on xlib and imlib2.
xwallpaper - Minimalistic wallpaper utility
xzgv - image viewer

Instant-Messaging clients
bitlbee - A program to translate IM protocols to IRC.
CenterIM - A centericq fork.
irssi-xmpp - An irssi plugin to connect to the Jabber network.
mcabber - A console jabber client.
profanity - A console XMPP client written in C. OMEMO/GPG/OTR supported.
ysm - A console-based ICQ client.

Mail clients
aerc - email client for your terminal.
fdm - fetch and deliver mail.
heirloom-mailx - A mail client based on the original Berkeley Mail 8.1 with many new features.
isync - MDA that can work better for IMAP, also known as mbsync.
mblaze - UNIX utilities to deal with Maildir.
mmh - Meillo's mail handler (mmh), a fork of nmh.
mpop - a POP3 mail client. It is much faster and simpler than fetchmail.
mutt - A ncurses mail client for fetching, reading and sending email.
nmh - Message Handling System.
plan9port/Mail - A mail client for acme. Included with plan9port.
s-nail - An improved heirloom-mailx.

Media players
ffplay - FFplay is a very simple and portable media player. It came with ffmpeg which mplayer depends on.
mplayer
mpv - a free, open-source and cross-platform media player.

Notifications
herbe - Daemon-less notifications without D-Bus. Minimal, lightweight & written in C. You can use tiramisu to call herbe.
tiramisu - Tiramisu is a notification daemon based on dunst that outputs notifications to STDOUT in order to allow the user to process notifications any way they prefer, like in your dwm statusbar for example.

Password managers
oathtool - Open AuTHentication (OATH) one-time password tool.
pinentry-dmenu - pinentry-dmenu is a pinentry program with the charm of dmenu. It is a nice interface to pass
pass - "The standard UNIX password manager".
spm - Simple password manager (actively maintained fork of nmeum's tpm).
tpm - Tiny password manager.

PDF viewers
mupdf - a lightweight PDF viewer written in C. It supports PDF, XPS, EPUB, XHTML, CBZ, PNG, JPEG, GIF and TIFF.
zathura - an extensible document viewer/shell which can support CBZ, DJVU, PS, EPUB (with mupdf) and PDF (with mupdf or poppler).
d
Shells
dash - DASH is a POSIX-compliant implementation of /bin/sh that aims to be as small as possible.
mksh - MirBSD Korn Shell, an actively developed free implementation of the Korn Shell programming language and a successor to the Public Domain Korn Shell (pdksh).
oksh - Portable OpenBSD ksh.
yash - Yet another shell, is intended to be the most POSIX-compliant shell in the world while supporting features for daily interactive and scripting use.

Text editors
acme - Rob Pike's framing text editor for Plan 9. Included in plan9port.
ed - ED IS THE STANDARD TEXT EDITOR!
ired - A minimalist hexadecimal editor and bindiffer for p9, w32 and *nix.
mg - A portable version of mg.
mle - A small, flexible console text editor.
nano - A pico clone - this is small simple code and easy to use.
neatvi - A minimal vi implementation supporting bidirectional UTF-8
nextvi - A continuation of neatvi development with more features.
nvi - A small, multiple file vi-alike.
micro - A terminal text editor, written in go with common key bindings like ctrl-c to copy and ctrl-v to paste.
sam - An editor by Rob Pike with inspiration from ed.
sim - The sim text editor. Based on vim and sam.
traditional vi - A fixed version of the original vi.
vim (With the GUI, use :set go+=c to kill popup dialogs). It can be compiled to be as minimal as possible (see vim-tiny in Debian repos).
vis - A modern, legacy free, simple yet efficient vim-like editor.
wily - An acme clone for POSIX.

Text processing
csvquote - tool to encode troublesome CSV characters such that unix tools can correctly process them. SIMD optimized by default, portable C fallback can be enabled at build time.
json2tsv - a JSON to TAB-Separated Value (TSV) converter and stand-alone JSON parser code.
md4c - markdown to html converter. Fast, CommonMark compliant, offers extensions which can be switched on/off via cli args.
wak - A small, POSIX compliant awk implementation.

Utilities / miscellaneous
abduco - session {at,de}tach support.
dvtm - dynamic virtual terminal manager.
entr - Run arbitrary commands when files change.
mrandr - Simple and lightweight monitor (display) profile manager written in POSIX shell.
mtm - Micro Terminal Multiplexer.
nq - UNIX command line queue utility.
piscou - Simple file previewer written in C.
soap - Simple xdg-open replacement with fallback.
pv - tool for monitoring the progress of data through a pipeline.
smenu - A powerful and versatile CLI selection tool for interactive or scripting use.
snore - Sleep with feedback.
yt-dlp - youtube-dl fork, download videos from youtube.com or other video platforms.
zbar - software suite for reading bar codes from various sources, such as video streams, image files.

Web browsers
Abaco - A graphical web browser for Plan 9 that supports most of HTML 4.01.
Dillo - Blazingly fast graphical browser with basic CSS support.
edbrowse - ed-alike webbrowser. Unfortunately it is not the standard web browser.
ELinks - Feature-rich fork of Links, but without the graphical mode.
Links - A text-based browser that also has a simple graphical mode.
Lynx - text-mode web browser, supports the Gopher protocol.
netsurf - Very fast graphical browser with custom engine that has near-perfect CSS support.
surf - WebKit2 browser that can be embedded into other applications and uses dmenu as the address bar.
Tridactyl - A WebExtension that tries to make Firefox Vim like. Unlike many similar extensions it works with firefox 57+.
uzbl - Web interface tools which adhere to the UNIX philosophy.
Vimperator - An extension to make Firefox keyboard friendly and Vim-like. (Doesn't work with Firefox 57+).
w3m - Text-based browser which can view images in the terminal (X11 hack).

X11
9menu - A menu program based on the Blit-style menus so prevalent in Plan 9.
dmenu - dmenu is a dynamic menu for X.
ffcast - Simple screencasting.
grabc - Grab the color of some pixel in X11.
keynav - A new way for keyboard selection.
wjt - A slider widget for X.
wmutils - A set of utilities for managing windows. Can be used on their own or to augment a WM itself. Support for tiling present.
xbanish - Hide the cursor while typing.
xhidecursor - xbanish but simpler.
xclip - A tool for controlling the X11 clipboard.
xdotool - A tool for scripting X11 actions.
xdo - Similar to xdotool but it's smaller and has a much cleaner codebase.
xzoom - A simple zoom application.

Daemons
This section is dedicated to daemons that are related to the UNIX philosophy.

Web Servers
darkhttpd - Darkhttpd is a simple, fast HTTP 1.1 web server for static content.
merecat - thttpd with vhost support.
mini_httpd - By the thttpd developers. Even smaller subset of thttpd with support for .htpasswd, CGI, dirlisting, HTTP errors and SSL, nothing more or less than that.
OpenBSD httpd - OpenBSD HTTP daemon. Concise configuration, sane defaults, secure.
quark - suckless simple static web server.
thttpd - Outperforms many bigger httpds. Old, still works very well!

Gopher servers
geomyidae - small gopher-daemon written by 20h.

Misc daemons
scron - simple crond.
```

also, there is https://github.com/mayfrost/guides/blob/master/ALTERNATIVES.md for even more alternatives that may be smaller. the further to the right you go on each line on this document, the more minimal the packages become. For example, PuTTY -> Cool Retro Term -> Terminology -> rxvt-unicode (a.k.a. urxvt) -> Termite -> UXTerm (XTerm) -> st -> Qodem. Qodem would be the most minimal, followed by st, UXTerm, etc. there is also software you should avoid:

```
Stuff that sucks
See the philosophy about what applies to this page.

Bigger topics that suck: systemd, the web

Libraries
These libraries are broken/considered harmful and should not be used if it's possible to avoid them. If you use them, consider looking for alternatives.

glib - implements C++ STL on top of C (because C++ sucks so much, let's reinvent it!), adding lots of useless data types for "portability" and "readability" reasons. even worse, it is not possible to write robust applications using glib, since it aborts in out-of-memory situations. glib usage is required to write gtk+ and gnome applications, but is also used when common functionality is needed (e.g. hashlists, base64 decoder, etc). it is not suited at all for static linking due to its huge size and the authors explicitly state that "static linking is not supported".

Alternatives: libmowgli, libulz, BSD queue.h/tree.h macros.

GMP - GNU's bignum/arbitrary precision library. Quite bloated, slow and calls abort() on failed malloc

Alternatives: libtommath, TomsFastMath, imath, libzahl (WIP), hebimath (WIP)

Build Systems
cmake (written in C++) - so huge and bloated, compilation takes longer than compiling GCC (!). It's not even possible to create freestanding Makefiles, since the generated Makefiles call back into the cmake binary itself. Usage of cmake requires learning a new custom scripting language with very limited expressiveness. Its major selling point is the existence of a clicky-click GUI for windows users.
waf and scons (both written in Python) - waf code is dropped into the compilee's build tree, so it does not benefit from updated versions and bugfixes.
As these build systems are often used to compile C programs, one has to set up a C++ compiler or Python interpreter respectively just in order to be able to build some C code.

Alternatives: make, mk

Version Control Systems

subversion - Teaches developers to think of version control in a harmful and terrible way, centralized, ugly code, conceptionally broken in a lot of terms. "Centralized" is said to be one of the main benefits for "enterprise" applications, however, there is no benefit at all compared to decentralized version control systems like git. There is no copy-on-write, branching essentially will create a 1:1 copy of the full tree you have under version control, making feature-branches and temporary changes to your code a painful mess. It is slow, encourages people to come up with weird workarounds just to get their work done, and the only thing enterprisey about it is that it just sucks.
Programs
There are many broken X programs. Go bug the developers of these broken programs to fix them. Here are some of the main causes of this brokenness:

The program assumes a specific window management model, e.g. assumes you are using a WIMP-window manager like those found in KDE or Gnome. This assumption breaks the ICCCM conventions.
The application uses a fixed size - this limitation does not fit into the world of tiling window managers very well, and can also be seen as breaking the ICCCM conventions, because a fixed sized window assumes a specific window management model as well (though the ICCCM does not forbid fixed-size windows). In any case, the ICCCM requests that clients accept any size the window manager proposes to them.
The program is based on strange non-standard window manager hints that only work properly with a window manager supporting these extensions - this simply breaks the ICCCM as well. E.g. trash icon programs.
The program does not conform to ICCCM due to some missing or improperly set hints.
If you still need some program which expects a floating WM, use it in floating mode.

Documentation
Somewhen GNU tried to make the world a bit more miserable by inventing texinfo. The result is that in 2019 man pages are still used and the documentation of GNU tools requires you to run info $application. The info browser is awkward and unintuitive and the reason why no one gets further than finding 'q' to quit it.

Look at GNU tools how to not handle documentation.

Talking about the suck in enforced HTML documentation, which forces you to open up a 1 Gb of RAM wasting web browser, just to see some eye-candy, which could have been described in the source with some easy way to jump to that line in the source code, is not worth the time.

The suckless way is to have a short usage and a descriptive manpage. The complete details are in the source.

Alternatives: roff, mdoc.

C Compilers
GCC: as of 2016 it is now written in C++ and so complete suck. Why can't a compiler just be a simple binary doing its work instead of adding path dependencies deep into the system?
Clang is written in C++. If you don't believe that it sucks, try to build clang by hand.
```

additional packages to avoid are here: https://harmful.cat-v.org/software/. remember, we are looking for the most minimal yet still extremely flexible software.

## goals

- **minimal toolchain** the most minimal and modularized programs should be used per UNIX and Suckless philosophies.
- **glibc and proprietary software** support all proprietary and glibc based software even if the system is not glibc based.
- **uefi and bios support, minimal-kernel target** A trimmed linux kernel (`monarch`) configured from `tinyconfig` plus whatever settings are needed for additional compatibility/flexibility or support for things like bluetooth and wifi, and a trimmed linux-zen/performance kernel (`firefly`) with a minimal configuration with optimizations not included in linux kernel. paired with limine bootloader.
- **plan mode first** ask me before building anything in the project (implement plan mode to start), and to re-read README.md every time you want to make a change to make sure it aligns with the project. summarize and compress memory after every session.
- **flexibility** the user of the distro should be able to make the system as minimal or as bloated as they want to, but we will keep it as a baseline system with many packages to offer.
- **software in c** if we can create/code a tool in c that is more minimal that an external tool, ask to build it from scratch instead of using the outside tool.
- **package manager** we will build our own package manager, `branch`, that is a pacman clone written in C. it will have a sibling program `leaf` as the aur helper. this system will masquerade as an arch linux-based system/distro but with much less bloat and more flexibility in its software.
- **caveman ultra mode** this entire conversation should have caveman ultra always on, and all other conversations with claude.
- **ruflo** use ruflo agents to the maximum in order to be as productive as possible while staying controlled.
- **suckless** use suckless utilities when possible. always prefer utilities from suckless to provide tools. https://git.suckless.org/ 
- **from source** all dependencies/build tools/packages should be built from source. for example, the linux kernel should be built from the tree https://git.kernel.org/.

## repos in the package set

built packages put in repo (`zenith`) as `.pkg.tar.zst` archives that can be accessed by the project's own package manager, all package descriptions should be short and concise and lowercase.

the repositories are listed below with proper packages that should exist in each.

- `twilight` — toolchain dependencies (ex. c compiler, libc implementation, …).
- `dawn` — userland (ex. sbase, ubase, …).
- `dusk` — extra packages (desktop stack, tuis, …).
- `afterglow` — testing packages (unstable/testing packages, …)

all of these repositories live in ~/projects/zenith/$REPO/$ARCH directory.

currently, $ARCH is only x86_64 for now, but make room to extend compatibility with other architectures.

this document should be the basis of the entire system. write this to memory

do not update this file. 
