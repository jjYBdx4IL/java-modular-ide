# Java Modular IDE

You don't like the current set of free IDEs for Java? Then join us and let's make a state-of-the-art one!

## Current state

Looking for comments, volunteers, contributors, supporters, etc.

## Goals

* Better license: Apache License v2.
* Strictly modular: re-use components in other projects!
* Re-usability improves usability!
* KISS - keep it simple, stupid!
* Support for extended technologies like Android, other languages, J2EE etc. **is not a primary concern** because it would distract from a stable core too much, but can be provided through modules. A lot of these technologies don't really need extensive support from the IDE and the strange GUI frontend IDEs like Eclipse and Netbeans provide, are usually a pain to debug because users don't actually know what's going on when using them.

## Main problems we have to solve

* Full Java code support. The modularity must allow to use different code parsers/AST generators, ie. javaparser and eclipse compiler.
* Integration of code support with EditorKit. Or some other Swing-based editor component that can provide syntax highlighting and all the other editor features.
* Build system? We should at least support Maven. The IDE does not care about the build system too much, it essentially just needs to know about dependencies and source code locations. Ideal would be an external, continuous build system, configured like an embedded Jetty instance, that can be configured to scan for source changes and recompile and re-test as necessary. I never liked the idea of using XML to configure strongly-typed Java applications. Why not configuring stuff in Java code?
* JUnit test execution. The aforementioned continuous, external build system/server could provide this more naturally than any IDE: it could maintain a dependency hierarchy between the classes and use that information to decide which unit tests to re-run when a source file gets updated.

## Differences to other IDEs

* Using only Swing GUI elements (vs Eclipse's SWT that looks nice but even fails to scroll editor contents properly...).
* Functionality over superficiality. We don't care if the IDE is ugly. It must be bug-free and 'hardened' for serious every-day work. (Netbeans has a ton of annoying bugs that never get fixed).
* Default theme is non-bright. No use of OS GUI elements that force users to change their desktop colors to affect the IDE's background colors (as seen in Eclipse and in Netbeans partially). No strange artifacts like the ones that you can see, for example, in the problem marker list in Eclipse when using a dark theme because the table cell borders are rendered in bright white and make the list essentially unreadable. This is all a sympton of the Eclipse publishers not caring enough -- the theme is provided by a 3rd party although a massive amount of users are complaining!
* Support to scale the GUI (ie support high DPI monitors), maybe at the start simply by using a configurable base font size.
* Reliable IDE component hosting at the maven central repository (unlike Eclipse market place - most installs and uninstalls take 10 minutes or something), hosted by a non-profit organization. Re-use of the sonatype aether stuff to resolve IDE dependencies.
* Extremely free and clear license. (Eclipse: their FAQ can't even assure you that you can use their stuff in commercial projects unless you talk to a lawyer... why do they even have to use their own license? wtf? Netbeans: GPL).

## Final words

Comments are welcome. All types of contributions and support are welcome!
