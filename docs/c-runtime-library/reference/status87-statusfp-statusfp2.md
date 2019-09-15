---
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
api_name:
- _statusfp2
- _statusfp
- _status87
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
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
ms.openlocfilehash: 54faf70296ef41f2682f88a8edaa82ee0d2071d4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958094"
---
# <a name="_status87-_statusfp-_statusfp2"></a>_status87, _statusfp, _statusfp2

Получает слово состояния модуля операций с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
unsigned int _status87( void );
unsigned int _statusfp( void );
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)
```

### <a name="parameters"></a>Параметры

*px86*<br/>
Этот адрес заполняется словом состояния для модуля операций с плавающей запятой x87.

*pSSE2*<br/>
Этот адрес заполняется словом состояния для модуля операций с плавающей запятой SSE2.

## <a name="return-value"></a>Возвращаемое значение

Для **_status87** и **_statusfp**биты в возвращаемом значении указывают на состояние с плавающей запятой. См. раздел FLOAT. H include File для определения битов, возвращаемых функцией **_statusfp**. Многие математические библиотечные функции изменяют слово состояния операций с плавающей запятой с непредсказуемыми результатами. Оптимизация может переупорядочивать, объединять и устранять операции с плавающей запятой вокруг вызовов **_status87**, **_statusfp**и связанных функций. Используйте параметр компилятора [/Od (выключение (отладчика))](../../build/reference/od-disable-debug.md) или директиву pragma [fenv_access](../../preprocessor/fenv-access.md) для исключения оптимизаций, изменяющих порядок операций с плавающей запятой. Значения, возвращаемые из **_clearfp** и **_statusfp**, а также возвращаемые параметры **_statusfp2**, более надежны, если между известными состояниями слова состояния с плавающей запятой выполняется меньше операций с плавающей запятой.

## <a name="remarks"></a>Примечания

Функция **_statusfp** получает слово состояния с плавающей запятой. Слово состояния содержит состояние модуля операций с плавающей запятой и другие условия, обнаруженные обработчиком исключений операций с плавающей запятой, — например, переполнение стека или потеря точности. Перед возвращением содержимого слова состояния проверяются немаскированные исключения. Это означает, что вызывающая функция информируется о необработанных исключениях. На платформах x86 **_statusfp** Возвращает сочетание состояния с плавающей точкой X87 и SSE2. На платформах x64 возвращаемое состояние основывается на состоянии MXCSR SSE. На платформах ARM **_statusfp** возвращает состояние из регистра регистра fpscr.

**_statusfp** — это независимая от платформы переносимая версия **_status87**. Он идентичен **_status87** на платформах Intel (x86) и поддерживается платформами x64 и ARM. Чтобы обеспечить перенос кода с плавающей запятой во все архитектуры, используйте **_statusfp**. Если вы предназначена только для платформ x86, можно использовать либо **_status87** , либо **_statusfp**.

Мы рекомендуем **_statusfp2** для микросхем (например, Pentium IV), которые имеют процессор с плавающей запятой X87 и SSE2. Для **_statusfp2**адреса заполняются с помощью слова состояния с плавающей запятой для процессора с плавающей запятой X87 или SSE2. Для микросхемы, поддерживающей обработчики с плавающей запятой x87 и SSE2, EM_AMBIGUOUS устанавливается в значение 1, если используется **_statusfp** или **_controlfp** , а действие неоднозначно, так как оно может ссылаться на слово состояния x87 или SSE2 с плавающей запятой. Функция **_statusfp2** поддерживается только на платформах x86.

Эти функции не используются для [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md) , так как среда CLR поддерживает только точность с плавающей запятой по умолчанию.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_status87**, **_statusfp**, **_statusfp2**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
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

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
