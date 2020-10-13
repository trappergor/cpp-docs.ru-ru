---
title: sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
ms.date: 06/23/2020
api_name:
- __swprintf_l
- sprintf
- _sprintf_l
- _swprintf_l
- swprintf
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _stprintf_l
- __swprintf_l
- sprintf_l
- swprintf
- _sprintf_l
- sprintf
- _stprintf
- stprintf_l
helpviewer_keywords:
- _swprintf_l function
- _stprintf function
- __swprintf_l function
- stprintf function
- sprintf function
- _sprintf_l function
- _stprintf_l function
- swprintf function
- strings [C++], writing to
- _CRT_NON_CONFORMING_SWPRINTFS
- swprintf_l function
- stprintf_l function
- sprintf_l function
- formatted text [C++]
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
ms.openlocfilehash: da3c5b3660b481fd3a7140adbc236f44cd51f37e
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008827"
---
# <a name="sprintf-_sprintf_l-swprintf-_swprintf_l-__swprintf_l"></a>sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l

Запись форматированных данных в строку. Существуют более безопасные версии этих функций; см. раздел [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md). Безопасные версии **swprintf** и **_swprintf_l** имеют размер буфера в качестве параметра.

## <a name="syntax"></a>Синтаксис

```C
int sprintf(
   char *buffer,
   const char *format [,
   argument] ...
);
int _sprintf_l(
   char *buffer,
   const char *format,
   locale_t locale [,
   argument] ...
);
int swprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument]...
);
int _swprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
int __swprintf_l(
   wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int sprintf(
   char (&buffer)[size],
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _sprintf_l(
   char (&buffer)[size],
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>Параметры

*двойной*<br/>
Место хранения выходных данных

*count*<br/>
Максимальное количество символов, которое может хранить эта функция в версии Юникод.

*format*<br/>
Строка управления форматом

*argument*<br/>
Необязательные аргументы

*locale*<br/>
Используемый языковой стандарт.

Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Возвращаемое значение

Число записанных символов или-1, если произошла ошибка. Если *buffer* или *Format* является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают-1 **и устанавливают для** **еинвал**значение.

**sprintf** возвращает число байтов, хранящихся в *буфере*, без учета завершающего нуль символа. **swprintf** возвращает количество расширенных символов, хранящихся в *буфере*, без учета завершающего расширенного символа null.

## <a name="remarks"></a>Комментарии

Функция **sprintf** форматирует и сохраняет последовательность символов и значений в *буфере*. Каждый *аргумент* (при его наличии) преобразуется и выводится в соответствии с соответствующей спецификацией формата в *формате*. Формат состоит из обычных символов и имеет ту же форму и функцию, что и аргумент *Format* для [printf](printf-printf-l-wprintf-wprintf-l.md). После последнего написанного символа добавляется символ null. Если копирование производится между перекрывающимися строками, поведение не определено.

> [!IMPORTANT]
> С помощью **sprintf**невозможно ограничить число записанных символов. Это означает, что код, использующий **sprintf** , уязвим для переполнения буфера. Рассмотрите возможность использования функции [_snprintf](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), которая указывает максимальное число символов для записи в *буфер*, или используйте [_scprintf](scprintf-scprintf-l-scwprintf-scwprintf-l.md) , чтобы определить, сколько требуется буфера. Кроме того, убедитесь, что *Формат* не является определяемой пользователем строкой.

**swprintf** — это версия **sprintf**для расширенных символов; аргументы-указатели для **swprintf** являются строками расширенных символов. Обнаружение ошибок кодирования в **swprintf** может отличаться от **sprintf**. поведение **swprintf** и **fwprintf** идентично, за исключением того, что **swprintf** записывает выходные данные в строку, а не в назначение типа **File**, а **swprintf** требует параметр *Count* , чтобы указать максимальное число символов для записи. Версии этих функций с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.

**swprintf** соответствует стандарту ISO C, для которого требуется второй параметр, *count*, типа **size_t**. Чтобы принудительно использовать старое нестандартное поведение, определите **_CRT_NON_CONFORMING_SWPRINTFS**. В будущей версии старое поведение может быть удалено, поэтому код необходимо изменить в соответствии с новым стандартным поведением.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf**|**sprintf**|**sprintf**|**_swprintf**|
|**_stprintf_l**|**_sprintf_l**|**_sprintf_l**|**__swprintf_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**sprintf**, **_sprintf_l**|\<stdio.h>|
|**swprintf**, **_swprintf_l**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example-use-sprintf-to-format-data"></a>Пример. Использование sprintf для форматирования данных

```C
// crt_sprintf.c
// compile with: /W3
// This program uses sprintf to format various
// data and place them in the string named buffer.

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996
   // Note: sprintf is deprecated; consider using sprintf_s instead

   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );
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

## <a name="example-error-code-handling"></a>Пример: обработка кода ошибки

```C
// crt_swprintf.c
// wide character example
// also demonstrates swprintf returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>См. также статью

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[Функции vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
