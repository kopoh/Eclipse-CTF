Solution 1 (JADX)
To get started, download JADX 
After that, open the APK file attached to the task
And we will explore the structure of the project

Often all that is needed is stored in the package ID, in our case it is com -> KopohGames.Scheduler (com.KopohGames.Scheduler)
![[Pasted image 20240417232035.png]]
While studying the application, we find the TeacherLoginScreen file
We find his ViewModel in it with the name TeacherLoginViewModel
![[Pasted image 20240417232443.png]]
We see a reference to the TeacherRepository file
Then clicking on the method ==teacherLogin(login, password)== we get a link to this 
method in which the values for the login are hidden
![[Pasted image 20240417232840.png]]
Going to the method, we see the conditional expression if(login == "eclipse" && password == "eclipse")

Next, enter the application by pre-setting the start date of Redshift in the phone (emulator) (12/18/2023)
![[Screenshot_2023-12-18-00-05-41-276_com.android.settings-edit.jpg]]

![[Screenshot_2023_12_18_00_08_04_356_com_KopohGames_Scheduler_androidApp.jpg]]

And by convention, we look at the settings page where we see a hint (that we need to find it in the kopoh user's discord)
![[Screenshot_2023_12_18_00_06_42_529_com_KopohGames_Scheduler_androidApp.jpg]]


Or, at the research stage of the project, find an image that is buried deep in files
![[Pasted image 20240418000208.png]]
![[Pasted image 20240417235903.png]]

And the flag is
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![[Pasted image 20240418001354.png]]

Solution 2 (BRUTFORCE)

Brute email and password values :D

Solution 3 (IDA)

Opening the APK file in ida64 as APK
![[Pasted image 20240418001155.png]]

Next, we use Strings to collect all the strings in the code
![[Pasted image 20240418001858.png]]
After that, we search for (email or eclipse field/string)
![[Pasted image 20240418001908.png]]
As a result, we go to the code block with the if condition(email == "eclipse")
![[Pasted image 20240418001819.png]]

Next, log in to the application with the eclipse start date and search for the flag in the discord
![[Screenshot_2023-12-18-00-05-41-276_com.android.settings-edit.jpg]]![[Screenshot_2023_12_18_00_08_04_356_com_KopohGames_Scheduler_androidApp.jpg]]

![[Screenshot_2023_12_18_00_06_42_529_com_KopohGames_Scheduler_androidApp.jpg]]

And the flag is
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![[Pasted image 20240418001354.png]]