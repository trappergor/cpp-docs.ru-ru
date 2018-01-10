---
title: "Возможные ошибки при передаче объектов CRT через границы DLL | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0355b1c6a2731c9ca82e7ced37ad28f30a881eca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>Потенциальные ошибки при передаче объектов CRT через границы DLL
При передаче объектов времени выполнения C (CRT), таких как дескрипторы файлов, языковые стандарты и переменные среды, в библиотеку DLL или из нее (вызовы функций через границы DLL) может возникнуть непредвиденное поведение, если библиотека DLL, а также файлы вызывающие функции из DLL, используют различные копии библиотек CRT.  
  
 Связанная с этим проблема может возникнуть при выделении памяти (либо явно с использованием `new` или `malloc`, либо неявно с использованием `strdup`, `strstreambuf::str` и т. д.) и последующей передаче указателя через границу библиотеки DLL для освобождения. Это может вызвать повреждение кучи или нарушение доступа к памяти, если библиотека DLL и ее пользователи используют различные копии библиотек CRT.  
  
 Другим признаком этой проблемы может быть ошибка в окне вывода во время отладки, например:  
  
 HEAP[]: Invalid Address specified to RtlValidateHeap(#,#)  
  
## <a name="causes"></a>Причины  
 Каждая копия библиотеки CRT имеет определенное собственное состояние, которое хранится приложением или библиотекой DLL в локальном хранилище потока приложения. Поэтому объекты CRT, такие как дескрипторы файлов, переменные среды и языковые стандарты, применимы только для той копии CRT в приложении или DLL, в которой эти объекты размещены или установлены. Если библиотека DLL и ее клиентские приложения используют разные копии библиотеки CRT, вы не можете просто передать CRT-объект через границу DLL, ожидая, что он будет правильно принят на другой стороне. Это особенно актуально для версий CRT, выпущенных до появления универсальной CRT в Visual Studio версии 2015 и выше. В Visual C++ 2013 и более ранних версиях создавались специальные библиотеки CRT для каждой версии Visual Studio. Внутренняя реализация библиотек CRT, в том числе структуры данных и соглашения об именовании, могли различаться в разных версиях. Динамически связанный код, скомпилированный для конкретной версии CRT, никогда не поддерживался в других версиях DLL CRT. Иногда он мог успешно работать при переносе, но это происходило скорее случайно.  
  
 Кроме того, поскольку все копии библиотеки CRT имеют свой собственный диспетчер кучи, распределение памяти в одной библиотеке CRT и передача указателя через границу DLL для освобождения другой копией библиотеки CRT может вызвать повреждение кучи. Если вы разрабатываете библиотеку DLL так, чтобы она передавала объекты CRT через границы или распределяла память и ожидала ее освобождения вне DLL, клиентские приложения будут вынуждены использовать в качестве DLL ту же копию библиотеки CRT. Библиотека DLL и ее клиенты используют одну и ту же копию библиотеки CRT, только если при загрузке они будут связаны с одной и той же версией DLL CRT. В Visual Studio версии 2015 и выше под управлением Windows 10 версия DLL для универсальной библиотеки CRT развертывается централизованно как компонент Windows ucrtbase.dll. Поэтому теперь она будет одинаковой для всех приложений, созданных в Visual Studio версии 2015 и выше. Но даже когда код CRT будет одинаковым, вы не сможете передавать память, выделенную в одной куче, любому компоненту, использующему другую кучу.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В этом примере дескриптор файла передается через границу библиотеки DLL.  
  
 Библиотека DLL и exe-файл создаются с /MD, поэтому они совместно используют один экземпляр CRT.  
  
 При повторной сборке с /MT таким образом, чтобы в них использовались отдельные копии CRT, запуск получившегося test1Main.exe вызывает нарушение прав доступа.  
  
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
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
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
  
 Если и библиотека DLL, и exe-файл создаются с /MD так, что будет использоваться только одна копия CRT, программа выполняется успешно и выдает следующий результат:  
  
```  
New MYLIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)