---
title: Функции-члены потока ввода
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
ms.openlocfilehash: b046ea1995d5a8eaa39dced9feb7a5e4c422c253
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663987"
---
# <a name="input-stream-member-functions"></a>Функции-члены потока ввода

Функции — члены потока ввода используются для дисковых операций ввода. К этим функциям относятся:

- [Функция open для потоков ввода](#vclrftheopenfunctionforinputstreamsanchor11)

- [Get](#vclrfthegetfunctionanchor12)

- [Getline](#vclrfthegetlinefunctionanchor13)

- [Свойство для чтения](#vclrfthereadfunctionanchor14)

- [Функции seekg и tellg](#vclrftheseekgandtellgfunctionsanchor7)

- [Функция close для потоков ввода](#vclrftheclosefunctionforinputstreamsanchor15)

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Функция open для потоков ввода

При использовании входного файлового потока (ifstream) этот поток необходимо связать с конкретным файлом на диске. Это можно сделать в конструкторе, или воспользоваться `open` функции. В любом случае аргументы одни и те же.

Обычно указывается [ios_base::openmode](../standard-library/ios-base-class.md#openmode) флаг при открытии файла, связанного с потоком ввода (режим по умолчанию — `ios::in`). Список `open_mode` флаги, см. в разделе [открытия](#vclrftheopenfunctionforinputstreamsanchor11). Флаги могут быть объединены с помощью побитового оператора OR (&#124;).

Чтобы прочитать файл, сначала используйте `fail` определить, существует ли функция-член:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a> Get

Неформатированная `get` функция-член работает подобно `>>` оператора с двумя исключениями. Во-первых, `get` функция включает в себя знаки пробела, а извлечения исключает пробелы при `skipws` флаг установлен (по умолчанию). Во-вторых, `get` функция меньшей вероятностью вызовет потока вывода (`cout`, например) были записаны на диск.

Разновидность `get` функция указывает адрес буфера и максимальное число символов для чтения. Это полезно для ограничения количества символов, отправленных в конкретную переменную, как показано в примере:

```cpp
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

### <a name="input"></a>Входные данные

```Input
1234
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
1234
```

## <a name="vclrfthegetlinefunctionanchor13"></a> Getline

`getline` Функция-член аналогична `get` функции. Обе функции допускают третий аргумент, который указывает завершающий символ для входных данных. Значение по умолчанию — символ новой строки. Обе функции резервируют один символ для необходимого завершающего символа. Тем не менее `get` оставляет завершающий символ в потоке и `getline` Удаляет завершающий символ.

В следующем примере задается завершающий символ для потока ввода:

```cpp
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

### <a name="input"></a>Входные данные

```Input
test
```

## <a name="vclrfthereadfunctionanchor14"></a> Свойство для чтения

`read` Функция-член считывает байт из файла в указанную область памяти. Аргумент length определяет количество прочтенных байтов. Если этот аргумент не указан, чтение останавливается при достижении физического конца файла или, в случае файла в текстовом режиме, при чтении встроенного символа `EOF`.

Этот пример считывает двоичную запись из файла заработной платы в структуру:

```cpp
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

Программа предполагает, что записи данных имеют формат, точно как указано в структуре, без завершающих символов возврата каретки или перевода строки.

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Функции seekg и tellg

Потоки входного файла хранят внутренний указатель на позицию в файле, с которой будет продолжаться чтение. Этот указатель можно установить функцией `seekg`, как показано ниже:

```cpp
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

Чтобы использовать `seekg` для реализации систем управления данными на базе записей, умножьте размер записи фиксированной длины на номер записи, чтобы получить позицию байта относительно конца файла, а затем используйте `get` объект для чтения записи.

Функция-член `tellg` возвращает текущую позицию в файле для чтения. Это значение имеет тип `streampos`, `typedef`, определенное в \<iostream>. В следующем примере выполняется чтение файла и показ сообщения с позициями пробелов.

```cpp
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

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Функция close для потоков ввода

`close` Функция-член закрывает дисковый файл, связанный с входным файловым потоком и освобождает дескриптор файла операционной системы. [Ifstream](../standard-library/basic-ifstream-class.md) деструктор закрывает файл, но можно использовать `close` работать, если вам нужно открыть другой файл для одного объекта stream.

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
