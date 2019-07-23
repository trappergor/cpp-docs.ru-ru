---
title: Функции-члены потока ввода
ms.date: 07/19/2019
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
ms.openlocfilehash: 3b028090c9b91c7f0dde195243a5d2daef55fbbc
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376246"
---
# <a name="input-stream-member-functions"></a>Функции-члены потока ввода

Функции — члены потока ввода используются для дисковых операций ввода.

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a>открыт

Если используется входной поток файлов (`ifstream`), необходимо связать этот поток с конкретным файлом диска. Это можно сделать в конструкторе или можно использовать `open` функцию. В любом случае аргументы одни и те же.

При открытии файла, связанного с входным потоком, обычно указывается флаг [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) (режим по умолчанию — `ios::in`). Список `openmode` флагов см. в разделе [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode). Флаги могут быть объединены с помощью побитового оператора OR (&#124;).

Чтобы прочитать файл, сначала используйте `fail` функцию-член, чтобы определить, существует ли она:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a>Получить

Неформатированная `get` функция элемента работает `>>` как оператор с двумя исключениями. Во-первых `get` , функция включает пробелы, в то время как средство извлечения исключает пробелы при установке флага(поумолчанию).`skipws` Во-вторых `get` , эта функция менее вероятно приведет к тому, что связанный`cout`поток вывода (например,) будет сброшен.

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

### <a name="input"></a>Ввод

```Input
1234
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
1234
```

## <a name="vclrfthegetlinefunctionanchor13"></a>getline

`get` Функция- `getline` член аналогична функции. Обе функции допускают третий аргумент, который указывает завершающий символ для входных данных. Значение по умолчанию — символ новой строки. Обе функции резервируют один символ для необходимого завершающего символа. Однако оставляет завершающий символ в потоке и `getline` Удаляет завершающий символ. `get`

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

### <a name="input"></a>Ввод

```Input
test
```

## <a name="vclrfthereadfunctionanchor14"></a>Просмотр

Функция `read` -член считывает байты из файла в указанную область памяти. Аргумент length определяет количество прочтенных байтов. Если этот аргумент не указан, чтение останавливается при достижении физического конца файла или, в случае файла в текстовом режиме, при чтении встроенного символа `EOF`.

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

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a>функции seekg и tellg

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

Чтобы использовать `seekg` для реализации систем управления данными, ориентированных на записи, умножьте размер записи фиксированной длины на номер записи, чтобы получить координату байта относительно конца файла, а затем `get` используйте объект для чтения записи.

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

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a>выхода

Функция `close` члена закрывает файл диска, связанный с входным файлом потока, и освобождает файл операционной системы. Деструктор закрывает файл, но `close` функцию можно использовать, если необходимо открыть другой файл для того же объекта потока. [`ifstream`](../standard-library/basic-ifstream-class.md)

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
