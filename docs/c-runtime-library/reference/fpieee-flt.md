---
title: "_fpieee_flt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpieee_flt"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fpieee_flt"
  - "_fpieee_flt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция _fpieee_flt"
  - "обработка исключений, с плавающей запятой"
  - "обработка исключений с плавающей запятой"
  - "Функция fpieee_flt"
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _fpieee_flt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает определяемый пользователем обработчик исключений и повреждений для исключений IEEE с плавающей точкой.  
  
## Синтаксис  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### Параметры  
 `excCode`  
 Код исключения.  
  
 `excInfo`  
 Указатель на структуру сведений об исключении Windows NT.  
  
 `handler`  
 Указатель на пользовательскую процедуру обработчика исключений и повреждений IEEE.  
  
## Возвращаемое значение  
 Возвращаемое значение `_fpieee_flt` \- значение, возвращённое `handler`.  В этом случае процедура фильтра IEEE может быть использована в условном выражении except механизма структурной обработки исключений \(SEH\).  
  
## Заметки  
 Функция `_fpieee_flt` вызывает определяемый пользователем обработчик исключений и повреждений для исключений IEEE с плавающей точкой и предоставляет его со всей нужной информацией.  Эта процедура служит в виде фильтра исключений в механизме SEH, который вызывает ваш собственные обработчик исключений IEEE в случае необходимости.  
  
 Структура `_FPIEEE_RECORD`, определенная в Fpieee.h, содержит сведения, относящихся к исключениям IEEE с плавающей точкой.  Эта структура передается функцией `_fpieee_flt` обработчику исключений и повреждений, определяемому пользователем.  
  
|Поле \_FPIEEE\_RECORD|Описание|  
|---------------------------|--------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|Эти поля содержат сведения о среде чисел с плавающей точкой в момент возникновения исключения.|  
|`unsigned int Operation`|Указывает тип операции, вызвавшей ловушку.  Если этот тип \- сравнение \(`_FpCodeCompare`\), можно задать одно из специальных значений `_FPIEEE_COMPARE_RESULT` \(как определено в Fpieee.h\) в поле `Result.Value`.  Тип преобразования \(`_FpCodeConvert`\) указывает на то, что ловушка произошла во время операции преобразования числа с плавающей точкой.  Типы `Operand1` и  `Result` определяют тип этого преобразования.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|Эти структуры указывают типы и значения предполагаемого результата и операндов:<br /><br /> `OperandValid` Флажок, указывающее, является ли значение допустимым.<br /><br /> `Format` Тип данных соответствующего значения.  Тип формата может быть возвращен, даже если соответствующее значение недопустимо.<br /><br /> `Value` Значение данных результата или операнда.|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|\_FPIEEE\_EXCEPTION\_FLAGS содержит одно битовое поле для каждого типа исключения для числа с плавающей точкой.<br /><br /> Есть соответствие между этими полями и аргументами, используемыми в маске исключения, предоставленной [\_controlfp](../Topic/_control87,%20_controlfp,%20__control87_2.md).<br /><br /> Точное значение каждого бита зависит от контекста:<br /><br /> `Cause` Каждый бит набора отображает определенное исключение, которое было вызвано.<br /><br /> `Enable` Каждый бит набора отображает конкретное исключение, которое в данный момент демаскировано.<br /><br /> `Status` Каждый бит набора отображает конкретное исключение, которое в данный момент ожидается.  Сюда включаются исключения, которые не вызывались, поскольку они были маскированы `_controlfp`.|  
  
 Ожидающие исключения, которые отключены, вызываются при их включении.  Это может привести к непредвиденному поведению при использовании `_fpieee_flt` в качестве фильтра исключений.  Всегда следует вызывать [\_clearfp](../../c-runtime-library/reference/clear87-clearfp.md) перед включением исключений для чисел с плавающей точкой.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_fpieee_flt`|\<fpieee.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_fpieee.c  
// This program demonstrates the implementation of  
// a user-defined floating-point exception handler using the  
// _fpieee_flt function.  
  
#include <fpieee.h>  
#include <excpt.h>  
#include <float.h>  
#include <stddef.h>  
  
int fpieee_handler( _FPIEEE_RECORD * );  
  
int fpieee_handler( _FPIEEE_RECORD *pieee )  
{  
   // user-defined ieee trap handler routine:  
   // there is one handler for all   
   // IEEE exceptions  
  
   // Assume the user wants all invalid   
   // operations to return 0.  
  
   if ((pieee->Cause.InvalidOperation) &&   
       (pieee->Result.Format == _FpFormatFp32))   
   {  
        pieee->Result.Value.Fp32Value = 0.0F;  
  
        return EXCEPTION_CONTINUE_EXECUTION;  
   }  
   else  
      return EXCEPTION_EXECUTE_HANDLER;  
}  
  
#define _EXC_MASK    \  
    _EM_UNDERFLOW  + \  
    _EM_OVERFLOW   + \  
    _EM_ZERODIVIDE + \  
    _EM_INEXACT  
  
int main( void )  
{  
   // ...  
  
   __try {  
      // unmask invalid operation exception  
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);   
  
      // code that may generate   
      // fp exceptions goes here  
   }  
   __except ( _fpieee_flt( GetExceptionCode(),  
                GetExceptionInformation(),  
                fpieee_handler ) ){  
  
      // code that gets control   
  
      // if fpieee_handler returns  
      // EXCEPTION_EXECUTE_HANDLER goes here  
  
   }  
  
   // ...  
}  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)   
 [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md)