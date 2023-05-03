# Google Cloud Exercises, Quizzes and Notes

## Section 2

Now, let’s do an exercise to change the pinned objects. Scroll down to BigQuery in the Big Data section of the Navigation menu and pin it. Then pin Cloud Dataproc. Verify that both appear at the top of the navigation window.

Find Dataproc, click on the pushpin icon and then find BigQuery, click on the pushpin icon. And then we’ll scroll up, and see that both appear at the top of the navigation menu. And now we can turn off the pinning, too.

![Exercises 2_14_1.png](Section%202%2FExercises%202_14_1.png)

### Quiz

![Quiz Section 2.png](Section%202%2FQuiz%20Section%202.png)

## Section 3

    cat README-cloudshell.txt

![catCommand.png](Section%203%2FcatCommand.png)

### Code Editor

![Helloworldfile.png](Section%203%2FHelloworldfile.png)

Run the file

![HelloworldRun.png](Section%203%2FHelloworldRun.png)


### Cloud SDK

There are two main commands

1. gsutil - Working with storage
2. gcloud - Other Services

Other - These are less important for the exam

1. bq - Big Query
2. cbt - Big Table

gcloud is seperated into groups like:

1. compute
2. sql
3. dns

using this code you can access cloud instances and manipulate them.

Example:

        gcloud compute instances list


![gcloudcomputelist.png](Section%203%2Fgcloudcomputelist.png)


For help just type an incomplete command

        gcloud compute instances

![gcloudcomputeerror.png](Section%203%2Fgcloudcomputeerror.png)

the Same two options for gsutil

![gsutil.png](Section%203%2Fgsutil.png)

### Exercise 3.18

Let’s start a cloud console if you don’t have one open already and let’s clear the screen and adjust the size. Now for this exercise, use the gcloud command to list instances. Enter the command:

        gcloud compute instances list

![gcloudcomputelist.png](Section%203%2Fgcloudcomputelist.png)

An important thing to know about buckets is that their names are globally unique. Since I have a bucket called ace-cloud-engineer-bucket-1 that means you can’t use that name. Instead, use the gsutil command to create a bucket called ace-cloud-engineer-bucket-<some random number>. Use the help command with both gcloud and gsutil to get more information about each command. 

![testbucket.png](Section%203%2Ftestbucket.png)

Get a list of commands you can use with gsutil. To get a list of commands, use gsutil help.

![gsutil help.png](Section%203%2Fgsutil%20help.png)

## Section 5

### Quiz

![Quiz Section5.png](Section%205%2FQuiz%20Section5.png)

## Section 6

### Quiz

![QuizSection6.png](Section%206%2FQuizSection6.png)

## Section 7

### Exercise: Create a virtual Machine

You can create a new VM instance under VM instances with the GUI:

![CreatenewInstance.png](Section%207%2FCreatenewInstance.png)

Or with the cloud shell running

        gcloud compute instances create test_april_vm

Extra options included:

        gcloud compute instances create testaprilvm --zone=us-west1-c \
        --machine-type=g1-small --boot-disk-size=10gb

![CreateCommand.png](Section%207%2FCreateCommand.png)

Resulting in:

![resultingVM's.png](Section%207%2FresultingVM%27s.png)


### Local CLI installation

Google cloud SDK can be isntalled locally from here: 

https://cloud.google.com/sdk/docs/install

![localinstall.png](Section%207%2Flocalinstall.png)

![shellresult.png](Section%207%2Fshellresult.png)

### Access a vm

Press the ssh or rdp button on the vm GUI page

![access.png](Section%207%2Faccess.png)


## Section 8

### Exercise: Create a Preemptible VM

You do this under 

    Create VM --> 
    Advanced Options --> 
    Management --> 
    Availability Policies --> 
    Spot

![createpreemtible.png](Section%208%2Fcreatepreemtible.png)

![spotvm.png](Section%208%2Fspotvm.png)

## Section 9

### Exercise: Create an Instance Group

![Create Instance Group.png](Section%209%2FCreate%20Instance%20Group.png)

Result

![instancegroup.png](Section%209%2Finstancegroup.png)


## Section 10 

### Exercise 1 Create a cluster

Create kubernetes cluster using cloud shell
I did this locally instead of the cloud console (due to speed considerations)

    gcloud container clusters create test-cluster-1 --zone=us-west1-c --machine-type=n1-standard-1 --disk-size=10gb

Initial error to enable API:

![APIerror.png](Section%2010%2FAPIerror.png)

Completed Command:

![CompletedCluster.png](Section%2010%2FCompletedCluster.png)

Details:




### Exercise 2 Create a workload

First go to the workload overview in kubernetes

Pick a premade workload container (NGINX):

![step1.png](Section%2010%2Fstep1.png)

view Yaml:

![yaml.png](Section%2010%2Fyaml.png)

Set options:

![step2.png](Section%2010%2Fstep2.png)

Deploy:

![deploy.png](Section%2010%2Fdeploy.png)

![workloaddetails.png](Section%2010%2Fworkloaddetails.png)

### Quiz 4

![quiz4.png](Section%2010%2Fquiz4.png)

## Section 11

This section talks about stackdriver however since 2020 this has been renamed to:
Google cloud operations

### Exercise: Monitoring

Check if monitoring is on:

![monitoring on.png](Section%2011%2Fmonitoring%20on.png)

Go to monitoring in Google Cloud

![monitoringdashboard.png](Section%2011%2Fmonitoringdashboard.png)

### Quiz 5

![Quiz.png](Section%2011%2FQuiz.png)


## Section 12

### Exercise: Deploying an app to app Engine

For this we will use the cloud SDK locally

Due to me doing the assignment locally i will have to use windows CMD commands over linux
Think of dir vs ls

1. Check if python is up to date

        gcloud components install app-engine-python

![updateappenginepython.png](Section%2012%2Fupdateappenginepython.png)

2. Get the correct python Docs

         git clone https://github.com/GoogleCloudPlatform/python-docs-samples


![gitclone.png](Section%2012%2Fgitclone.png)

3. Check folder
   
         cd python-docs-samples
         cd appengine
         cd standard
         cd hello_world
         dir
         
![clone.png](Section%2012%2Fclone.png)


4. Deploy 

         gcloud app deploy app.yaml

![deploy.png](Section%2012%2Fdeploy.png)

5. Check the output

         gcloud app browse

![output.png](Section%2012%2Foutput.png)

### Quiz 6

![quiz.png](Section%2012%2Fquiz.png)


## Section 13

### Exercise Creating a cloud function

Create a function with unauthenticated invocations

![setup.png](Section%2013%2Fsetup.png)

Create a function in a chosen language

![codeeditor.png](Section%2013%2Fcodeeditor.png)

Deploy

### Exercise Creating a cloud Pubsub function

Steps are the same except for channging from http to cloud pub/sub

An additional step is creating a topic:

![createtopic.png](Section%2013%2Fcreatetopic.png)

And after deployment both functions look like this:

![functionresult.png](Section%2013%2Ffunctionresult.png)


### Exercise Deploy a cloud function with SDK

Create a python script

![pythonscript.png](Section%2013%2Fpythonscript.png)

Create a zip file

      zip main.zip main.py

Create a bucket

      gcloud storage buckets create gs://exam-test-bucket-12312452 

upload to bucket

      gsutil cp main.zip gs://exam-test-bucket-12312452 

![bucket upload.png](Section%2013%2Fbucket%20upload.png)

Deploy function

      gcloud functions deploy hello_gcs --runtime=python311 \
      --trigger-resource=exam-test-bucket-12312452 \ 
      --trigger-event=google.storage.object.finalize \ 
      --source=gs://exam-test-bucket-12312452/main.zip

I actually ran into a user source code error but since the class is not about python 
as stated by the lecturer and I completed all the exercise steps I'll move on

![outcome.png](Section%2013%2Foutcome.png)


### Quiz 7 

![quiz.png](Section%2013%2Fquiz.png)


## Section 16

### Exercise Versioning and object life cycle management

Add a rule to a bucket;

![ruleui.png](Section%2016%2Fruleui.png)

Select action

![action.png](Section%2016%2Faction.png)

Select condition of action

![conditions.png](Section%2016%2Fconditions.png)

Deploy:

![deployed.png](Section%2016%2Fdeployed.png)

### Exercise entity management in datastore

Create an entity in datastore

![entitycreation.png](Section%2016%2Fentitycreation.png)

Data can be edited by editing properties

![editproperty.png](Section%2016%2Feditproperty.png)

Queries can be generated by google in their UI

![querybefore.png](Section%2016%2Fquerybefore.png)

And shows a result

![query after.png](Section%2016%2Fquery%20after.png)

Entities can have different properties because it is a NoSQL database

![different entity.png](Section%2016%2Fdifferent%20entity.png)

### Quiz

![quiz.png](Section%2016%2Fquiz.png)

## Section 18

### Exercise Setup G Sub/Pub

First create a topic

![createtopic.png](Section%2018%2Fcreatetopic.png)

Create a subscription to topic

![subscription.png](Section%2018%2Fsubscription.png)

Send Message to Topic

![test message.png](Section%2018%2Ftest%20message.png)

Then pull the message to receive it back

![Messagepull.png](Section%2018%2FMessagepull.png)

Using Ack message you acknowledge the message and it will be deleted

### Exercise Setup DataProc

Create a cluster

![clusternodes.png](Section%2018%2Fclusternodes.png)

Setup Nodes

![nodesetup.png](Section%2018%2Fnodesetup.png)

Deploy 

![deployedcluster.png](Section%2018%2Fdeployedcluster.png)

Then we can deploy a job to the cluster 

![job selection.png](Section%2018%2Fjob%20selection.png)

### Exercise Setup Dataflow

Create a job and select a template

![dataflowtemplates.png](Section%2018%2Fdataflowtemplates.png)

Put in Google word example
This bucket can be reached with an adress because the namespace is global

![jobfilledout.png](Section%2018%2Fjobfilledout.png)

Completed

![completedjob.png](Section%2018%2Fcompletedjob.png)

Result can be found in the bucket

![result.png](Section%2018%2Fresult.png)

### Quiz 9

![quiz.png](Section%2018%2Fquiz.png)


## Section 19 

### Exercise Create a VPC

![vpc create.png](Section%2019%2Fvpc%20create.png)

### Quiz 10 

![Quiz.png](Section%2019%2FQuiz.png)

## Section 20

### Exercise Setup a Load Balancer

First we need an instance group in compute engine

![instancegroup.png](Section%2020%2Finstancegroup.png)


Then we go to network services for the load balancer
We have to reserve a subnet

![subnet.png](Section%2020%2Fsubnet.png)

And do the backend config

![create backend.png](Section%2020%2Fcreate%20backend.png)

and the front end config

![frontend.png](Section%2020%2Ffrontend.png)

## Section 23

### Quiz 11

![Quiz.png](Section%2023%2FQuiz.png)



