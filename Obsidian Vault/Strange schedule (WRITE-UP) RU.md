Решение 1 (JADX)
Для начала скачиваем JADX 
После этого открываем прилагаемый к таску APK файл
И исследуем структуру проекта

Зачастую всё что нужно хранится в package ID в нашем случае это com -> KopohGames.Scheduler (com.KopohGames.Scheduler)
![Assets/1.png](Assets/1.png)
Изучая приложение мы находим файл TeacherLoginScreen
Находим в нем его ViewModel с названием TeacherLoginViewModel
![Assets/2.png](Assets/2.png)
Видим обращение к файлу TeacherRepository
Дальше кликая по методу ==teacherLogin(login, password)== получаем ссылку на этот метод в котором спрятаны значения для входа
![Assets/3.png](Assets/3.png)
Перейдя в метод мы видим условное выражение if(login == "eclipse" && password == "eclipse")

Далее входим в приложение предварительно поставив в телефоне (эмуляторе) дату начала Redshift (18.12.2023)
![Assets/4.jpg](Assets/4.jpg)
![Assets/5.jpg](Assets/5.jpg)


И по условию смотрим на страничку настроек где видим подсказку (что надо найти её в дискорде у пользователя kopoh)
![Assets/6.jpg](Assets/6.jpg)

Или же на этапе исследования проекта найти картинку которая закопана глубоко в файлах
![Assets/7.png](Assets/7.png)
![Assets/8.png](Assets/8.png)

И флаг это 
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![Assets/9.png](Assets/9.png)

Решение 2 (BRUTFORCE)

Пробрутить значения email и password  :D

Решение 3 (IDA)

Открываем APK файл в ida64 как APK
![Assets/10.png](Assets/10.png)

Дальше используем Strings для того чтобы собрать все строки в коде
![Assets/11.png](Assets/11.png)
После этого ищем (поле/строку email или eclipse)
![Assets/12.png](Assets/12.png)
В итоге выходим на блок кода с условием if(email == "eclipse")
![Assets/13.png](Assets/13.png)

Далее вход в приложение с датой начала eclipse и поиск флага в дискорде
![Assets/4.jpg](Assets/4.jpg)![Assets/5.jpg](Assets/5.jpg)

![Assets/6.jpg](Assets/6.jpg)

И флаг это
```
eclipseCTF{k0po#_1S_U9V3R$}
```
![Assets/9.png](Assets/9.png)
