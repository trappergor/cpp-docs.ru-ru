---
title: Функции-члены потока ввода
ms.date: 07/19/2019
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
ms.openlocfilehash: 8aa211a03bb6e9b1d910db360066b4a2ca76571a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233175"
---
# <a name="input-stream-member-functions"></a>Функции-члены потока ввода

Функции — члены потока ввода используются для дисковых операций ввода.

## <a name="open"></a><a name="vclrftheopenfunctionforinputstreamsanchor11"></a>открыт

Если используется входной поток файлов ( `ifstream` ), необходимо связать этот поток с конкретным файлом диска. Это можно сделать в конструкторе или можно использовать `open` функцию. В любом случае аргументы одни и те же.

При открытии файла, связанного с входным потоком, обычно указывается флаг [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) (режим по умолчанию — `ios::in` ). Список `openmode` флагов см. в разделе [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode). Флаги могут быть объединены с помощью побитового оператора OR (&#124;).

Чтобы прочитать файл, сначала используйте функцию- `fail` член, чтобы определить, существует ли она:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="get"></a><a name="vclrfthegetfunctionanchor12"></a>Получить

Неформатированная `get` функция элемента работает как `>>` оператор с двумя исключениями. Во-первых, `get` функция включает пробелы, в то время как средство извлечения исключает пробелы при `skipws` установке флага (по умолчанию). Во-вторых, эта `get` функция менее вероятно приведет к тому, что связанный поток вывода ( `cout` например,) будет сброшен.

Вариант `get` функции указывает адрес буфера и максимальное число считываемых символов. Это полезно для ограничения количества символов, отправленных в конкретную переменную, как показано в примере:

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

### <a name="sample-output"></a>Пример выходных данных

```Output
1234
```

## <a name="getline"></a><a name="vclrfthegetlinefunctionanchor13"></a>getline

`getline`Функция-член аналогична `get` функции. Обе функции допускают третий аргумент, который указывает завершающий символ для входных данных. Значение по умолчанию — символ новой строки. Обе функции резервируют один символ для необходимого завершающего символа. Однако `get` оставляет завершающий символ в потоке и `getline` удаляет завершающий символ.

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

## <a name="read"></a><a name="vclrfthereadfunctionanchor14"></a>Просмотр

`read`Функция-член считывает байты из файла в указанную область памяти. Аргумент length определяет количество прочтенных байтов. Если этот аргумент не указан, чтение останавливается при достижении физического конца файла или, в случае файла в текстовом режиме, при чтении встроенного символа `EOF`.

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

Программа предполагает, что записи данных форматируются точно так же, как указано в структуре, без завершающего возврата каретки или символов перевода строки.

## <a name="seekg-and-tellg"></a><a name="vclrftheseekgandtellgfunctionsanchor7"></a>функции seekg и tellg

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

Чтобы использовать `seekg` для реализации систем управления данными, ориентированных на записи, умножьте размер записи фиксированной длины на номер записи, чтобы получить координату байта относительно конца файла, а затем используйте `get` объект для чтения записи.

Функция-член `tellg` возвращает текущую позицию в файле для чтения. Это значение имеет тип `streampos` , **`typedef`** определенный в \<iostream> . В следующем примере выполняется чтение файла и показ сообщения с позициями пробелов.

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

## <a name="close"></a><a name="vclrftheclosefunctionforinputstreamsanchor15"></a>выхода

`close`Функция члена закрывает файл диска, связанный с входным файлом потока, и освобождает файл операционной системы. [`ifstream`](../standard-library/basic-ifstream-class.md)Деструктор закрывает файл, но функцию можно использовать, `close` Если необходимо открыть другой файл для того же объекта потока.

## <a name="see-also"></a>См. также статью

[Входные потоки](../standard-library/input-streams.md)
