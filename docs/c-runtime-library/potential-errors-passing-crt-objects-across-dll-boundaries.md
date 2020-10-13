---
title: Потенциальные ошибки при передаче объектов CRT через границы DLL
description: Обзор потенциальных проблем, которые могут возникнуть при передаче объектов среды выполнения Microsoft C через границу библиотеки динамической компоновки (DLL).
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
ms.openlocfilehash: 2d42803b5eca7a43f122d209b7d9e2d4e45c38de
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008944"
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>Потенциальные ошибки при передаче объектов CRT через границы DLL

При передаче объектов времени выполнения (CRT), таких как дескрипторы файлов, языковые стандарты и переменные среды, в библиотеку DLL или из нее через вызовы функций через границу DLL, непредвиденное поведение может возникнуть, если библиотека DLL или файлы, вызывающие эту БИБЛИОТЕКУ, используют разные копии библиотек CRT.

Связанная проблема может возникнуть при выделении памяти (явно с помощью `new` или `malloc` , или неявно с помощью `strdup` , `strstreambuf::str` и т. д.), а затем передайте указатель через границу библиотеки DLL, в которую она освобождается. Это может привести к нарушению прав доступа к памяти или повреждению кучи, если библиотека DLL и ее потребители используют разные копии библиотек CRT.

Другим симптомом этой проблемы является ошибка в окне вывода во время отладки, например `HEAP[]: Invalid Address specified to RtlValidateHeap(#,#)`

## <a name="causes"></a>Причины

Каждая копия библиотеки CRT имеет определенное собственное состояние, которое хранится приложением или библиотекой DLL в локальном хранилище потока приложения.

Объекты CRT, такие как дескрипторы файлов, переменные среды и языковые стандарты, допустимы только для копии CRT в приложении или библиотеке DLL, где эти объекты были выделены или заданы. Если библиотека DLL и ее клиенты используют разные копии библиотеки CRT, вы не сможете передать эти объекты CRT через границу DLL, и они должны правильно использоваться на другой стороне. Это справедливо для CRT-версий до универсальной CRT в Visual Studio 2015 и более поздних версиях.

В Visual Studio 2013 и более ранних версиях создавались специальные библиотеки CRT для каждой версии Visual Studio. Внутренние детали реализации CRT, такие как структуры данных и соглашения об именовании, отличаются в каждой версии. Динамическая компоновка кода, скомпилированного для одной версии CRT, в другую версию библиотеки DLL CRT никогда не поддерживалась. Иногда это сработает, но из-за удачи, а не проектирования.

Поскольку каждая копия библиотеки CRT имеет собственный диспетчер куч, выделение памяти в одной библиотеке CRT и передача указателя через границу библиотеки DLL для освобождения другой копии библиотеки CRT, может привести к повреждению кучи. Если вы разрабатываете библиотеку DLL таким образом, чтобы она передавала объекты CRT через границу DLL, или выделяет память и предполагает ее освобождение вне библиотеки DLL, клиенты библиотеки DLL должны использовать ту же копию библиотеки CRT, что и библиотека DLL.

Библиотека DLL и ее клиенты используют одну и ту же копию библиотеки CRT, только если при загрузке они будут связаны с одной и той же версией DLL CRT. Так как версия библиотеки DLL универсальной библиотеки CRT, используемой Visual Studio 2015 и более поздних версий в Windows 10, теперь является центрально развернутым компонентом Windows (ucrtbase.dll), это то же самое, что и для приложений, созданных с помощью Visual Studio 2015 и более поздних версий. Однако даже если код CRT идентичен, нельзя выделить память, выделенную в одной куче, компоненту, использующему другую кучу.

## <a name="example-pass-file-handle-across-dll-boundary"></a>Пример. Передача обработчика файла через границу DLL

### <a name="description"></a>Описание

В этом примере дескриптор файла передается через границу библиотеки DLL.

DLL-и exe-файлы создаются с помощью `/MD` , поэтому они совместно используют одну копию CRT.

При перестроении с `/MT` таким образом, чтобы они использовали отдельные копии CRT, выполнение полученного **test1Main.exe** приведет к нарушению прав доступа.

```cpp
// test1Dll.cpp
// compile with: cl /EHsc /W4 /MD /LD test1Dll.cpp
#include <stdio.h>
__declspec(dllexport) void writeFile(FILE *stream)
{
   char   s[] = "this is a string\n";
   fprintf( stream, "%s", s );
   fclose( stream );
}
```

```cpp
// test1Main.cpp
// compile with: cl /EHsc /W4 /MD test1Main.cpp test1Dll.lib
#include <stdio.h>
#include <process.h>
void writeFile(FILE *stream);

int main(void)
{
   FILE  * stream;
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );
   writeFile(stream);
   system( "type fprintf.out" );
}
```

```Output
this is a string
```

## <a name="example-pass-environment-variables-across-dll-boundary"></a>Пример. Передача переменных среды через границу DLL

### <a name="description"></a>Описание

В этом примере переменные среды передаются через границу библиотеки DLL.

```cpp
// test2Dll.cpp
// compile with: cl /EHsc /W4 /MT /LD test2Dll.cpp
#include <stdio.h>
#include <stdlib.h>

__declspec(dllexport) void readEnv()
{
   char *libvar;
   size_t libvarsize;

   /* Get the value of the MYLIB environment variable. */
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );

   if( libvar != NULL )
      printf( "New MYLIB variable is: %s\n", libvar);
   else
      printf( "MYLIB has not been set.\n");
   free( libvar );
}
```

```cpp
// test2Main.cpp
// compile with: cl /EHsc /W4 /MT test2Main.cpp test2dll.lib
#include <stdlib.h>
#include <stdio.h>

void readEnv();

int main( void )
{
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );
   readEnv();
}
```

```Output
MYLIB has not been set.
```

Если и библиотека DLL, и exe-файл созданы с помощью, `/MD` так что используется только одна копия CRT, программа выполняется успешно и выдается следующий результат:

```
New MYLIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>См. также статью

[Возможности библиотеки CRT](../c-runtime-library/crt-library-features.md)
