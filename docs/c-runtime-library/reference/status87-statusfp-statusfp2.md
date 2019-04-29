---
title: _status87, _statusfp, _statusfp2
ms.date: 04/05/2018
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
ms.openlocfilehash: 271c28dd4e267e5b3b702858cc398689e3e35d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354435"
---
# <a name="status87-statusfp-statusfp2"></a>_status87, _statusfp, _statusfp2

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

Для **_status87** и **_statusfp**, биты в значение, которое возвращается указывают состояний с плавающей запятой. См. в число с плавающей запятой. H включаемый файл для определения битов, возвращаемых **_statusfp**. Многие математические библиотечные функции изменяют слово состояния операций с плавающей запятой с непредсказуемыми результатами. Можно изменить порядок, объединения и исключить операций с плавающей запятой вокруг вызовов для оптимизации **_status87**, **_statusfp**и соответствующие функции. Используйте параметр компилятора [/Od (выключение (отладчика))](../../build/reference/od-disable-debug.md) или директиву pragma [fenv_access](../../preprocessor/fenv-access.md) для исключения оптимизаций, изменяющих порядок операций с плавающей запятой. Возврат значений из **_clearfp** и **_statusfp**, а также возвращаемые параметры **_statusfp2**, более надежны, если выполняется меньше операций с плавающей запятой между известными слова состояний с плавающей запятой.

## <a name="remarks"></a>Примечания

**_Statusfp** функция получает слово состояния с плавающей запятой. Слово состояния содержит состояние модуля операций с плавающей запятой и другие условия, обнаруженные обработчиком исключений операций с плавающей запятой, — например, переполнение стека или потеря точности. Перед возвращением содержимого слова состояния проверяются немаскированные исключения. Это означает, что вызывающая функция информируется о необработанных исключениях. На x86 платформ, **_statusfp** возвращает комбинацию x87 и состояний с плавающей запятой SSE2. На платформах x64 возвращаемое состояние основывается на состоянии MXCSR SSE. На платформах ARM **_statusfp** возвращает состояние из регистра fpscr.

**_statusfp** — это независимая от платформы, переносимая версия **_status87**. Она идентична **_status87** на платформах Intel (x86) и также поддерживается x64 и платформы ARM. Чтобы убедиться, что ваш код с плавающей запятой является переносимым на все архитектуры, используйте **_statusfp**. Если только x x86 платформ, можно использовать либо **_status87** или **_statusfp**.

Мы рекомендуем **_statusfp2** для chips (например, Pentium IV), которые имеют x87 и процессор с плавающей запятой SSE2. Для **_statusfp2**, адреса заполняются с использованием слова состояния для x87 или процессора с плавающей запятой SSE2. Микросхем, поддерживающих x87 и процессоры с плавающей запятой SSE2, EM_AMBIGUOUS устанавливается значение 1, если **_statusfp** или **_controlfp** используется и действие было неоднозначным, поскольку он может ссылаться на x87 или SSE2 слово состояния. **_Statusfp2** функция поддерживается только на x86 платформ.

Эти функции не используются для [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) так, как среда CLR (CLR) поддерживает только точность чисел с плавающей запятой по умолчанию.

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
