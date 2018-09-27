# Adding scheduled jobs and remote build Triggers

### Build Triggers
Build triggers decide when a jenkins job is run. Whether it happens based on a external event e.g. a push to git repository, a scheduled run, or a job is run after another job is completed, there are plenty of options to trigger builds.

From project page, click on **Configure**.

### Types of Triggers
  1. Trigger builds remotely
  2. Build after other projects are built
  3. Build periodically
  4. Poll SCM

### Execute Jobs Remotely

Jobs can be triggered remotely outside of jenkins. This is very useful when you would like the jobs to be triggered based on some event or part of the logic you have written as part of your script. This is also the way you would trigger the job based on the activities performed on the repositories. e.g. adding new commit to git hub.

### Example

 Goto Select Project --> configutation --> Build trigger

 Select Build periodically and add your schedule Trigger for run at continours manner.

 ![local](images/Triggers/Trigger1.png)
* In **Build Trigger**, check **Trigger Builds remotely**.
![local](images/Triggers/remote.jpg)
* Define a token (More complex one than the example)
* Save the job.
* To trigger the job, you need two things
  * user
  * user's API token

* Create url file using your user name and API token in your terminal
  * user:<API_TOKEN>@<Jenkins_URL>/job/job1/build?token=<JOB_TOKEN>
   * example: http://admin:552dab89b070c0fcc3fad281c51318ad@10.40.1.14:8080/job/job1/build?token=mytoken

 * Goto jenkins_homepage -> people -> admin -> configure
  ![local](images/Triggers/flow.gif)

  Click on **Show API Token** Note down the user's **API token**.
  * Visit the trigger from browser or use curl
    * example: http://admin:552dab89b070c0fcc3fad281c51318ad@10.40.1.14:8080/job/job1/build?token=mytoken
  * This will Trigger the build
    ![local](images/Triggers/trigger.jpg)
