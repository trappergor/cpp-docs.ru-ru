---
title: gets_s, _getws_s
ms.date: 11/04/2016
apiname:
- _getws_s
- gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getws_s
- gets_s
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
ms.openlocfilehash: f71fafceaf1974bc5ff736ff175a67cf6c924ee6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482905"
---
# <a name="getss-getwss"></a>gets_s, _getws_s

Получает строку из **stdin** потока. Это версии функций [gets, _getws](../../c-runtime-library/gets-getws.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
char *gets_s(
   char *buffer,
   size_t sizeInCharacters
);
wchar_t *_getws_s(
   wchar_t *buffer,
   size_t sizeInCharacters
);
```

```cpp
template <size_t size>
char *gets_s( char (&buffer)[size] ); // C++ only

template <size_t size>
wchar_t *_getws_s( wchar_t (&buffer)[size] ); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения входной строки.

*sizeInCharacters*<br/>
Размер буфера.

## <a name="return-value"></a>Возвращаемое значение

Возвращает *буфера* при успешном выполнении. Указатель **NULL** указывает на ошибку или конец файла. Используйте [ferror](ferror.md) или [feof](feof.md) для определения того, что именно произошло.

## <a name="remarks"></a>Примечания

**Gets_s** функция считывает строку из стандартного входного потока **stdin** и сохраняет его в *буфера*. Строка состоит из всех символов до первого символа новой строки ("\n"). **gets_s** затем заменяет символ новой строки нуль-символом («\0») перед возвратом строки. Напротив **fgets_s** функция сохраняет символ новой строки.

Если первым считан символ является символом конец файла, символ null хранится в начале *буфера* и **NULL** возвращается.

**_getws_s** — это двухбайтовая версия **gets_s**; ее аргумент и возвращаемое значение представляют собой строки расширенных символов.

Если *буфера* — **NULL** или *sizeInCharacters* меньше или равно нулю, или если буфер слишком мал, чтобы вместить входную строку и завершающий нуль-символ, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **NULL** и устанавливают параметр errno в **ERANGE**.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**gets_s**|\<stdio.h>|
|**_getws_s**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_gets_s.c
// This program retrieves a string from the stdin and
// prints the same string to the console.

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets_s( line, 20 );
   printf( "The line entered was: %s\n", line );
}
```

```Input
Hello there!
```

```Output
The line entered was: Hello there!
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
