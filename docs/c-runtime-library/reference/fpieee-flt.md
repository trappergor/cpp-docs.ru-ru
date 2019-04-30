---
title: _fpieee_flt
ms.date: 04/05/2018
apiname:
- _fpieee_flt
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
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
ms.openlocfilehash: 9a49ec403b1cb95407b0a366accf1d9374d9cb22
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333252"
---
# <a name="fpieeeflt"></a>_fpieee_flt

Вызывает определяемый пользователем обработчик исключений и прерываний для исключений IEEE с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>Параметры

*excCode*<br/>
Код исключения.

*excInfo*<br/>
Указатель на структуру сведений об исключении Windows NT.

*Обработчик*<br/>
Указатель на пользовательскую подпрограмму обработчика исключений и прерываний IEEE.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение **_fpieee_flt** является значение, возвращенное *обработчик*. Как таковая, подпрограмма фильтра IEEE может быть использована в выражении except механизма структурной обработки исключений (SEH).

## <a name="remarks"></a>Примечания

**_Fpieee_flt** функция вызывает обработчик прерываний для исключений с плавающей запятой IEEE и предоставляет ему все важные сведения. Эта подпрограмма выполняет роль фильтра исключений в механизме SEH, который вызывает ваш собственные обработчик исключений IEEE в случае необходимости.

**_FPIEEE_RECORD** структура, определенная в Fpieee.h, содержит сведения, относящиеся к исключения с плавающей запятой IEEE. Эта структура передается в обработчик прерываний, **_fpieee_flt**.

|Поле _FPIEEE_RECORD|Описание|
|----------------------------|-----------------|
|**RoundingMode**<br/>**Точность**|Эти **без знака** **int** поля содержат сведения о среду с плавающей запятой в момент возникновения исключения.|
|**Операция**|Это **без знака** **int** поле указывает тип операции, вызвавшей перехват. Если тип является сравнением (**_FpCodeCompare**), можно задать одно из специальных **_FPIEEE_COMPARE_RESULT** значения (как определено в Fpieee.h) в **Result.Value** поля. Тип преобразования (**_FpCodeConvert**) указывает, что захват произошел во время операции преобразования с плавающей запятой. Вы можете изучить **операнд1** и **результат** типа, чтобы определить тип этого преобразования.|
|**Операнд1**<br/>**Операнд2**<br/>**Результат**|Эти **_FPIEEE_VALUE** структуры указывают типы и значения предполагаемого результата и операндов. Каждая структура содержит следующие поля:<br /><br /> **OperandValid** — флаг, указывающий, является ли значение допустимым.<br />**Формат** -тип данных соответствующего значения. Тип формата может быть возвращен даже в том случае, если соответствующее значение недопустимо.<br />**Значение** -значение данных результата или операнда.|
|**Причина**<br/>**Enable**<br/>**Состояние**|**_FPIEEE_EXCEPTION_FLAGS** содержит одно битовое поле для каждого типа операций с плавающей запятой. Имеется соответствие между этими полями и аргументами, используемыми в маске исключения, переданной функции [_controlfp](control87-controlfp-control87-2.md). Точное смысловое значение каждого бита зависит от контекста:<br /><br /> **Причина** -каждый установленный бит отображает определенное исключение, которое было создано.<br />**Включить** -каждый установленный бит обозначает, что конкретное исключение в данный момент демаскировано.<br />**Состояние** -каждый установленный бит отображает определенное исключение в настоящее время ожидается. Сюда входят исключения, которые не были созданы так, как они были маскированы **_controlfp**.|

Отключенные ожидающие исключения вызываются при их включении. Это может привести к неопределенному поведению при использовании **_fpieee_flt** как фильтр исключений. Перед включением исключений для чисел с плавающей запятой обязательно вызывайте функцию [_clearfp](clear87-clearfp.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
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

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
