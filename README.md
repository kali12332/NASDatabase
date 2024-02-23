Проект представляет собой open-source библиотеку, написанную на языке программирования C#, с целью упростить разработку приложений, требующих работы с различными объемами данных. Проект направлен на создание хорошего фундамента для разработки программ под разные задачи: от создания СУБД до работы с данными в среде CosmosOS. Для этого было разработано достаточное количество интерфейсов взаимодействия между объектами и модулей, поддерживающих их. Проект не является коммерческим и был создан для обучения.

Далее в [документиации](https://docs.google.com/document/d/1ekIoIGqzT_iCoHpOobplHOc7ajQwUDz_D_OkgWtXOpo/edit?usp=sharing) будет представлен последовательный рассказ о элементах API с примерами кода, написанного на C# и Python. Вы сможете создать свою собственную базу данных, разработать бота в Discord и создать свой класс-наследник от DataBase. 

🛠️Вспомогательные библиотеки
* [System.Text.Json](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/how-to)
  
____
Пример создания базы:
```C#
 //C# 
 DataBaseManager DBM = new DataBaseManager();//Создание экземпляра DataBaseManager
 
 var DBS = new DataBaseSettings("Test", "D:\\");//Передаем настройки
 
 var DB = DBM.CreateDataBase(DBS);//Создаем проект и загружаем БД в память
```
____
  Пример загрузки:
```c#
var DBM = new DataBaseManager();

string path = "..\\..";//путь до проекта

DataBase DB = DBM.LoadDB(path);
```
___
  Пример работы с данными: 
```c#
DB.AddData("Some person", "18");//name | old

//Обращаемся к столбцу по номеру 0 ("name") и ищем номер строки с такими данными
int id = DB.GetIDByParams("0", "Some person");
              
//Удаляем все строку с данными по id
DB.RemoveDataByID(id);

//Заменяем " " на Tom-а, которому 15 лет
DB.SetData(0, "Tom", "15");

``` 
