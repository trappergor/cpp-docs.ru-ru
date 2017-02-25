---
title: "Функции-члены потока ввода | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "объекты потока ввода"
  - "потоки ввода, функция-член"
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Функции-члены потока ввода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функции\-члены входного потока используются для ввода диска.  Функции\-члены включают:  
  
-   [Открытая функцию для входных потоков](#vclrftheopenfunctionforinputstreamsanchor11)  
  
-   [Функция получение](#vclrfthegetfunctionanchor12)  
  
-   [Функция getline](#vclrfthegetlinefunctionanchor13)  
  
-   [Функция прочесть](#vclrfthereadfunctionanchor14)  
  
-   [Функции seekg и tellg](#vclrftheseekgandtellgfunctionsanchor7)  
  
-   [Близкая функцию для входных потоков](#vclrftheclosefunctionforinputstreamsanchor15)  
  
##  <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Открытая функцию для входных потоков  
 При использовании файловый поток \(ifstream\), необходимо связать этот поток с определенным дисковым файлом.  Это можно сделать в конструкторе, или можно использовать функцию **open**.  В любом случае аргументы одинаково.  
  
 Обычно определяется флажок [ios\_base::openmode](../Topic/ios_base::openmode.md) при открытии файла, связанный с входным потоком \(режим по умолчанию **ios::in**\).  Для списка флажки **open\_mode** см. в разделе [Открытая функция](#vclrftheopenfunctionforinputstreamsanchor11).  Флажки можно объединять с побитовое ИЛИ \( &#124; оператор\).  
  
 Для считывания файла сначала используйте функции\-члена **Не пройдено**, чтобы определить, существует ли он:  
  
```  
istream ifile( "FILENAME" );  
if ( ifile.fail() )  
// The file does not exist ...  
```  
  
##  <a name="vclrfthegetfunctionanchor12"></a> Функция получение  
 Unformatted функцию\-член **get** работает так же, как и оператор **\>\>** с 2 исключениями.  Во\-первых, функция **get** содержит символы пробела, а экстрактор исключает пространство, если установлен флажок [skipws](../Topic/skipws.md) \(по умолчанию\).  Во\-вторых, функция **get**, скорее всего, не связанный поток вывода \(`cout`, например\), потопленным.  
  
 Вариант функции **get** указывает адрес буфера и максимальное количество символов для чтения.  Это полезно для ограничения количества символов, отправляемых в определенной переменной, как показано в следующем примере:  
  
```  
// ioo_get_function.cpp  
// compile with: /EHsc  
// Type up to 24 characters and a terminating character.   
// Any remaining characters can be extracted later.  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   char line[25];  
   cout << " Type a line terminated by carriage return\n>";  
   cin.get( line, 25 );  
   cout << line << endl;  
}  
```  
  
### Ввод  
  
```  
1234  
```  
  
### Пример результатов выполнения  
  
```  
1234  
```  
  
##  <a name="vclrfthegetlinefunctionanchor13"></a> Функция getline  
 Функцию\-член **getline** аналогична функции **get**.  Обе функции позволяют третий аргумент, определяющий конечный символ для ввода.  Значение по умолчанию — символ новой строки.  Обе функции резервируют один символ требуемого конечное символов.  Однако **get** оставляет конечный символ в поток и **getline** удаляет конечный символ.  
  
 В следующем примере определяется конечный символ для входного потока.  
  
```  
// getline_func.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char line[100];  
   cout << " Type a line terminated by 't'" << endl;  
   cin.getline( line, 100, 't' );  
   cout << line;  
}  
```  
  
### Ввод  
  
```  
test  
```  
  
##  <a name="vclrfthereadfunctionanchor14"></a> Функция прочесть  
 Функцию\-член **чтение** считывает байт из файла в определенной области памяти.  Аргумент длины определяет количество прочитанных байтов.  Если не указать этот аргумент, чтения останавливается при достижении конца физического файла или, в случае файла текст\- режиме, когда встроенный символ `EOF` читается.  
  
 В данном примере демонстрируется чтение бинарную запись из файла зарплаты в структуру:  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   struct  
   {  
      double salary;  
      char name[23];  
   } employee;  
  
   ifstream is( "payroll" );  
   if( is ) {  // ios::operator void*()  
      is.read( (char *) &employee, sizeof( employee ) );  
      cout << employee.name << ' ' << employee.salary << endl;  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 Программа высказывать записи данных форматируется точно, определенные структурой без выполнения символы возврата каретки и перевода строки.  
  
##  <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Функции seekg и tellg  
 Файловых потоков ввода хранит внутренний указатель на позиции в файле, в которой данные быть чтение далее.  Необходимо установить этот указатель с функцией `seekg`, как показано ниже:  
  
```  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)  
      while ( tfile.good() ) { // EOF or failure stops the reading  
         tfile.get( ch );  
         if( !ch ) break;      // quit on null  
         cout << ch;  
      }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 Для использования `seekg` реализовать ориентированные на запись системы управления данными, умножение размер фиксированной длины записи регистрировать числом для получения байтовую положение относительно конец файла, а затем использовать объект **get** для чтения записи.  
  
 Функция\-член `tellg` возвращает позицию текущего файла для чтения.  Значение типа `streampos`, `typedef` указанного недопустимо \<iostream\>.  В следующем примере считывается файл и отображает сообщения, указывающее позицию пробелов.  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
       while ( tfile.good( ) ) {  
          streampos here = tfile.tellg();  
          tfile.get( ch );  
          if ( ch == ' ' )  
             cout << "\nPosition " << here << " is a space";  
       }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
##  <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Близкая функцию для входных потоков  
 Функцию\-член **закрыть** закрывает дисковый файл, связанный с файловыми потоком ввода и освобождает дескриптор файла операционной системы.  Деструктор [ifstream](../standard-library/basic-ifstream-class.md) закрывает файл автоматически, но можно использовать функцию **закрыть**, если необходимо открыть другой файл для объекта того же самого потока.  
  
## См. также  
 [Потоки ввода](../standard-library/input-streams.md)