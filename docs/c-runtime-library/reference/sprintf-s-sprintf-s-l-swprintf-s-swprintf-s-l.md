---
title: sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
ms.date: 11/04/2016
apiname:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- swprintf_s
- sprintf_s
- stdio/sprintf_s
- stdio/swprintf_s
- stdio/_sprintf_s_l
- stdio/_swprintf_s_l
- _sprintf_s_l
- _swprintf_s_l
helpviewer_keywords:
- stprintf_s function
- stprintf_s_l function
- swprintf_s_l function
- sprintf_s function
- swprintf_s function
- _swprintf_s_l function
- sprintf_s_l function
- _stprintf_s_l function
- _stprintf_s function
- _sprintf_s_l function
- formatted text [C++]
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
ms.openlocfilehash: 4d4bec339caccf9b0843afada4b56b435243dd11
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210891"
---
# <a name="sprintfs-sprintfsl-swprintfs-swprintfsl"></a>sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l

Запись форматированных данных в строку. Это версии функций [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
int sprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   ...
);
int _sprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   locale_t locale,
   ...
);
int swprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   ...
);
int _swprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   locale_t locale,
   ...
);
template <size_t size>
int sprintf_s(
   char (&buffer)[size],
   const char *format,
   ...
); // C++ only
template <size_t size>
int swprintf_s(
   wchar_t (&buffer)[size],
   const wchar_t *format,
   ...
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения выходных данных

*sizeOfBuffer*<br/>
Наибольшее число символов для хранения.

*format*<br/>
Строка управления форматом

*...*<br/>
Необязательные аргументы для форматирования

*locale*<br/>
Используемый языковой стандарт.

Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Возвращаемое значение

Число записанных символов, или значение -1, если произошла ошибка. Если *буфера* или *формат* является пустым указателем, **sprintf_s** и **swprintf_s** возвращают значение -1 и задайте **errno**для **EINVAL**.

**sprintf_s** возвращает число байтов, сохраненных в *буфера*, не считая завершающий нуль-символ. **swprintf_s** возвращает число расширенных символов, сохраненных в *буфера*, без учета завершающего расширенного символа null.

## <a name="remarks"></a>Примечания

**Sprintf_s** функция форматирует и сохраняет серию символов и значений в *буфера*. Каждый *аргумент* (при наличии) преобразуется и выводится согласно соответствующей спецификации формата в *формат*. Формат состоит из обычных символов и имеет ту же форму и функциональные возможности, что и аргумент *format* для [printf](printf-printf-l-wprintf-wprintf-l.md). После последнего написанного символа добавляется символ null. Если производится копирование между перекрывающимися строками, поведение не определено.

Основное различие между **sprintf_s** и [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) является то, что **sprintf_s** проверяет строку форматирования на наличие допустимых символов форматирования, тогда как [ sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) только проверяет строка формата или буфер **NULL** указатели. Если проверка завершается с ошибкой, то вызывается обработчик недопустимого параметра, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает **errno** для **EINVAL**.

Основное различие между **sprintf_s** и [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) является то, что **sprintf_s** принимает параметр длины, определяющий размер выходного буфера в символах. Если буфер слишком мал для форматированного текста, включая завершающий символ null, то буфера присваивается пустая строка путем размещения символа null в *буфера*[0], и вызывается обработчик недопустимого параметра. В отличие от **_snprintf**, **sprintf_s** гарантирует, что буфер будет нулевым символом Если размер буфера не равен нулю.

**swprintf_s** — это двухбайтовая версия **sprintf_s**; аргументы указателя для **swprintf_s** представляют собой строки расширенных символов. Определение кодировки ошибок в **swprintf_s** может отличаться от отчетов, в **sprintf_s**. Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.

В C++ использование этих функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера, что исключает необходимость указания аргумента с размером буфера, а также они могут автоматически заменять более старые незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Существуют версии **sprintf_s** , обеспечивают дополнительный контроль над происходящим, если буфер слишком мал. Дополнительные сведения см. в разделе [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_s**|**sprintf_s**|**sprintf_s**|**swprintf_s**|
|**_stprintf_s_l**|**_sprintf_s_l**|**_sprintf_s_l**|**_swprintf_s_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**sprintf_s**, **_sprintf_s_l**|C: \<stdio.h><br /><br /> C++: \<cstdio> или \<stdio.h>|
|**swprintf_s**, **_swprintf_s_l**|C: \<stdio.h> или \<wchar.h><br /><br /> C++: \<cstdio>, \<cwchar>, \<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_sprintf_s.c
// This program uses sprintf_s to format various
// data and place them in the string named buffer.
//

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );

   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>Пример

```C
// crt_swprintf_s.c
// wide character example
// also demonstrates swprintf_s returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf_s fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[Функции vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
