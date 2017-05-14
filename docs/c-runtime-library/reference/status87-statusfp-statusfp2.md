---
title: "_status87, _statusfp, _statusfp2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _statusfp2
- _statusfp
- _status87
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
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
dev_langs:
- C++
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
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
ms.openlocfilehash: 69a19aaa457ffc52c431a9ca1c3597a475a10994
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2
Получает слово состояния модуля операций с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### <a name="parameters"></a>Параметры  
 `px86`  
 Этот адрес заполняется словом состояния для модуля операций с плавающей запятой x87.  
  
 `pSSE2`  
 Этот адрес заполняется словом состояния для модуля операций с плавающей запятой SSE2.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Для функций `_status87` и `_statusfp` биты в возвращаемом значении указывают состояние модуля операций с плавающей запятой. Определения битов, возвращаемых функцией `_statusfp`, см. в файле FLOAT.H. Многие математические библиотечные функции изменяют слово состояния операций с плавающей запятой с непредсказуемыми результатами. Оптимизация может изменять, объединять и исключать операции с плавающей запятой вокруг вызовов `_status87`, `_statusfp` и связанных функций. Используйте параметр компилятора [/Od (выключение (отладчика))](../../build/reference/od-disable-debug.md) или директиву pragma [fenv_access](../../preprocessor/fenv-access.md) для исключения оптимизаций, изменяющих порядок операций с плавающей запятой. Чем меньше операций с плавающей запятой выполняется между известными значениями слова состояния модуля операций с плавающей запятой, тем надежнее возвращаемые из функций `_clearfp` и `_statusfp` значения, а также возвращаемые параметры функции `_statusfp2`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_statusfp` получает слово состояния модуля операций с плавающей запятой. Слово состояния содержит состояние модуля операций с плавающей запятой и другие условия, обнаруженные обработчиком исключений операций с плавающей запятой, — например, переполнение стека или потеря точности. Перед возвращением содержимого слова состояния проверяются немаскированные исключения. Это означает, что вызывающая функция информируется о необработанных исключениях. На платформах x86 функция `_statusfp` возвращает комбинацию состояний x87 и SSE2 модуля операций с плавающей запятой. На платформах x64 возвращаемое состояние основывается на состоянии MXCSR SSE. На платформах ARM функция `_statusfp` возвращает состояние из регистра FPSCR.  
  
 `_statusfp` — независимая от платформы, переносимая версия функции `_status87`. Она идентична функции `_status87` на платформах Intel (x86) и также поддерживается платформами x64 и ARM. Чтобы код, выполняющий операции с плавающей запятой, был переносимым на все архитектуры, используйте функцию `_statusfp`. Если код предназначен только для платформ x86, можно использовать функцию `_status87` или `_statusfp`.  
  
 Для процессоров, поддерживающих как набор команд x87, так и SSE2 (например, Pentium IV), рекомендуется использовать функцию `_statusfp2`. В случае функции `_statusfp2` адреса заполняются с использованием слова состояния процессора операций с плавающей запятой как для x87, так и для SSE2. В случае микросхем, поддерживающих процессоры с плавающей запятой x87 и SSE2, для бита EM_AMBIGUOUS устанавливается значение 1, если используется функция `_statusfp` или `_controlfp` и действие было неоднозначным, поскольку оно могло ссылаться на слово состояние модуля операций с плавающей запятой x87 или SSE2. Функция `_statusfp2` поддерживается только на платформах x86.  
  
 Эти функции не используются в [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) поскольку общеязыковой среды выполнения (CLR) поддерживает только точность чисел с плавающей запятой по умолчанию.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
```Output  
Status = 0x00000000 - clear  
Status = 0x00000003 - inexact, underflow  
Status = 0x00080003 - inexact, underflow, denormal  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
