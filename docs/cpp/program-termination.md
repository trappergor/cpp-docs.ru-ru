---
title: Завершение программы C++
description: 'Описывает способы программирования на :::no-loc(exit)::: языке C++.'
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- :::no-loc(exit):::ing applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- ':::no-loc(exit):::'
- ':::no-loc(abort):::'
- ':::no-loc(return):::'
- ':::no-loc(main):::'
- ':::no-loc(atexit):::'
- ':::no-loc(void):::'
ms.openlocfilehash: 216aef5dbe8d110f9d75d43b5009b89fc5bfda51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227183"
---
# <a name="c-program-termination"></a>Завершение программы C++

В C++ вы можете выполнить :::no-loc(exit)::: программу следующими способами:

- Вызовите [:::no-loc(exit):::](:::no-loc(exit):::-function.md) функцию.
- Вызовите [:::no-loc(abort):::](:::no-loc(abort):::-function.md) функцию.
- Выполните [:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md) инструкцию из `:::no-loc(main):::` .

## <a name="no-locexit-function"></a>Функция :::no-loc(exit):::

[:::no-loc(exit):::](../c-runtime-library/reference/:::no-loc(exit):::-:::no-loc(exit):::-:::no-loc(exit):::.md)Функция, объявленная в \<stdlib.h> , завершает программу на C++. Значение, передаваемое в качестве аргумента, `:::no-loc(exit):::` восстановится в :::no-loc(return)::: операционной системе в виде :::no-loc(return)::: кода программы или :::no-loc(exit)::: кода. По соглашению :::no-loc(return)::: нулевой код означает, что программа выполнена успешно. Константы EXIT_FAILURE и EXIT_SUCCESS, также определенные в, можно использовать \<stdlib.h> для обозначения успеха или сбоя программы.

Выдача **`:::no-loc(return):::`** инструкции из `:::no-loc(main):::` функции эквивалентна вызову `:::no-loc(exit):::` функции со :::no-loc(return)::: значением в качестве аргумента.

## <a name="no-locabort-function"></a>Функция :::no-loc(abort):::

[:::no-loc(abort):::](../c-runtime-library/reference/:::no-loc(abort):::.md)Функция, также объявленная в стандартном включаемом файле \<stdlib.h> , завершает программу на C++. Разница между `:::no-loc(exit):::` и заключается в том `:::no-loc(abort):::` , что `:::no-loc(exit):::` позволяет выполнять обработку завершения выполнения C++ (будут вызываться деструкторы глобальных объектов), тогда как `:::no-loc(abort):::` программа немедленно завершает выполнение программы. `:::no-loc(abort):::`Функция обходит обычный процесс уничтожения инициализированных глобальных статических объектов. Он также обходит любую специальную обработку, указанную с помощью [:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md) функции.

## <a name="no-locatexit-function"></a>Функция :::no-loc(atexit):::

Используйте [:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md) функцию, чтобы указать действия, выполняемые до завершения программы. Глобальные статические объекты, инициализированные до вызова метода **:::no-loc(atexit):::** , не уничтожаются до выполнения :::no-loc(exit)::: функции обработки.

## <a name="no-locreturn-statement-in-no-locmain"></a>:::no-loc(return):::в:::no-loc(main):::

Выдача [:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md) инструкции из `:::no-loc(main):::` функционально эквивалентна вызову `:::no-loc(exit):::` функции. Рассмотрим следующий пример:

```cpp
// :::no-loc(return):::_statement.cpp
#include <stdlib.h>
int :::no-loc(main):::()
{
    :::no-loc(exit):::( 3 );
    :::no-loc(return)::: 3;
}
```

`:::no-loc(exit):::`Операторы и **`:::no-loc(return):::`** в предыдущем примере функционально идентичны. Однако для C++ требуются функции, которые имеют :::no-loc(return)::: типы, отличные от **`:::no-loc(void):::`** :::no-loc(return)::: значений. **`:::no-loc(return):::`** Оператор позволяет получить :::no-loc(return)::: значение из `:::no-loc(main):::` .

## <a name="destruction-of-static-objects"></a>Уничтожение статических объектов

При вызове `:::no-loc(exit):::` или выполнении **`:::no-loc(return):::`** инструкции из `:::no-loc(main):::` статические объекты уничтожаются в обратном порядке их инициализации (после вызова метода, `:::no-loc(atexit):::` если он существует). В следующем примере показано выполнение такого процесса инициализации и удаления.

### <a name="example"></a>Пример

В следующем примере статические объекты `sd1` и `sd2` создаются и инициализируются перед записью в `:::no-loc(main):::` . После завершения выполнения этой программы с помощью **`:::no-loc(return):::`** инструкции сначала `sd2` уничтожается, а затем `sd1` . Деструктор класса `ShowData` закрывает файлы, связанные с этими статическими объектами.

```cpp
// using_:::no-loc(exit):::_or_:::no-loc(return):::1.cpp
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
   :::no-loc(void)::: Disp( char *szData ) {
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

int :::no-loc(main):::() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

Другой способ записать этот код — объявить объекты `ShowData` с областью видимости блока, в результате чего они будут удаляться при выходе из области.

```cpp
int :::no-loc(main):::() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>См. также статью

[:::no-loc(main):::аргументы функции и командной строки](:::no-loc(main):::-function-command-line-args.md)
