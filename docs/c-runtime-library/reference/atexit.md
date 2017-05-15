---
title: "atexit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- atexit
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6d0d85ffc7f3ed71a26a947dd66c710e76388e96
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="atexit"></a>atexit
Обрабатывает указанную функцию на выходе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `func`  
 Функция, которую требуется вызвать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `atexit` возвращает 0 в случае успеха или ненулевое значение в случае ошибки.  
  
## <a name="remarks"></a>Примечания  
 Функции `atexit` передается адрес функции (`func`), которую требуется вызывать при завершении программы в обычном режиме. Последовательные вызовы функции `atexit` создают регистр функций, которые выполняются в порядке LIFO (последним поступил — первым обслужен). Функции, передаваемые в функции `atexit`, не могут принимать параметры. Для хранения регистра функций `atexit` и `_onexit` используют кучу. В связи с этим количество функций, которое можно зарегистрировать, ограничивается только памятью кучи.  
  
 Код в функции `atexit` не должен содержать никакие зависимости от библиотек DLL, которые при вызове функции `atexit` могли быть уже разгружены.  
  
 Для создания ANSI-совместимого приложения можно использовать функцию `atexit`, стандартную для ANSI (а не аналогичную функцию `_onexit`).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`atexit`|\<stdlib.h>|  
  
## <a name="example"></a>Пример  
 Это программа отправляет четыре функции в стек функций, которые должны выполняться при вызове `atexit`. При завершении работы программы эти программы выполняются в обратном порядке.  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
```Output  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)
