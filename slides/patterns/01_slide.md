# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty

* Doing part one without part two is an anti-pattern
    + You will have jury-rigged a landmine in your infrastructure
    + Then foreverafter, you must always walk on eggshells around it
    + In twenty ${time-units} you won't remember what you did, why, or how and it __WILL__ blow up in your face

.notes ${time-units} could be years, months, weeks, days, hours, minutes,
or even seconds.  The point is the same.  However, if you focus on making
it pretty first, you'll get way down the line before you discover whether
or not the idea will actually work.

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often

* Helps encourage both parts of #1
    + Publishing something ugly is a negative feedback mechanism
* Encourages working in smaller increments that are more digestible

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git

* All tools for chef that assist with SCM workflow integration will assume git
    + Probably won't work with anything else
* As a Distributed VCS, git encourages frequent small commits, where tags and branches are trivially easy
* [WhyGitIsBetterThanX](http://whygitisbetterthanx.com/)

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github

* Github is Facebook+LinkedIn for Developers & DevOps
    + It's how you show prospective employers what work you've done
    + It's how prospective employers show you what kind of work you might be doing
* Github is the largest Git community
    + Github works very hard to make it as easy as possible for people and groups to collaborate with each other
    + Git+Github is one of the most powerful tool combinations in your toolbox

.notes You can even do your Résumé in Markdown format, on github -- Résumé As Code FTW!

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github
1. One Github Repo per Chef Cookbook

* With Git and Github, collaboration occurs primarily at the repo level -- forking, sharing, remotes, committing, etc...
    + Each Chef cookbook should be largely standalone
    + Therefore, each Chef cookbook should be a separate repo
    + Can combine multiple repos together with [Librarian](https://github.com/applicationsonline/librarian), [Braid](https://github.com/evilchelu/braid/wiki), or git submodules

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github
1. One Github Repo per Chef Cookbook
1. Use Code Reviews

* 90% of the time, I catch my code errors on proper inspection when I try to explain the code to someone else
* 90% of the remainder, my code errors are caught on inspection by the person who reviews my code

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github
1. One Github Repo per Chef Cookbook
1. Use Code Reviews
1. Use Automated Testing and Test Driven Development

* Chef [minitest](https://github.com/seattlerb/minitest) and
[Rspec](https://github.com/acrmp/chefspec) are improving but still
alpha/beta quality code, and still not as well documented as they
should be.

* [Cucumber-chef](https://github.com/Atalanta/cucumber-chef) is
currently dependent on Amazon EC2, and needs more work as well as
better documentation (e.g., better than [Test-Driven Infrastructure
with Chef](http://shop.oreilly.com/product/0636920020042.do)).

    * [Stephen Nelson-Smith](http://www.atalanta-systems.com/people.html)
      ([@LordCope](https://twitter.com/#!/LordCope)) is one of the
      the key people to follow for all types of TDD/Behaviour Driven
      Development, and not just cucumber-chef

.notes Whether it is Unit Testing, Integration Testing, Regression
Testing, Stress Testing, Fuzzing, whatever, it doesn't matter -- do as
much as you can now, automate it now, and add more as you can.

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github
1. One Github Repo per Chef Cookbook
1. Use Code Reviews
1. Use Automated Testing
1. Use Continuous Integration/Deployment

* We use [Jenkins](http://jenkins-ci.org/) but the tool you use is less
important than doing CI in some fashion

    + [chef-jenkins](https://github.com/adamhjk/chef-jenkins) is
    the tool to use Jenkins to drive continuous deployment and
    synchronization of your Chef Environments from a git repository

.notes If you do all the other things, then with proper CI/CD, you should
be able to deploy at will, tens or even hundreds of times per day,
and with virtually no risk of causing problems for your production
environment.  Moreover, you will have automated methods of falling
back to the previous version, if the deployment does fail.

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github
1. One Github Repo per Chef Cookbook
1. Use Code Reviews
1. Use Automated Testing
1. Use Continuous Integration/Deployment
1. Monitoring Is Just Continuous System/Service Testing

* You need both internal and external monitoring
    + We use [Zenoss](http://community.zenoss.org/) and
      [monit](http://mmonit.com/monit/) for internal monitoring
    + We use [CopperEgg RevealCloud](http://www.copperegg.com/product/revealcloud)
      for external monitoring
* You need to monitor the systems, the applications, and the services
    + We use Zenoss and RevealCloud to monitor our systems
    + We use monit to monitor our applications
    + We use Zenoss to monitor our services

# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use Git
1. Use Github
1. One Github Repo per Chef Cookbook
1. Use Code Reviews
1. Use Automated Testing
1. Use Continuous Integration/Deployment
1. Monitoring Is Just Continuous System/Service Testing
1. [ChaosMonkey](http://www.readwriteweb.com/cloud/2010/12/chaos-monkey-how-netflix-uses.php) Is The (Current) Holy Grail

* Failure will happen -- It's not a matter of if, but when
    + What if you could have some control over when failure occurs and how
your systems respond?
