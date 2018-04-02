# Continuous Inspection

#### Overall Health
Your project home page shows where you stand in terms of quality in a glimpse of an eye. This main page also shows you an immediate sense of the good results achieved over time.

#### Focus on the Leak
The water leak paradigm is a simple yet powerful way to manage code quality: quality of new - changed and added - code should be put under control before anything else. Once that Leak is under control, code quality will start improving systematically. In SonarQube, the Leak is a built-in concept that you can’t miss. Once you’ve had a look at this yellow area on the left of your project home page, you will always remain focused on it to not miss any new issues.

#### Enforce Quality Gate
With SonarQube, a developer has everything at hand to take ownership of the quality of his code. To fully enforce a code quality practice across all teams, you need to set up a Quality Gate. This core concept of SonarQube is a set of requirements that tells whether or not a new version of a project can go into production. SonarQube’s default Quality Gate checks what happened on the Leak period and fails if your new code got worse in this period.

#### Analyze pull requests
Once you have SonarQube in place, you will quickly want to make sure you add as few issues as possible to your code base. To shorten the feedback loop so you don’t have to wait for new analyses to be available on SonarQube, you can set up the analysis of your pull requests. Analyses will be run on your feature branches without being pushed to SonarQube, giving you the opportunity to fix issues before they ever reach SonarQube!

#### Branch Analysis
Track the quality of short-lived and long-lived code branches in SonarQube to ensure that only clean, approved code gets merged into master.

#### Dig into issues
The “Issues” page of your project gives you full power to analyze in detail what the main issues are, where they are located, when they were added to your code base and who originally introduced them. Specifically, you can be notified via email when you introduce new issues, then you simply click on the link in the email to see the set of new issues assigned to you for review.

#### Highlight hot spots
SonarQube treats test coverage and duplications, two of the major software quality problems, as first class citizens. The “Measures” page lets you browse your project in different ways to highlight files that need your attention. More generally, for each main domain SonarQube provides a bubble chart that correlates different metrics to highlight other potential hot spots.

#### Visualise the history of a project
Thanks to the Activity page you can dig into the details of the history of your project very easily and precisely to better understand what happened in the past. Use graphs and visualisations to track project quality over time and zoom in on specific time periods for more granular analysis.

# Detect Tricky Issues

#### Code Smells
“Smelly” code does (probably) what it should, but it will be difficult to maintain. In the worst cases, it will be so confusing that maintainers can inadvertently introduce bugs. Examples include duplicated code, uncovered code by unit tests and too complex code.

#### Security Vulnerability
It’s probably Pollyanna-ish to think you’ll never be targeted by hackers. When you are, what vulnerabilities will they find in your system? SonarQube helps you find and track the insecurities in your code. Examples include SQL injection, hard-coded passwords and badly managed errors.

#### Activate The Rules You Need
SonarQube code analyzers include default Quality Profiles that offer strong value with non-controversial rule sets. The default Quality Profiles will work for most projects, but you can easily tune them to fully match your needs. The rules page enables to find rules by multiple criteria, alone or in combination. From the search results you can activate or deactivate rules in your Quality Profile.

#### Explore All Execution Paths
SonarQube relies on several path-sensitive dataflow engines and thus code analyzers explore all possible execution paths to spot the trickiest bugs. Even a simple function containing only 10 different branches might lead to 100 different possible execution paths at runtime. Manually checking that those 100 execution paths are error proof is simply impossible.

# Multi-language

#### 20+ Programming Languages
With SonarQube comes a code analyzer for each major programming language. Each analyzer provides numerous rules to spot general and language-specific quality issues.

[C/C++](http://redirect.sonarsource.com/plugins/cpp.html)
[JavaScript](http://redirect.sonarsource.com/plugins/javascript.html)
[C#](http://redirect.sonarsource.com/plugins/csharp.html)
[Java](http://redirect.sonarsource.com/plugins/java.html)
[COBOL](http://redirect.sonarsource.com/plugins/cobol.html)
[TypeScript](https://redirect.sonarsource.com/plugins/typescript.html)
[PL/SQL](https://redirect.sonarsource.com/plugins/typescript.html)
[PL/I](https://redirect.sonarsource.com/plugins/pli.html)
[PHP](http://redirect.sonarsource.com/plugins/php.html)
[ABAP](http://redirect.sonarsource.com/plugins/abap.html)
[T-SQL](https://redirect.sonarsource.com/plugins/tsql.html)
[VB.NET](http://redirect.sonarsource.com/plugins/vbnet.html)
[VB6](https://redirect.sonarsource.com/plugins/vb.html)
[Python](http://redirect.sonarsource.com/plugins/python.html)
[RPG](http://redirect.sonarsource.com/plugins/rpg.html)
[Flex](http://redirect.sonarsource.com/plugins/flex.html)
[Objective-C](http://redirect.sonarsource.com/plugins/objectivec.html)
[Swift](http://redirect.sonarsource.com/plugins/swift.html)
[Web](http://redirect.sonarsource.com/plugins/web.html)
[XML](https://redirect.sonarsource.com/plugins/xml.html)

#### Multi-Language Projects
Applications often use several programming languages at once, for example [C#, C++ and JavaScript] or [Java, JavaScript and HTML]. SonarQube automatically detects these languages and invokes the corresponding analyzers.

#### Languages Consistency
When switching from one language to another, the user experience remains consistent, with the same way to describe and tag rules, report issues, evaluate remediation effort… Moreover, when a quality issue pattern is common to several languages, the rule for that pattern is available for all relevant languages.

# DevOps Integration

#### Build Systems
For dynamic languages like JavaScript, PHP, Python, … executing an analysis is as easy as feeding SonarQube with a bunch of source files. But for languages like Java, C#, C, C++ and Objective-C, there is simply no way to provide accurate results without being part of the build. That’s why built-in integrations are provided for MSBuild, Maven, Gradle, Ant, and Makefiles.

#### CI Engines
Native integrations with build systems let you easily schedule the execution of an analysis from all CI engines: Jenkins, VSTS, TFS, Travis-CI… Don’t worry if your CI engine isn’t listed here, integration effort will be minimum.

#### Pass/Fail Notification
Once an analysis is done, a report is sent to the SonarQube server to be integrated. At the end of this integration, a standard webhook mechanism lets you notify any external system to do whatever you want: trigger an alarm, update a wallboard, notify a chat room.

#### Full Web API
As part of the overall development ecosystem, the SonarQube Web API can be used to automatically provision a SonarQube project, feed a BI tool, monitor SonarQube, etc. Morever the list and definition of all the Web API is built in SonarQube

#### Promotion Pipelines
Using webhooks, SonarQube can be integrated as a promotion step in your delivery pipelines. This way, you can make sure that only artifacts that pass the Quality Gate will be released and deployed to production.

#### High Availability
Ensure maximum uptime code quality services for distributed global developer teams and high-volume projects. Test hundreds of millions of lines of code across multiple locations and teams without worrying about downtime or interruption.

# Centralize Quality

#### All projects in one place
Getting everyone on a team on the same page about quality is hard enough. What happens when you expand the scope to a department or an entire organization? SonarQube enables you to centralize and scale a single vision of code quality.

#### Shared rulesets
SonarQube offers a central place to view and define the rules used during analysis of projects. These rulesets are organized in quality profiles. Every member of the organization can see which rules are applied to their project. Every project administrator can choose which quality profile is used for the project.

#### Unified Quality Gate
SonarQube provides out-of-the-box a default Quality Gate focusing on the Leak concept. This means that the same requirements will be applied across the board to every project - greenfield and legacy; in-house, out-source and off-shore.

#### Cross projects services
Most services are available cross projects. For example, as a developer you can use the issues service to get all new issues assigned to you - across projects - so that you can concentrate on your work. As a technical lead, the projects page lists all your favorite projects and lets you explore them on different axes.

#### Risk-based views
Executives will use aggregated dashboards which come as part of the Governance product not only to get the big picture about quality of projects but also to assess their risk: Reliability, Security, and Maintainability; as well as the overall Releasability (Quality Gate adherence). The timeline charts let you assess changes in project quality over time, or zoom in on a subset of the project history to pinpoint changes in quality gate status.

#### Parallel report processing
Ensure fast, efficient report generation and processing across multiple fields of analysis…no matter how many projects you have or how complex your reporting requirements are!
