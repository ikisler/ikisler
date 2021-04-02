## Hello! 👋

I'm a backend software engineer interested in working on projects with a positive impact.

With my background in business, I appreciate how technical needs integrate with the overall business needs, and take a pragmatic approach to balancing these sometimes opposing forces.  In my current role, I've worn many different hats -- this has helped me learn how to think on my feet and how to pick up new technologies quickly.

### Contact 📬
The best way to contact me is via [LinkedIn](https://www.linkedin.com/in/ikisler/)

### Technologies 💻
Some technologies I'm familiar with include:
- PHP
- Symfony
- JavaScript
- Python
- Java
- C++
- AWS
- Docker
- LAMP stack
- Apache
- MySQL
- HTML
- CSS

### Currently Learning 🎓
Recently, I took a series of courses from Udacity and earned a [C++ Nanodegree!](https://graduation.udacity.com/confirm/K5UWGKEA)  For more information about this program, check out [Udacity's page about it](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213).

<img src="https://s3-us-west-2.amazonaws.com/udacity-printer/production/certificates/ae7d071c-a877-425a-aa2f-b2a48ba3755c.svg" width="500">

### Projects ☕
Some major projects I've worked on in the last few years include (click the project name for more details):

<details><summary>Reporting rewrite/redesign</summary>

#### Explanation:
In order to meet the future needs of our users, our reporting engine had to change significantly; so significantly that the decision was made to create something new from the ground up.  The existing reporting module was largely legacy code, tightly coupled to the frontend and suffering from problems related to the data storage format.  For this project, I designed a system that is could be reasonably migrated to from our existing structures, while completely sidestepping certain issues related to performance and scalability.  Using the Symfony framework for this project as opposed to our legacy home-grown framework introduced a number of built-in standards, making the structure and code easier to reason about for future developers.
#### Technologies used:
- PHP
- Symfony framework
- AWS services
- NodeJS
#### Skills used / improved:
- Leadership; communicating designs, goals, requirements with other engineers
- Interpersonal skills; this project involved a lot of push/pull with our product owners to meet user needs in a reasonable timeframe
</details>

<details><summary>Data warehouse</summary>

#### Explanation:
This project's main goal was gathering meta data regarding usage and engagement of our users.  We wanted this whole system to be independent from our existing data storage and structures, which opened up a number of possibilities.  For this project, I did a significant amount of research regarding structures for big data, and chose to implement a star schema in AWS Redshift.  To get data into Redshift, I used a set of PHP scripts to feed data into AWS Glue, where it was processed via Python and inserted into Redshift.  Metabase was used for the frontend, taking advantage of the speed and simplicity of implementing a "boxed" solution.
#### Technologies used:
- PHP
- Python
- AWS Redshift
- AWS Glue
- Metabase
#### Skills used / improved:
- New database types and more about schema design
- New technologies (Redshift and Glue)
</details>

<details><summary>Move to AWS / cloud infra</summary>

#### Explanation:
Moving to AWS was a big step in our goal to make the engineering side of the company more scalable.  The ability to tailor our server sizes and number to load, and the ability to easily create servers for tests and experiments was a huge benefit.  In order to get to this point though, we had a huge amount of work to undertake; our requirements related to disaster preparedness and security are unusual enough that we couldn't just pick everything up and move it to the cloud.  My manager and I worked closely together to plan out all the steps of this transition, and I spearheaded the implementation.  The project was done in steps; we integrated as many services as we could up front in our existing architecture, to spread the risk of change and unexpected consequences out as much as possible.  Eventually we had a series of downtime to move our actual databases over to AWS, which I automated with a series of scripts.  Overall, the project was a huge success, and we have since been able to take advantage of the agility that this move granted us.
#### Technologies used:
- AWS EC2 and VPC
- AWS S3
- DynamoDB
- Lambda
#### Skills used / improved:
- Organization (significant number of security and stability requirements to keep track of)
- Refactoring (making legacy code less stateful to allow better scaling)
- Learning new technologies (AWS)
</details>

<details><summary>Reduce run time for nightly batch jobs by 70%</summary>

#### Explanation:
This had been a long-time issue at the company -- at one point, nightly batch jobs were taking something like 12 hours to complete, and while effort had been made at that time to reduce this and introduce some metric gathering, the time it took to complete still ballooned up as use increased.  I was given the directive to drastically reduce this run time, and I was able to achieve an 70% reduction via a combination of improving process efficiency, and implementing concurrent processes.

This project involved doing some analysis on our current processes to determine how much improvement could be made by changing code; this portion had some significant constraints around it in terms of the company's appetite for risk.  I could make code changes, but could not implement refactoring to the same scale as I had done to improve report load times.  Again, I discovered time spent making trips to the database accounted for a significant amount of time, so I used data transfer objects to reduce these trips significantly.  The greater improvement came without touching any existing code at all; the fact that the nature of the work was already largely in self-contained "blocks" made implementing concurrent process relatively simple.  By separating out these blocks and running them at the same time, we could also take advantage of existing extra server capacity, getting the most use out of our current resources.  Ultimately, I was able to reduce total run time by 70%.
#### Technologies used:
- PHP
- XDebug and Webgrind for profiling
- Bash
#### Skills used / improved:
- Performance analysis
- Improving performance without significantly changing code structure
</details>

<details><summary>Reduce average load time for reports by 90%</summary>

#### Explanation:
For this project, my first step was research; basically, identifying what the problem was specifically.  In our system, we had both pre-made and ad hoc/user-created reports, so it wasn't just a case of running through our standard suite of reports and fixing up certain queries.  As part of my research, I looked over support tickets and talked with our support and product people; this research netted me several good examples that I could use as a baseline to measure my improvement.

After identifying examples of the issue, I then spent some time profiling the requests using XDebug and Webgrind -- I was able to identify specifically one area which contained a significant amount of data processing, and another area where we were making a lot of repetitive database queries.  The database query issue was pretty simple to resolve; gather all the data in just one query and keep it cached for all the places it was required.  The other area with the data processing, was much more difficult to improve.  This is a legacy codebase, and there was little to no comments or explanation in terms of code structure to help determine exactly what the purpose of the data processing was, so I had to determine this myself.  What I found was surprising; in most cases, there was absolutely no need to spend all this time processing data, and in the cases where there was a need, the algoritm could be simplified significantly.  Refactoring this portion of code was a big job, and involved making some changes in the (unfortunately) closely coupled frontend as well.  However, once released, it reduced average load time of reports by 90 percent.
#### Technologies used:
- PHP
- XDebug and Webgrind for profiling
#### Skills used / improved:
- Refactoring
- Code profiling
</details>

<!---
ikisler/ikisler is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
