---
title: _printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l
ms.date: 11/04/2016
api_name:
- _printf_p
- _wprintf_p
- _printf_p_l
- _wprintf_p_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wprintf_p
- _wprintf_p
- printf_p_l
- _printf_p
- printf_p
- _wprintf_p_l
- _printf_p_l
- wprintf_p_l
helpviewer_keywords:
- printf_p function
- printf_p_l function
- wprintf_p function
- wprintf_p_l function
- _tprintf_p_l function
- _wprintf_p function
- _wprintf_p_l function
- _printf_p function
- tprintf_p_l function
- _printf_p_l function
ms.assetid: 1b7e9ef9-a069-45db-af9d-c2730168322e
ms.openlocfilehash: 555739fbcdd3503461d7b831660a94602f244aa3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950269"
---
# <a name="_printf_p-_printf_p_l-_wprintf_p-_wprintf_p_l"></a>_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l

Выводит форматированные выходные данные в стандартный поток вывода и обеспечивает задание порядка, в котором параметры используются в строке форматирования.

## <a name="syntax"></a>Синтаксис

```C
int _printf_p(
   const char *format [,
   argument]...
);
int _printf_p_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int _wprintf_p(
   const wchar_t *format [,
   argument]...
);
int _wprintf_p_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Параметры

*format*<br/>
Формат объекта.

*параметр*<br/>
Необязательные аргументы.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает число выведенных символов или отрицательное значение в случае ошибки.

## <a name="remarks"></a>Примечания

Функция **_printf_p** форматирует и выводит последовательность символов и значений в стандартный выходной поток, **stdout**. Если аргументы следуют за строкой *формата* , строка *формата* должна содержать спецификации, определяющие формат выходных данных для аргументов (см. раздел [printf_p позиционированные параметры](../../c-runtime-library/printf-p-positional-parameters.md)).

Различие между **_printf_p** и **printf_s** заключается в том, что **_printf_p** поддерживает позиционированные параметры, позволяющие указать порядок, в котором аргументы используются в строке формата. Дополнительные сведения см. в разделе [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md).

**_wprintf_p** — это версия **_printf_p**для расширенных символов; они ведут себя одинаково, если поток открыт в режиме ANSI. **_printf_p** в настоящее время не поддерживает вывод в поток Юникода.

Версии этих функций с суффиксом **_l** идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо локали текущего потока.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем.

Если параметр *Format* или *Argument* имеет **значение NULL**или строка формата содержит недопустимые символы форматирования, функции **_printf_p** и **_wprintf_p** вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров. ](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция **возвращает значение-1 и устанавливает** для **еинвал**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tprintf_p**|**_printf_p**|**_printf_p**|**_wprintf_p**|
|**_tprintf_p_l**|**_printf_p_l**|**_printf_p_l**|**_wprintf_p_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_printf_p**, **_printf_p_l**|\<stdio.h>|
|**_wprintf_p**, **_wprintf_p_l**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальная платформа Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**и **stderr**, должны быть перенаправляться до того, как функции времени выполнения C смогут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_printf_p.c
// This program uses the _printf_p and _wprintf_p
// functions to choose the order in which parameters
// are used.

#include <stdio.h>

int main( void )
{
   // Positional arguments
   _printf_p( "Specifying the order: %2$s %3$s %1$s %4$s %5$s.\n",
              "little", "I'm", "a", "tea", "pot");

   // Resume arguments
   _wprintf_p( L"Reusing arguments: %1$d %1$d %1$d %1$d\n", 10);

   // Width argument
   _printf_p("Width specifiers: %1$*2$s", "Hello\n", 10);
}
```

```Output
Specifying the order: I'm a little tea pot.
Reusing arguments: 10 10 10 10
Width specifiers:     Hello
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)<br/>
[Функции vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
