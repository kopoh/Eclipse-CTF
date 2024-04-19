Solution 1 (JADX)
To get started, download JADX 
After that, open the APK file attached to the task
And we will explore the structure of the project

Often all that is needed is stored in the package ID, in our case it is com -> KopohGames.Scheduler (com.KopohGames.Scheduler)
![[Assets/1.png]]
While studying the application, we find the TeacherLoginScreen file
We find his ViewModel in it with the name TeacherLoginViewModel
![[Assets/2.png]]
We see a reference to the TeacherRepository file
Then clicking on the method ==teacherLogin(login, password)== we get a link to this 
method in which the values for the login are hidden
![[Assets/3.png]]
Going to the method, we see the conditional expression if(login == "eclipse" && password == "eclipse")

Next, enter the application by pre-setting the start date of Redshift in the phone (emulator) (12/18/2023)
![[Assets/4.jpg]]

![[Assets/5.jpg]]

And by convention, we look at the settings page where we see a hint (that we need to find it in the kopoh user's discord)
![[Assets/6.jpg]]


Or, at the research stage of the project, find an image that is buried deep in files
![[Assets/7.png]]
![[Assets/8.png]]

And the flag is
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![[Assets/9.png]]

Solution 2 (BRUTFORCE)

Brute email and password values :D

Solution 3 (IDA)

Opening the APK file in ida64 as APK
![[Assets/10.png]]

Next, we use Strings to collect all the strings in the code
![[Assets/11.png]]
After that, we search for (email or eclipse field/string)
![[Assets/12.png]]
As a result, we go to the code block with the if condition(email == "eclipse")
![[Assets/13.png]]

Next, log in to the application with the eclipse start date and search for the flag in the discord
![[Assets/4.jpg]]![[Assets/5.jpg]]

![[Assets/6.jpg]]

And the flag is
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![[Assets/9.png]]