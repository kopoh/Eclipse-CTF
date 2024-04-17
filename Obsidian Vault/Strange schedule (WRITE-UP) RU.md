Решение 1 (JADX)
Для начала скачиваем JADX 
После этого открываем прилагаемый к таску APK файл
И исследуем структуру проекта

Зачастую всё что нужно хранится в package ID в нашем случае это com -> KopohGames.Scheduler (com.KopohGames.Scheduler)
![[Pasted image 20240417232035.png]]
Изучая приложение мы находим файл TeacherLoginScreen
Находим в нем его ViewModel с названием TeacherLoginViewModel
![[Pasted image 20240417232443.png]]
Видим обращение к файлу TeacherRepository
Дальше кликая по методу ==teacherLogin(login, password)== получаем ссылку на этот метод в котором спрятаны значения для входа
![[Pasted image 20240417232840.png]]
Перейдя в метод мы видим условное выражение if(login == "eclipse" && password == "eclipse")

Далее входим в приложение предварительно поставив в телефоне (эмуляторе) дату начала Redshift (18.12.2023)
![[Screenshot_2023-12-18-00-05-41-276_com.android.settings-edit.jpg]]
![[Screenshot_2023_12_18_00_08_04_356_com_KopohGames_Scheduler_androidApp.jpg]]


И по условию смотрим на страничку настроек где видим подсказку (что надо найти её в дискорде у пользователя kopoh)
![[Screenshot_2023_12_18_00_06_42_529_com_KopohGames_Scheduler_androidApp.jpg]]

Или же на этапе исследования проекта найти картинку которая закопана глубоко в файлах
![[Pasted image 20240418000208.png]]

и флаг это 
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![[Pasted image 20240418001354.png]]

Решение 2 (BRUTFORCE)

Пробрутить значения email и password  :D

Решение 3 (IDA)

Открываем APK файл в ida64 как APK
![[Pasted image 20240418001155.png]]

Дальше используем Strings для того чтобы собрать все строки в коде
![[Pasted image 20240418001858.png]]
После этого ищем (поле/строку email или eclipse)
![[Pasted image 20240418001908.png]]
В итоге выходим на блок кода с условием if(email == "eclipse")
![[Pasted image 20240418001819.png]]

Далее вход в приложение с датой начала eclipse и поиск флага в дискорде
![[Screenshot_2023-12-18-00-05-41-276_com.android.settings-edit.jpg]]![[Screenshot_2023_12_18_00_08_04_356_com_KopohGames_Scheduler_androidApp.jpg]]

![[Screenshot_2023_12_18_00_06_42_529_com_KopohGames_Scheduler_androidApp.jpg]]

And the flag is
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![[Pasted image 20240418001354.png]]