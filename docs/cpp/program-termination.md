---
title: Завершение программы C++
description: Описывает способы программирования на exit языке C++.
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- exit
- abort
- return
- main
- atexit
- void
ms.openlocfilehash: fd0c7699ae032b5551f4fbc37eb3b7fa999a168f
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352925"
---
# <a name="c-program-termination"></a>Завершение программы C++

В C++ вы можете выполнить exit программу следующими способами:

- Вызовите [exit](../c-runtime-library/reference/exit-exit-exit.md) функцию.
- Вызовите [abort](../c-runtime-library/reference/abort.md) функцию.
- Выполните [return](return-statement-cpp.md) инструкцию из `main` .

## <a name="no-locexit-function"></a>Функция exit

[exit](../c-runtime-library/reference/exit-exit-exit.md)Функция, объявленная в \<stdlib.h> , завершает программу на C++. Значение, передаваемое в качестве аргумента, `exit` восстановится в return операционной системе в виде return кода программы или exit кода. По соглашению return нулевой код означает, что программа выполнена успешно. Константы EXIT_FAILURE и EXIT_SUCCESS, также определенные в, можно использовать \<stdlib.h> для обозначения успеха или сбоя программы.

Выдача **`return`** инструкции из `main` функции эквивалентна вызову `exit` функции со return значением в качестве аргумента.

## <a name="no-locabort-function"></a>Функция abort

[abort](../c-runtime-library/reference/abort.md)Функция, также объявленная в стандартном включаемом файле \<stdlib.h> , завершает программу на C++. Разница между `exit` и заключается в том `abort` , что `exit` позволяет выполнять обработку завершения выполнения C++ (будут вызываться деструкторы глобальных объектов), тогда как `abort` программа немедленно завершает выполнение программы. `abort`Функция обходит обычный процесс уничтожения инициализированных глобальных статических объектов. Он также обходит любую специальную обработку, указанную с помощью [atexit](../c-runtime-library/reference/atexit.md) функции.

## <a name="no-locatexit-function"></a>Функция atexit

Используйте [atexit](../c-runtime-library/reference/atexit.md) функцию, чтобы указать действия, выполняемые до завершения программы. Глобальные статические объекты, инициализированные до вызова метода **atexit** , не уничтожаются до выполнения exit функции обработки.

## <a name="no-locreturn-statement-in-no-locmain"></a>return в main

Выдача [return](return-statement-cpp.md) инструкции из `main` функционально эквивалентна вызову `exit` функции. Рассмотрим следующий пример.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`Операторы и **`return`** в предыдущем примере функционально идентичны. Однако для C++ требуются функции, которые имеют return типы, отличные от **`void`** return значений. **`return`** Оператор позволяет получить return значение из `main` .

## <a name="destruction-of-static-objects"></a>Уничтожение статических объектов

При вызове `exit` или выполнении **`return`** инструкции из `main` статические объекты уничтожаются в обратном порядке их инициализации (после вызова метода, `atexit` если он существует). В следующем примере показано выполнение такого процесса инициализации и удаления.

### <a name="example"></a>Пример

В следующем примере статические объекты `sd1` и `sd2` создаются и инициализируются перед записью в `main` . После завершения выполнения этой программы с помощью **`return`** инструкции сначала `sd2` уничтожается, а затем `sd1` . Деструктор класса `ShowData` закрывает файлы, связанные с этими статическими объектами.

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

Другой способ записать этот код — объявить объекты `ShowData` с областью видимости блока, в результате чего они будут удаляться при выходе из области.

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>См. также раздел

[main аргументы функции и командной строки](main-function-command-line-args.md)
