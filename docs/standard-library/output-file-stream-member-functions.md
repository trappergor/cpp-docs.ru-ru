---
title: Функции-члены потока выходного файла
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: f20ed4e238d23211a6eeec4a3091daeb4d02a9b3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217679"
---
# <a name="output-file-stream-member-functions"></a>Функции-члены потока выходного файла

Функции-члены потока вывода делятся на три типа: эквивалентные манипуляторам, выполняющие неформатированные операции записи и изменяющие состояние потока другим образом и при этом не имеющие эквивалентных манипуляторов или операторов вставки. Для последовательного форматированного вывода можно использовать только операторы вставки и манипуляторы. Для двоичного дискового вывода с произвольным доступом следует использовать другие функции-члены с операторами вставки или без них.

## <a name="the-open-function-for-output-streams"></a>Функция open для потоков вывода

Чтобы использовать выходной поток файлов ([ofstream](../standard-library/basic-ofstream-class.md)), необходимо связать этот поток с конкретным дисковым файлом в конструкторе или `open` функции. При использовании `open` функции можно повторно использовать один и тот же объект потока с серией файлов. В любом случае аргументы, описывающие файл, одни и те же.

При открытии файла, связанного с выходным потоком, обычно указывается `open_mode` флаг. Эти флаги, определенные как перечислители в классе `ios`, можно комбинировать с помощью побитового оператора OR (&#124;). Список перечислителей приведен в разделе [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

Три типовые ситуации для потока вывода используют параметры режима:

- Создание файла. Если файл уже существует, старая версия удаляется.

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- Добавление записей к существующему файлу или создание нового, если он не существует.

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- Открытие двух файлов в одном и том же потоке, по одному за раз.

   ```cpp
   ofstream ofile();
   ofile.open("FILE1", ios::in);
   // Do some output
   ofile.close();    // FILE1 closed
   ofile.open("FILE2", ios::in);
   // Do some more output
   ofile.close();    // FILE2 closed
   // When ofile goes out of scope it is destroyed.
   ```

## <a name="the-put"></a>Размещение

Функция **put** записывает в поток вывода один символ. Следующие две конструкции по умолчанию одинаковы, но вторая зависит от аргументов формата потока:

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>Запись

`write`Функция записывает блок памяти в поток выходных файлов. Аргумент length указывает количество записанных байт. Следующий пример создает файловый поток вывода и записывает в него двоичное значение структуры `Date`:

```cpp
// write_function.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;

struct Date
{
   int mo, da, yr;
};

int main( )
{
   Date dt = { 6, 10, 92 };
   ofstream tfile( "date.dat" , ios::binary );
   tfile.write( (char *) &dt, sizeof dt );
}
```

`write`Функция не останавливается при достижении символа null, поэтому записывается полная структура класса. Функция принимает два аргумента: **`char`** указатель и число символов для записи. Обратите внимание на обязательное приведение до **`char`** <strong>\*</strong> адреса объекта структуры.

## <a name="the-seekp-and-tellp-functions"></a>Функции seekp и tellp

Файловый поток вывода хранит внутренний указатель на позицию следующей записи данных. Функция-член `seekp` устанавливает этот указатель, предоставляя тем самым вывод произвольного доступа в дисковый файл. Функция-член `tellp` возвращает позицию в файле. Примеры использования эквивалентов входного потока для `seekp` и `tellp` см. в разделе [Функции seekg и tellg](../standard-library/input-stream-member-functions.md).

## <a name="the-close-function-for-output-streams"></a>Функция close для потоков вывода

`close`Функция члена закрывает файл диска, связанный с выходным потоком файлов. Для завершения всех операций вывода на диск файл должен быть закрыт. При необходимости `ofstream` деструктор закрывает файл, но функцию можно использовать, `close` Если необходимо открыть другой файл для того же объекта потока.

Деструктор потока вывода автоматически закрывает файл потока только в том случае, если этот файл открыт конструктором или `open` функцией-членом. Если конструктору передается дескриптор файла для уже открытого файла или используется `attach` функция-член, необходимо закрыть файл явным образом.

## <a name="error-processing-functions"></a><a name="vclrferrorprocessingfunctionsanchor10"></a> Функции обработки ошибок

Используйте эти функции-члены для проверки на ошибки при записи в поток:

|Компонент|Возвращаемое значение|
|--------------|------------------|
|[Неправильное значение](basic-ios-class.md#bad)|Возвращает, если произошла **`true`** Неустранимая ошибка.|
|[Cчетчик](basic-ios-class.md#fail)|Возвращает значение **`true`** , если обнаружена неустранимая ошибка или ожидаемое условие, например ошибка преобразования или если файл не найден. Обработка часто может возобновляться после вызова `clear` с нулевым аргументом.|
|[рекомендуется](basic-ios-class.md#good)|Возвращает, **`true`** Если условие ошибки (невосстанавливаемое или в противном случае) отсутствует, а флаг конца файла не задан.|
|[конца](basic-ios-class.md#eof)|Возвращает **`true`** условие конца файла.|
|[открытым](basic-ios-class.md#clear)|Устанавливает внутреннее состояние ошибки. Если вызывается с аргументами по умолчанию, он очищает все биты ошибок.|
|rdstate (Basic-iOS-класс. md # rdstate|Возвращает текущее состояние ошибки.|

**!** оператор перегружен для выполнения той же функции, что и `fail` функция. Таким образом выражение:

```cpp
if(!cout)...
```

эквивалентно правилу

```cpp
if(cout.fail())...
```

Оператор **void\*()** перегружается, чтобы быть противоположностью оператора **!**; таким образом выражение:

```cpp
if(cout)...
```

эквивалентно:

```cpp
if(!cout.fail())...
```

Оператор **void \* ()** не эквивалентен, `good` поскольку он не проверяет конец файла.

## <a name="see-also"></a>См. также раздел

[Выходные потоки](../standard-library/output-streams.md)
