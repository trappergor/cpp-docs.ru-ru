---
title: C++завершение программы
description: Описывает способы exit программы на C++языке.
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
ms.openlocfilehash: f83c9d5da5b0a1127603a97fd7946e9cca43a7a5
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123959"
---
# <a name="c-program-termination"></a>C++завершение программы

В C++можно exit программу следующими способами:

- Вызовите функцию [exit](exit-function.md) .
- Вызовите функцию [abort](abort-function.md) .
- Выполните инструкцию [return](return-statement-cpp.md) из `main`.

## <a name="opno-locexit-function"></a>Функция exit

Функция [exit](../c-runtime-library/reference/exit-exit-exit.md) , объявленная в \<stdlib. h >, завершает C++ программу. Значение, передаваемое в качестве аргумента в `exit`, возвращается операционной системе в виде кода return программы или кода exit. По соглашению код return ноль означает, что программа выполнена успешно. Константы EXIT_FAILURE и EXIT_SUCCESS, также определенные в \<stdlib. h >, можно использовать для обозначения успеха или неудачи программы.

Выдача оператора **return** из функции `main` эквивалентно вызову функции `exit` со значением return в качестве аргумента.

## <a name="opno-locabort-function"></a>Функция abort

Функция [abort](../c-runtime-library/reference/abort.md) , также объявленная в стандартном включаемом файле \<stdlib. h >, завершает C++ программу. Различие между `exit` и `abort` заключается в том, что `exit` C++ позволяет обрабатывать прерывание во время выполнения (будут вызываться деструкторы глобальных объектов), в то время как `abort` немедленно прерывает выполнение программы. Функция `abort` обходит обычный процесс уничтожения инициализированных глобальных статических объектов. Он также обходит любую специальную обработку, указанную с помощью функции [atexit](../c-runtime-library/reference/atexit.md) .

## <a name="opno-locatexit-function"></a>Функция atexit

Используйте функцию [atexit](../c-runtime-library/reference/atexit.md) , чтобы указать действия, которые выполняются до завершения программы. Глобальные статические объекты, не инициализированные до вызова **atexit** , уничтожаются до выполнения функции обработки exit.

## <a name="opno-locreturn-statement-in-opno-locmain"></a>Оператор return в main

Выдача [return](return-statement-cpp.md) оператора из `main` функционально эквивалентна вызову функции `exit`. Рассмотрим следующий пример.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Операторы `exit` и **return** в предыдущем примере функционально идентичны. Однако C++ требует, чтобы функции, имеющие return типы, отличные от **void** , return значение. Оператор **return** позволяет return значение из `main`.

## <a name="destruction-of-static-objects"></a>Уничтожение статических объектов

При вызове `exit` или выполнении инструкции **return** из `main`статические объекты уничтожаются в обратном порядке их инициализации (после вызова `atexit`, если он существует). В следующем примере показано выполнение такого процесса инициализации и удаления.

### <a name="example"></a>Пример

В следующем примере статические объекты `sd1` и `sd2` создаются и инициализируются перед записью `main`. После завершения работы программы с помощью оператора **return** сначала уничтожаются `sd2`, а затем `sd1`. Деструктор класса `ShowData` закрывает файлы, связанные с этими статическими объектами.

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

## <a name="see-also"></a>См. также:

[функции main и аргументы командной строки](main-function-command-line-args.md)
