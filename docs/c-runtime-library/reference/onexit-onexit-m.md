---
title: "_onexit, _onexit_m | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 50070672e990333073f5ad7f7ba604110c3a3cfa
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m
Регистрирует подпрограмму, вызываемую во время выхода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `function`  
 Указатель на функцию, которая должна вызываться при выходе.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_onexit` возвращает указатель на функцию в случае успеха или значение `NULL`, если нет места для хранения указателя на функцию.  
  
## <a name="remarks"></a>Примечания  
 Функции `_onexit` передается адрес функции (`function`), которую требуется вызывать при завершении программы в обычном режиме. Последовательные вызовы функции `_onexit` создают регистр функций, которые выполняются в порядке LIFO (последним поступил — первым обслужен). Функции, передаваемые в функции `_onexit`, не могут принимать параметры.  
  
 В случае, если функция `_onexit` вызывается из библиотеки DLL, подпрограммы, зарегистрированные с помощью функции `_onexit`, выполняются при выгрузке DLL после вызова `DllMain` с DLL_PROCESS_DETACH.  
  
 `_onexit` является расширением Майкрософт. Чтобы обеспечить переносимость ANSI, используйте функцию [atexit](../../c-runtime-library/reference/atexit.md). Версия `_onexit_m` этой функции предназначена для использования смешанного режима.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_onexit`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [__dllonexit](../../c-runtime-library/dllonexit.md)
