# Patterns & Anti-Patterns

1. Make It Work, Then Make It Pretty
1. Publish Early, Publish Often
1. Use [Git](http://git-scm.com/)
1. Use [Github](https://github.com/)
1. One Github Repo per Chef Cookbook
1. Use All Available Resources for Help
1. Use Code Reviews
1. Use Automated Testing
1. Use Continuous Integration/Deployment
1. Monitoring Is Just Continuous System/Service Testing
1. Logging is Monitoring Too
1. [ChaosMonkey](http://www.readwriteweb.com/cloud/2010/12/chaos-monkey-how-netflix-uses.php) Is The (Current) Holy Grail

# Make It Work, Then Make It Pretty

* Doing part one without part two is an __anti-pattern__
    + You will have jury-rigged a landmine in your infrastructure
    + Then foreverafter, you must always walk on eggshells around it
    + In twenty ${time-units} you won't remember what you did, why, or how and it __WILL__ blow up in your face

.notes ${time-units} could be years, months, weeks, days, hours, minutes,
or even seconds.  The point is the same.  However, if you focus on making
it pretty first, you'll get way down the line before you discover whether
or not the idea will actually work.

# Publish Early, Publish Often

* Helps encourage both parts of #1
    + Publishing something ugly is a negative feedback mechanism
* Encourages working in smaller increments that are more digestible

# Use [Git](http://git-scm.com/)

* All tools for Chef that assist with SCM workflow will assume [git](http://git-scm.com/)
    + Probably won't work with anything else
* As a Distributed VCS, git encourages frequent small commits, where tags and branches are trivially easy
* [WhyGitIsBetterThanX](http://whygitisbetterthanx.com/)

# Use [Github](https://github.com/)

* Github is Facebook+LinkedIn for Developers & DevOps
    + It's how you show prospective employers what work you've done
    + It's how prospective employers show you what kind of work you might be doing
* Github is the largest Git community
    + Github works very hard to make it as easy as possible for people and groups to collaborate with each other
    + Git+Github is one of the most powerful tool combinations in your toolbox

.notes You can even do your Résumé in Markdown format, on github -- Résumé As Code FTW!

# One Github Repo per Chef Cookbook

* With Git and Github, collaboration occurs primarily at the repo level -- forking, sharing, remotes, committing, etc...
    + Each Chef cookbook should be largely standalone
    + Therefore, each Chef cookbook should be a separate repo
    + Can combine multiple repos together with [Librarian](https://github.com/applicationsonline/librarian), [Braid](https://github.com/evilchelu/braid/wiki), or git submodules

# Use All Available Resources for Help

* No one can be an expert on everything
    + Whatever you're trying to do, someone else has probably already tried it
    + Don't stubbornly insist on re-inventing the wheel
* Use
    + Wiki: [http://wiki.opscode.com/](http://wiki.opscode.com/)
    + Bug Tracker: [http://tickets.opscode.com/](http://tickets.opscode.com/)
    + Community Cookbooks: [http://community.opscode.com/cookbooks](http://community.opscode.com/cookbooks)
    + Chef Mailing list: [http://lists.opscode.com/sympa/info/chef](http://lists.opscode.com/sympa/info/chef)
    + irc: [irc.freenode.net #chef](irc://irc.freenode.net/chef)
    + Hosted Chef:
        - Free for first five clients
        - Free access to Opscode Support: support@opscode.com

.notes Opscode support for free Hosted Chef customers is "best effort", but
it's real live support from real live human beings who actually work at
Opscode and who generally have a clue or three

# Use Code Reviews

* 80-90% of the time, I catch my code errors on proper inspection when I try to explain the code to someone else
* 80-90% of the remainder, my code errors are caught on inspection by the person who reviews my code
* If I skip code reviews, I lose the 95-99% error catch rate that having a programming partner would bring to the table

# Use Automated Testing and Test Driven Development

* Chef [minitest](https://github.com/seattlerb/minitest) and [Rspec](https://github.com/acrmp/chefspec) are improving
    + Still beta quality code
    + Still not as well documented as they should be.
* [Cucumber-chef](https://github.com/Atalanta/cucumber-chef) is currently dependent on Amazon EC2
    + Needs more work (e.g., needs to support other cloud platforms)
    + Needs better documentation
	- [Test-Driven Infrastructure with Chef](http://shop.oreilly.com/product/0636920020042.do) is supposed to just be a "taste"
* Follow [Stephen Nelson-Smith](http://www.atalanta-systems.com/people.html) ([@LordCope](https://twitter.com/#!/LordCope))
    + For all aspects of TDD/BDD, not just cucumber-chef

.notes Whether it is Unit Testing, Integration Testing (check out
[Toft](https://github.com/exceedhl/toft)), Regression Testing,
Stress Testing, Fuzzing, whatever, it doesn't matter -- do as much
as you can now, automate it as soon as you can, and add more as
quickly as you can.

# Use Continuous Integration/Deployment

* We use [Jenkins](http://jenkins-ci.org/) but the tool you use is less important than doing CI in some fashion
    + [chef-jenkins](https://github.com/adamhjk/chef-jenkins) is the tool to use Jenkins to drive continuous deployment and synchronization of your Chef Environments from a git repository
* Chef is all about automating the management of the configuration of your infrastructure, and CI tools like Jenkins dovetail naturally with that

.notes If you do all the other things, then with proper CI/CD, you should
be able to deploy at will, tens or even hundreds of times per day,
and with virtually no risk of causing problems for your production
environment.  Moreover, you will have automated methods of falling
back to the previous version, if the deployment does fail.

# Monitoring=Continuous System/Service Testing

* You need both internal and external monitoring
    + We use [Zenoss](http://community.zenoss.org/) and
      [monit](http://mmonit.com/monit/) for internal monitoring
    + We use [CopperEgg RevealCloud](http://www.copperegg.com/product/revealcloud)
      for external monitoring
* You need to monitor the systems, the applications, and the services
    + We use Zenoss and RevealCloud to monitor our systems
    + We use monit to monitor our applications
    + We use Zenoss to monitor our services

# Logging is Monitoring Too

* Logging is just another way to monitor what is going on with your systems & applications
    + Forwarding & Gathering  -- syslog-based (e.g., rsyslog & syslog-ng) and agent-based (incl. graylog agent, logstash, Splunk forwarders, etc...)
    + Analytics (e.g., graylog2, logstash, Splunk, etc...)
* Logging and log analysis is just as critical (if not more so) as monitoring
    + System, Service, and Application monitoring tell you __what__ is happening
    + Log processing is more likely to be able to tell you __how__ and __why__

# [ChaosMonkey](http://www.readwriteweb.com/cloud/2010/12/chaos-monkey-how-netflix-uses.php) Is The (Current) Holy Grail

* Failure __will__ happen -- It's not a matter of __if__, but __when__
    + What if you could have some control over when failure occurs and how
your systems respond?
