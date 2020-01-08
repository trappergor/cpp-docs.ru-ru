---
title: C++завершение программы
ms.date: 12/10/2019
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
ms.openlocfilehash: a0e86cacd951327d39296a183be5ee4fbc36fd15
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301344"
---
# <a name="c-program-termination"></a>C++завершение программы

В C++можно выйти из программы следующими способами:

- Вызовите функцию [Exit](exit-function.md) .
- Вызовите функцию [Abort](abort-function.md) .
- Выполните инструкцию [return](return-statement-cpp.md) из `main`.

## <a name="exit-function"></a>Функция exit

Функция [Exit](../c-runtime-library/reference/exit-exit-exit.md) , объявленная в \<stdlib. h >, завершает C++ программу. Значение, передаваемое в качестве аргумента в `exit`, возвращается операционной системе в качестве кода возврата программы или кода выхода. Принято, чтобы нулевым кодом возврата обозначалось, что программа завершена успешно. Константы EXIT_FAILURE и EXIT_SUCCESS, также определенные в \<stdlib. h >, можно использовать для обозначения успеха или неудачи программы.

Выдача оператора **return** из функции `main` эквивалентна вызову функции `exit` с возвращаемым значением в качестве аргумента.

## <a name="abort-function"></a>abort - функция

[Abort](../c-runtime-library/reference/abort.md) функция, также объявляется в стандартном включаемом файле \<stdlib.h >, завершает программу C++. Различие между `exit` и `abort` заключается в том, что `exit` C++ позволяет обрабатывать прерывание во время выполнения (будут вызываться деструкторы глобальных объектов), в то время как `abort` немедленно прерывает выполнение программы. Функция `abort` обходит обычный процесс уничтожения инициализированных глобальных статических объектов. Он также обходит любую специальную обработку, указанную с помощью функции [atexit](../c-runtime-library/reference/atexit.md) .

## <a name="atexit-function"></a>atexit - функция

Используйте функцию [atexit](../c-runtime-library/reference/atexit.md) , чтобы указать действия, которые выполняются до завершения программы. Глобальные статические объекты, инициализированные до вызова **atexit** , не будут уничтожены до выполнения функции exit-Processing.

## <a name="return-statement-in-main"></a>оператор return в Main

Выдача оператора [return](return-statement-cpp.md) из `main` функционально эквивалентна вызову функции `exit`. Рассмотрим следующий пример.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Операторы `exit` и **return** в предыдущем примере функционально идентичны. Однако C++ требует, чтобы функции с возвращаемыми типами, отличными от **void** , возвращали значение. Оператор **return** позволяет возвращать значение из `main`.

## <a name="destruction-of-static-objects"></a>Уничтожение статических объектов

При вызове `exit` или выполнении инструкции **return** из `main`статические объекты уничтожаются в обратном порядке их инициализации (после вызова `atexit`, если он существует). В следующем примере показано выполнение такого процесса инициализации и удаления.

### <a name="example"></a>Пример

В следующем примере статические объекты `sd1` и `sd2` создаются и инициализируются перед записью `main`. После завершения работы программы с помощью инструкции **return** первый `sd2` уничтожается, а затем `sd1`. Деструктор класса `ShowData` закрывает файлы, связанные с этими статическими объектами.

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

[Функция main: запуск программы](main-program-startup.md)