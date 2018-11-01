---
title: _cprintf, _cprintf_l, _cwprintf, _cwprintf_l
ms.date: 11/04/2016
apiname:
- _cwprintf_l
- _cprintf_l
- _cwprintf
- _cprintf
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
- _cwprintf
- cwprintf
- tcprintf
- _tcprintf
- _cprintf
- cwprintf_l
- tcprintf_l
- _tcprintf_l
- cprintf_l
- _cprintf_l
- _cwprintf_l
helpviewer_keywords:
- _cprintf_l function
- _cwprintf_l function
- cwprintf function
- cprintf_l function
- characters, printing to console
- printing characters to console
- _tcprintf_l function
- tcprintf function
- _tcprintf function
- tcprintf_l function
- _cwprintf function
- cwprintf_l function
- _cprintf function
ms.assetid: 67ffefd4-45b3-4be0-9833-d8d26ac7c4e2
ms.openlocfilehash: ce1913012ee37b19e15602daaa4eea042a69a3de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534047"
---
# <a name="cprintf-cprintfl-cwprintf-cwprintfl"></a>_cprintf, _cprintf_l, _cwprintf, _cwprintf_l

Форматируют и выводят данные на консоль. Доступны более безопасные версии; см. раздел [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _cprintf(
   const char * format [, argument_list]
);
int _cprintf_l(
   const char * format,
   locale_t locale [, argument_list]
);
int _cwprintf(
   const wchar * format [, argument_list]
);
int _cwprintf_l(
   const wchar * format,
   locale_t locale [, argument_list]
);
```

### <a name="parameters"></a>Параметры

*format*<br/>
Строка управления форматом.

*argument_list*<br/>
Необязательные параметры для строки формата.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Число отображаемых символов.

## <a name="remarks"></a>Примечания

Эти функции форматируют и выводят последовательности символов и значений напрямую на консоль, используя **_putch** функция (**_putwch** для **_cwprintf**) для вывода символов . Каждый аргумент в *argument_list* (при наличии) преобразуется и выводится согласно соответствующей спецификации формата в *формат*. *Формат* использует аргумент [синтаксис описания для функции printf и wprintf формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). В отличие от **fprintf**, **printf**, и **sprintf** функции, ни **_cprintf** , ни **_cwprintf**преобразование символов перевода строки в сочетания символов возврата строки (CR-LF), веб-канал каретки при выводе.

Важное отличие заключается в том, что **_cwprintf** показывает символы Юникода при использовании в Windows. В отличие от **_cprintf**, **_cwprintf** использует текущие настройки языкового стандарта консоли.

Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.

**_cprintf** проверяет *формат* параметра. Если *формат* является пустым указателем, функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает **errno** для **EINVAL**.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf**|**_cprintf**|**_cprintf**|**_cwprintf**|
|**_tcprintf_l**|**_cprintf_l**|**_cprintf_l**|**_cwprintf_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cprintf**, **_cprintf_l**|\<conio.h>|
|**_cwprintf**, **_cwprintf_l**|\<conio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_cprintf.c
// compile with: /c
// This program displays some variables to the console.

#include <conio.h>

int main( void )
{
    int         i = -16,
                h = 29;
    unsigned    u = 62511;
    char        c = 'A';
    char        s[] = "Test";

    // Note that console output does not translate \n as
    // standard output does. Use \r\n instead.
    //
    _cprintf( "%d  %.4x  %u  %c %s\r\n", i, h, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>См. также

[Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)<br/>
[Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
