# jenkins
# kubernetes
  create a minikube cluster
  create a namespace
  install jenkins with helm v3
  create a persistent volume
  create a service account deploy jenkins
# linux installers
  debian/ubantu
  fedora
  red hat/centOS
# offline installation can be done by WAR file
# apache tomcat is required to deploy jenkins
# jenkins in macOS
  ~brew install jenkins-lts (downloads and updates)
  ~brew list(shows installations)
  ~brew services list(shows status of files)
  ~brew services start(name of service) jenkins-lts(starts the file)
  ->open browser  ->localhost:8080 
                  ->change directory to which we can see on localhost to find out password (secrects ls -> secrects cat initialAdminPassword)
                  ->open file copy and paste password in browser  
  ->install suggested plugins
  ->create username and password
  ->start using jenkins

 

# creating jenkins build
  ->copy and paste password
     ->admin->configure->password->change password->save
  ->new item   ->jenkins-hello-world   
               ->freestyle project
  ->build steps   ->echo Hello World!(script)
  ->save and apply
  ->check in dashboard
  ->build now (run)
  ->status
  ->console output(Shows success)

 

# Jenkins and Security
->Controller isolation : each build must be isolated from one another
->User Interface:(default)-->CSRF protection,Markup formatter,Rendered user content

 

# Securing Jenkins Environment
->Manage jenkins
...Making local computer as controller and send instructions so that other computers and run and create builds on them(Controller isolation)--(Inadvisable for long run)
->Manage nodes and clouds
->New node
->Permanent Agent
->Launch method --via ssh--127.0.0.1(optional)
Access Controls
->Manage jenkins
->create user 
->right click and configure

 

 

# Jenkins Build Distribution
..Adding extra machines as needed
..Absorbing extra load dynamically
->Primary/Secondary Architecture
    ..primary deals with actual software computer/server where jenkins installed
    ..secondary doing all work for build distributions(Workers)-->Take instructions from primary node
->Secondary Agent
   Doesnt contains any jenkins software
   Get info from primary node
->Why needed?
..less latency,fault tolerance,availability,Scalability,Efficiency,durability

 

 

# Distributed Jenkin Builds
..Uses agent
->Connecting to agent
     ->Manage jenkins
    ...Making local computer as controller and send instructions so that other computers and run and create builds on them(Controller isolation)--(Inadvisable for long run)
    ->Manage nodes and clouds
    ->New node
    ->Permanent Agent
    ->Launch Method via ssh
      ->paste ec2 instance from aws
      ->add credentials
        username with private key
        in key copy and paste ssh key
      ->credentials ..elias
# Jenkins Fingerprints and Artifacts 
  ->File version---Tracking files is done using fingerprinting
  ->Dependency version
  How to do
  ->Record fingerprits jar files
  ->Record everything
  How fingerprints work
  ->MD5 checksum
  ->Jenkins maintained database

 

 

  How to Record Fingerprints
  ->Click 'Configure'
  ->Scroll to post-build actions
  ->Select record fingerprint of files

 

 

  Test and Artifacts
  ->Jenkins help by recording aggregate test results

 

 

  Recording and Tests and Artifacts
  ->Using Junit or Plugins

 

# Managing Jenkins Fingerprints and Artifacts 
  ->Create build
  ->In Add post-build actions
    ..Select Record fingerprints
    ..*.py(All python fingerprints will be fingerprinted)

 

 

#
..name of the syntax used to describe periodic builds---CronJob
..node by default runs the build--Built-in  
