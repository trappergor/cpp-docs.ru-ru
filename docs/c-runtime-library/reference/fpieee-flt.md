---
title: "_fpieee_flt | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fpieee_flt
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
- fpieee_flt
- _fpieee_flt
dev_langs: C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2e3f91d2baca3829538d199ce000d56a7be24d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fpieeeflt"></a>_fpieee_flt
Вызывает определяемый пользователем обработчик исключений и прерываний для исключений IEEE с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `excCode`  
 Код исключения.  
  
 `excInfo`  
 Указатель на структуру сведений об исключении Windows NT.  
  
 `handler`  
 Указатель на пользовательскую подпрограмму обработчика исключений и прерываний IEEE.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение `_fpieee_flt` представляет собой значение, возвращенное `handler`. Как таковая, подпрограмма фильтра IEEE может быть использована в выражении except механизма структурной обработки исключений (SEH).  
  
## <a name="remarks"></a>Примечания  
 Функция `_fpieee_flt` вызывает определяемый пользователем обработчик исключений и прерываний для исключений IEEE с плавающей запятой и предоставляет ему всю требуемую информацию. Эта подпрограмма выполняет роль фильтра исключений в механизме SEH, который вызывает ваш собственные обработчик исключений IEEE в случае необходимости.  
  
 Структура `_FPIEEE_RECORD`, определенная в Fpieee.h, содержит сведения, относящиеся к исключениям IEEE с плавающей запятой. Эта структура передается функцией `_fpieee_flt` обработчику исключений и прерываний, определяемому пользователем.  
  
|Поле _FPIEEE_RECORD|Описание|  
|----------------------------|-----------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|Эти поля содержат сведения о среде чисел с плавающей запятой в момент возникновения исключения.|  
|`unsigned int Operation`|Указывает тип операции, вызвавшей перехват. Если этот тип является сравнением (`_FpCodeCompare`), можно задать одно из специальных значений `_FPIEEE_COMPARE_RESULT` (как определено в Fpieee.h) в поле `Result.Value`. Тип преобразования (`_FpCodeConvert`) указывает на то, что захват произошел во время операции преобразования числа с плавающей запятой. Типы `Operand1` и `Result` позволяют определить тип этого преобразования.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|Эти структуры указывают типы и значения предполагаемого результата и операндов:<br /><br /> `OperandValid` Флаг, указывающий, является ли значение допустимым.<br /><br /> `Format` Тип данных соответствующего значения. Тип формата может быть возвращен даже в том случае, если соответствующее значение недопустимо.<br /><br /> `Value` Значение данных результата или операнда.|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|_FPIEEE_EXCEPTION_FLAGS содержит одно битовое поле для каждого типа исключений для чисел с плавающей запятой.<br /><br /> Имеется соответствие между этими полями и аргументами, используемыми в маске исключения, переданной функции [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md).<br /><br /> Точное смысловое значение каждого бита зависит от контекста:<br /><br /> `Cause` Каждый установленный бит отображает определенное исключение, которое было вызвано.<br /><br /> `Enable` Каждый установленный бит отображает конкретное исключение, которое в данный момент демаскировано.<br /><br /> `Status` Каждый установленный бит отображает конкретное исключение, которое в данный момент находится в состоянии ожидания. Сюда входят исключения, которые не вызывались, поскольку они были маскированы `_controlfp`.|  
  
 Отключенные ожидающие исключения вызываются при их включении. Это может привести к непредвиденному поведению при использовании `_fpieee_flt` в качестве фильтра исключений. Перед включением исключений для чисел с плавающей запятой обязательно вызывайте функцию [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fpieee_flt`|\<fpieee.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)