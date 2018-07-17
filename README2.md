#slackCheck for GITHUB and TRAVIS with SLACK

Inorder to check whether we get message in slack, we are using Fetch program thats all. Main concept is to check whether slack is connected
to github and travis.

----------------------------------------------------------------------------------------------------------------------------------------------
this repository has been connected to slack  " blooming-buds.slack.com " with the channel checkandgo channel . That channel has also connected
to travis. But when build happens in this repository, it fails and error occurs.That error is also been showed as a message in slack.
Now,when this project is changed or pushed then that will be send as a message in slack under the channel checkandgo....
----------------------------------------------------------------------------------------------------------------------------------

First GITHUB + SLACK :

1.create a channel named checkandgo
2. install github in apps section
3. after installing give the channel and select the repository. so that any changes made in specified repository will come in checkandgo.
4. now, in checkandgo channel type the command...
      /github subcribe KaviyaSriBathrachalam/slackCheck reviews comments pulls statuses deployments issues releases branches
      (github subcribe GITHUB_USERNAME/REPO_NAME reviews comments pulls statuses deployments issues releases branches)
      
5. then, this repository slackCheck has been added to slack under channel checkandgo. So, that any changes made in this repository will come under channel.
_________________________________________________________________________________________________________________

Second TRAVIS + SLACK :

1. install travis in apps
2. select channel checkandgo(according to convenience, you can create new channel and install travis too) then you will ask for addconfiguration.
3. Click Add configuration and you will find a token copy the token and put the token it in travis.yml file

    slack: blooming-buds:nUj3EVuUQ8csVY2Q8zCtgoQC  under notifications.
    
 4. Now, build it in travis. You will find the message in travis.
 
 NOTE : My travis will not work. So, i will get error while building in travis. I will get error message in slack.
 
 ERRORS FOUND :
 
 1. when i need to push the project, it asked for pull.. i did pull and pushed, but again it got rejected and asked for pull.
    Should put the command as 
    git pull origin master --allow-unrelated-histories
and then push

then it works!
-----------------------------------------------------------------------------------------------------------------------------------
REBASING and MERGING :
https://www.atlassian.com/git/tutorials/merging-vs-rebasing

REBASING IN DETAIL :
https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase
_------------------------------------------------------------------------------------------------------------
TO RUN : 

mvn install
mvn spring-boot:run

MAIN TO RUN :

If any changes done., git init

2.git add .
3.git commit -m "travis+github+slack"
4.git push origin master (if rejected)
5.git pull origin master
6. git push origin master. IT will work.

If again rejected and doesn't work., 

7.     git pull origin master --allow-unrelated-histories
8. git push origin master. It works.
-----------------------------------------------------------------------------------------------------------------

==> 17/7/2018


 
 
 
