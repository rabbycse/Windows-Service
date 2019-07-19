# Windows-Service
Let's create a Windows Service in C# using Visual Studio. 
## Step 1
Open Visual Studio, go to File > New and select Project. Now select new project from Dialog box and select “Window Service” and click on OK button.

![image001](https://user-images.githubusercontent.com/37344605/61525900-28741780-aa3b-11e9-83ee-f93918ba1ea5.png)

## Step 2

Go to Visual C# -> ”Windows Desktop” -> ”Windows Service” and give an appropriate name and then click OK
![image002](https://user-images.githubusercontent.com/37344605/61525953-46417c80-aa3b-11e9-88ef-8da3d5697fdd.png)

Once you click OK button the below screen will appear, which is your service

![image003](https://user-images.githubusercontent.com/37344605/61526011-65400e80-aa3b-11e9-9d07-f05e67a3fcb5.png)

## Step 3

Right click on the blank area and select “Add Installer”
 
### How to Add an Installer to a Windows Service
 
Before you can run a Windows Service, you need to install the Installer, which registers it with the Service Control Manager.

![image004](https://user-images.githubusercontent.com/37344605/61526094-91f42600-aa3b-11e9-8e4d-230c10bdc950.png)

After Adding Installer, ProjectInstaller will add in your project and ProjectInstakker.cs file will be open. Don’t forgot to save everything (by pressing ctrl + shift + s key)

![image005](https://user-images.githubusercontent.com/37344605/61526144-aafcd700-aa3b-11e9-9e81-f0d0cee0bfc9.png)

Solution Explore looks like this:

![image006](https://user-images.githubusercontent.com/37344605/61526183-bcde7a00-aa3b-11e9-80b7-ecb7a5579f44.png)

## Step 4

Right click on blank area and select “View Code”

![image007](https://user-images.githubusercontent.com/37344605/61526214-d4b5fe00-aa3b-11e9-8018-0f4c682595d3.png)

## Step 5

Its has Construtor which contains InitializeComponent method:
 
The InitializeComponent method contains the logic which create and initializes the user interface objects dragged on the form surface and provided the Property Grid of Form Designer.
 
Very important: Don't ever try to call any method before the call of InitializeComponent method.

![image008](https://user-images.githubusercontent.com/37344605/61526269-ee574580-aa3b-11e9-9531-c1da1848badd.png)

## Step 6

Select InitializeComponent method and press F12 key to go definition

![image009](https://user-images.githubusercontent.com/37344605/61526304-04650600-aa3c-11e9-9877-a589aafa8a6f.png)

## Step 7

Now add the below line:
 
this.serviceProcessInstaller1.Account = System.ServiceProcess.ServiceAccount.LocalSystem;
 
You also can add description and display service name (optionally).

```cpp
this.serviceInstaller1.Description = "My First Service demo";  
this.serviceInstaller1.DisplayName = "MyFirstService.Demo";
```

![image010](https://user-images.githubusercontent.com/37344605/61526437-3bd3b280-aa3c-11e9-92d3-b5d8aceb587e.png)

## Step 8

In this step, we will implement a timer, and code to call the service at a given time. We will create a text file and write current time in the text file using the service.

![image010](https://user-images.githubusercontent.com/37344605/61526437-3bd3b280-aa3c-11e9-92d3-b5d8aceb587e.png)

## Step 9. Rebuild your application.
 
Right click on your project or solution and select Rebuild.

![image011](https://user-images.githubusercontent.com/37344605/61526665-a84eb180-aa3c-11e9-9d35-64ff74a70991.png)

## Step 10

Search “command Prompt” and run as administrator

![image012](https://user-images.githubusercontent.com/37344605/61526832-07acc180-aa3d-11e9-9f27-86c946391905.png)

## Step 11

Fire the below command in the command prompt and press ENTER.
 
cd C:\Windows\Microsoft.NET\Framework\v4.0.30319 

![image013](https://user-images.githubusercontent.com/37344605/61526884-1b582800-aa3d-11e9-9cef-7e785bd871f6.png)

## Step 12

Now Go to your project source folder > bin > Debug and copy the full path of your Windows Service exe file.

![image014](https://user-images.githubusercontent.com/37344605/61526934-30cd5200-aa3d-11e9-8d1a-38788fed7885.png)

![image015](https://user-images.githubusercontent.com/37344605/61526968-3cb91400-aa3d-11e9-8a8f-cd059e732567.png)

## Installing a Windows Service

Open command prompt and fire the below command and press ENTER.
 
## Syntax

InstallUtil.exe + Your copied path + \your service name + .exe
 
## Our path

InstallUtil.exe C:\Users\source\repos\MyFirstService\MyFirstService\bin\Debug\MyFirstService.exe

![image016](https://user-images.githubusercontent.com/37344605/61527087-8275dc80-aa3d-11e9-904c-f2313ada8334.png)

## Check status of a Windows Service

Open services by following the below steps:
1. Press Window key + R.
2. Type services.msc
3. Find your Service.

![image017](https://user-images.githubusercontent.com/37344605/61527139-9cafba80-aa3d-11e9-867f-cfa8e8570fd7.png)

![image018](https://user-images.githubusercontent.com/37344605/61527148-9faaab00-aa3d-11e9-8040-07f6eecfa6ce.png)

You may notice that the Windows service is running.

![image019](https://user-images.githubusercontent.com/37344605/61527258-d385d080-aa3d-11e9-8526-72d9a82da56a.png)

## Check Windows Service Output 
 
The service will create a text file with the following text in it. 

Log folder will be created in your bin folder.
