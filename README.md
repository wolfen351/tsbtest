# TSB DevOps Role - Test Result

![Logo](https://github.com/wolfen351/tsbtest/raw/master/1.%20Documentation/Company%20name%20and%20logo/Burst%20Pizza.png)

I spent the weekend building this little DevOps demo for you. Please feel free to explore!

Starting with the requited feature list, I expanded out the list a little with my own ideas of how a company like that would operate. I put together a more comprehensive list of features and then went about looking what IT systems would need to be created/implemented to support it. 

Following this I spent some time thinking about the nature of the business, and how quickly it wants to grow. I split up the IT into in-shop and centrally provided services. I then designed a overview of those systems and where they fit in in a diagram. 

Next up, was to zoom into a particular area of the business and build "something" to show my DevOps skills. I zoomed into the development team and created a diagram to show how that team would work. 

As I chose to demonstrate my DevOps skills instead of my development skills. I put together a really really basic skeleton (like v0.001) of the pizza shop's live CI/CD system. The idea is to show you that I understand the concepts and that I can apply them even in a very simple demo situation. 


## Structure and Nature

There are several folders numbered 1 to 4. These contain the documentation and the various aspects and configuration files that I used to create the solution. 

Parts of the system are live on the Internet that you can interact with. They are hosted on one of my home servers - so feel free to mess around with them. 

### Prerequisites

The url of the Jenkins system is:  http://home.wolfen.za.net:8081/

The url of the 'production' web server is:

http://home.wolfen.za.net/tsbtest/

The url of the source control (svn) server is:

http://home.wolfen.za.net/svn/tsbtest/

### Credentials
You will need credentials for interacting with SVN and with Jenkins etc.
```
User: tsbtest
Pass: tsbtest!
```


## Running the tests

Ok, so now you've read all the documentation and you just want to see how this all works! 

### Step 1: Developer Machine

Check out the code using SVN:

```
svn co http://home.wolfen.za.net/svn/tsbtest/
```

### Step 2: Change something

I created a simple date.txt file that is part of the "website" to demonstrate the ability to change stuff. 

```
date > date.txt; svn commit -m "Test commit"
```

### Step 3: Check in 

Check in the hard work and observe the magic in Jenkins
```
svn commit -m "Worked on the date thing"
```

### Step 4: Jenkins

Open Jenkins and see 2 builds run automatically. The first checks out the code, 'tests' it, and then if the test 'passes', it checks in the artifacts for production deployment.

Then the production deployment jobs sees the commit, tests it and auto deploys it. 

These are just barebones skeletons for now, but could obviously be extended as needed.

Jenkins URL Again: http://home.wolfen.za.net:8081/

### Step 5: Verify against live

Check the changes made have 'gone live'. 

http://home.wolfen.za.net/tsbtest/date.txt

## Built With

* Jenkins - The Automation Tool
* SVN - Source Control
* Apache - Web Server

## Author

* **Iain Prior** - *Initial work* 

## License

(c) All rights reserved. Any and all permissions granted implicitly or explicitly may be revoked without notice, for any reason. No warranty is given to the fullest extent permitted by law.

## Acknowledgments

* TSB Bank for an awesome question, had fun building this
* Ubuntu server team for making this all possible
* The rest of the open source community - you guys rock!


