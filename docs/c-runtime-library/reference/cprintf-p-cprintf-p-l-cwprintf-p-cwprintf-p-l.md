---
title: _cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l
ms.date: 11/04/2016
apiname:
- _cprintf_p_l
- _cwprintf_p_l
- _cwprintf_p
- _cprintf_p
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
- cprintf_p
- cwprintf_p
- tcprintf_p
- _cwprintf_p_l
- _cprintf_p
- csprintf_p_l
- _cprintf_p_l
- _cwprintf_p
- _tcprintf_p
- cprintf_p_l
helpviewer_keywords:
- _cwprintf_p_l function
- cwprintf_p function
- tcprintf_p_l function
- cprintf_p_l function
- _tcprintf_p function
- _tcprintf_p_l function
- _cprintf_p function
- _cprintf_p_l function
- cwprintf_p_l function
- _cwprintf_p function
- tcprintf_p function
- cprintf_p function
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
ms.openlocfilehash: ef4ac6a89749c2784e4935fcf83810e81b61ae11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658462"
---
# <a name="cprintfp-cprintfpl-cwprintfp-cwprintfpl"></a>_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l

Форматирует и производит вывод на консоль, поддерживает позиционные параметры в строке форматирования.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _cprintf_p(
   const char * format [,
   argument] ...
);
int _cprintf_p_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_p(
   const wchar * format [,
   argument] ...
);
int _cwprintf_p_l(
   const wchar * format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Параметры

*format*<br/>
Строка управления форматом.

*Аргумент*<br/>
Необязательные параметры.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Число выведенных символов или отрицательное значение в случае ошибки.

## <a name="remarks"></a>Примечания

Эти функции форматируют и выводят последовательности символов и значений напрямую на консоль, используя **_putch** и **_putwch** функции для вывода символов. Каждый *аргумент* (при наличии) преобразуется и выводится согласно соответствующей спецификации формата в *формат*. Формат имеет те же форму и функционировать как *формат* параметр для [printf_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) функции. Разница между **_cprintf_p** и **cprintf_s** является то, что **_cprintf_p** поддерживает позиционные параметры, позволяющие определить порядок, в котором аргументы используется в строке формата. Дополнительные сведения см. в разделе [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md).

В отличие от **fprintf_p**, **printf_p**, и **sprintf_p** функции, ни **_cprintf_p** , ни **_cwprintf_p** преобразование символов перевода строки в сочетания символов возврата строки (CR-LF), веб-канал каретки при выводе. Важное отличие заключается в том, что **_cwprintf_p** показывает символы Юникода при использовании в Windows NT. В отличие от **_cprintf_p**, **_cwprintf_p** использует текущие настройки языкового стандарта консоли.

Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем.

Кроме того, такие как **_cprintf_s** и **_cwprintf_s**, они проверяют входной указатель и строку формата. Если *формат* или *аргумент* являются **NULL**, или строка форматирования содержит недопустимые символы форматирования, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают значение -1 и задайте **errno** для **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_p**|**_cprintf_p**|**_cprintf_p**|**_cwprintf_p**|
|**_tcprintf_p_l**|**_cprintf_p_l**|**_cprintf_p_l**|**_cwprintf_p_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cprintf_p**, **_cprintf_p_l**|\<conio.h>|
|**_cwprintf_p**, **_cwprintf_p_l**|\<conio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_cprintf_p.c
// This program displays some variables to the console
// using the _cprintf_p function.

#include <conio.h>

int main( void )
{
    int         i = -16,
                h = 29;
    unsigned    u = 62511;
    char        c = 'A';
    char        s[] = "Test";

    // Note that console output does not translate
    // \n as standard output does. Use \r\n instead.
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",
                h, i, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>См. также

[Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
