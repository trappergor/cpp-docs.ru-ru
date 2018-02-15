---
title: "_clear87 _clearfp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
dev_langs:
- C++
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e1afc7bd1b5921a7ac24e8df2ed0adf0a807616
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="clear87-clearfp"></a>_clear87, _clearfp
Получает и очищает слово состояния модуля операций с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Биты в возвращаемом значении указывают состояние модуля операций с плавающей запятой до вызова функций `_clear87` и `_clearfp`. Полные определения битов, возвращаемых функцией `_clear87`, см. в файле Float.h. Многие математические библиотечные функции изменяют слово состояния 8087/80287 с непредсказуемыми результатами. Чем меньше операций с плавающей запятой выполняется между известными значениями слова состояния модуля операций с плавающей запятой, тем надежнее возвращаемые из функций `_clear87` и `_status87` значения.  
  
## <a name="remarks"></a>Примечания  
 Функция `_clear87` очищает флаги исключения в слове состояния операций с плавающей запятой, устанавливает бит занятости в 0 и возвращает слово состояния. Слово состояния — это сочетание слова состояния 8087/80287 и других условий, обнаруженных обработчиком исключений 8087/80287, таких как переполнение стека или потеря точности.  
  
 `_clearfp` — независимая от платформы, переносимая версия функции `_clear87`. Она идентична функции `_clear87` на платформах Intel (x86) и также поддерживается платформами x64 и ARM. Чтобы код, выполняющий операции с плавающей запятой, был переносимым на архитектуры x64 и ARM, используйте функцию `_clearfp`. Если код предназначен только для платформ x86, можно использовать функцию `_clear87` или `_clearfp`.  
  
 Эти функции являются устаревшими, при компиляции с параметром [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) Поскольку общеязыковая среда выполнения поддерживает только точность чисел с плавающей запятой по умолчанию.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_clear87`|\<float.h>|  
|`_clearfp`|\<float.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
```Output  
Status: 0000 - clear  
Status: 0003 - inexact, underflow  
Status: 80000 - denormal  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)