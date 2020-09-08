---
title: snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
description: Справочник по API для snprintf, _snprintf, _snprintf_l, _snwprintf и _снвпринтф_; который записывает форматированные данные в строку.
ms.date: 08/27/2020
api_name:
- _snwprintf
- _snprintf
- _snprintf_l
- _snwprintf_l
- snprintf
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _snprintf
- snprintf_l
- snwprintf_l
- sntprintf
- snprintf
- _sntprintf
- _sntprintf_l
- sntprintf_l
- snwprintf
- _snprintf_l
- _snwprintf
- _snwprintf_l
helpviewer_keywords:
- snwprintf_l function
- sntprintf_l function
- snprintf_l function
- _snwprintf_l function
- _sntprintf_l function
- _snwprintf function
- _snprintf function
- _sntprintf function
- _snprintf_l function
- snwprintf function
- snprintf function
- sntprintf function
- formatted text [C++]
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
ms.openlocfilehash: 9a851f08e50d11d3716ea59e00e5e9028b6cd6d5
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556116"
---
# <a name="snprintf-_snprintf-_snprintf_l-_snwprintf-_snwprintf_l"></a>snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l

Записывает форматированные данные в строку. Существуют более безопасные версии этих функций; см. статью [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

## <a name="syntax"></a>Синтаксис

```C
int snprintf(
   char *buffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf(
   char *buffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
);
int _snwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument] ...
);
int _snwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int _snprintf(
   char (&buffer)[size],
   size_t count,
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>Параметры

*двойной*<br/>
Место хранения выходных данных.

*count*<br/>
Наибольшее число символов для хранения.

*format*<br/>
Строка управления форматом.

*argument*<br/>
Необязательные аргументы.

*locale*<br/>
Используемый языковой стандарт.

Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Возвращаемое значение

Пусть **Длина** строки форматированных данных не включает завершающее значение null. И **Len** , и **Count** — это число символов для **snprintf** и **_snprintf**, а также количество расширенных символов для **_snwprintf**.

Для всех функций, если параметр **Len**  <  *Count*, символы **Len** хранятся в *буфере*, добавляется завершающий символ NULL и возвращается **Len** .

Функция **snprintf** усекает выходные данные, если **ДЛСТР** больше или равна *Count*, помещая признак конца со значением NULL в `buffer[count-1]` . Возвращаемое значение — **Len**, количество символов, которое было бы выведено, если *Счетчик* был достаточно большим. Функция **snprintf** возвращает отрицательное значение при возникновении ошибки кодирования.

Для всех функций, кроме **snprintf**, если **значение len**  =  *count*, то символы **Len** хранятся в *буфере*, не добавляется символ конца null и возвращается **Len** . Если значение **Len**  >  *Count*, символы *Count* хранятся в *буфере*, не добавляется символ конца null и возвращается отрицательное.

Если *buffer* является пустым указателем, а *Count* равен нулю, то функция **Len** возвращается как количество символов, необходимых для форматирования выходных данных, не включая завершающее значение null. Чтобы выполнить успешный вызов с теми же *аргументами* и параметрами *локали* , выделите буфер, содержащий не менее **Len** + 1 символов.

Если *buffer* является пустым указателем, а *Count* имеет ненулевое значение или если *Format* является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают-1 **и устанавливают для** **еинвал**значение.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **snprintf** и семейство функций **_snprintf** , *а также формат хранения или* меньше символов в *буфере*. Функция **snprintf** всегда сохраняет завершающий нуль-символ, при необходимости обрезая выходные данные. **_Snprintf** семейство функций добавляет завершающий нуль-символ, если длина форматированной строки строго меньше символов *Count* . Каждый *аргумент* (при его наличии) преобразуется и выводится в соответствии с соответствующей спецификацией формата в *формате*. Формат состоит из обычных символов и имеет ту же форму и функцию, что и аргумент *Format* для [printf](printf-printf-l-wprintf-wprintf-l.md). Если копирование производится между перекрывающимися строками, поведение не определено.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем. Поскольку функции **_snprintf** не гарантируют нулевое завершение (в частности, если возвращаемое значение *Count*), следует убедиться, что за ними следует код, который добавляет символ конца null. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

Начиная с UCRT в Visual Studio 2015 и Windows 10, **snprintf** больше не идентичен **_snprintf**. Поведение функции **snprintf** теперь соответствует стандартам C99 Standard.

**_snwprintf** — это версия **_snprintf**для расширенных символов; аргументы-указатели для **_snwprintf** являются строками расширенных символов. Обнаружение ошибок кодирования в **_snwprintf** может отличаться от **_snprintf**. **_snwprintf**, как и **swprintf**, записывает выходные данные в строку вместо назначения **файла**типа.

Версии этих функций с суффиксом **_l** идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо локали текущего потока.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают их более новые и безопасные аналоги. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sntprintf**|**_snprintf**|**_snprintf**|**_snwprintf**|
|**_sntprintf_l**|**_snprintf_l**|**_snprintf_l**|**_snwprintf_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**snprintf**, **_snprintf**  **_snprintf_l**|\<stdio.h>|
|**_snwprintf**, **_snwprintf_l**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_snprintf.c
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

#if !defined(__cplusplus)
typedef int bool;
const bool true = 1;
const bool false = 0;
#endif

#define FAIL 0 // change to 1 and see what happens

int main(void)
{
   char buffer[200];
   const static char s[] = "computer"
#if FAIL
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
#endif
   ;
   const char c = 'l';
   const int i = 35;
#if FAIL
   const double fp = 1e300; // doesn't fit in the buffer
#else
   const double fp = 1.7320534;
#endif
   /* !subtract one to prevent "squeezing out" the terminal null! */
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;
   int bufferUsed = 0;
   int bufferLeft = bufferSize - bufferUsed;
   bool bSuccess = true;
   buffer[0] = 0;

   /* Format and print various data: */

   if (bufferLeft > 0)
   {
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],
      bufferLeft, "   String: %s\n", s ); // C4996
      // Note: _snprintf is deprecated; consider _snprintf_s instead
      if (bSuccess = (perElementBufferUsed >= 0))
      {
         bufferUsed += perElementBufferUsed;
         bufferLeft -= perElementBufferUsed;
         if (bufferLeft > 0)
         {
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],
            bufferLeft, "   Character: %c\n", c ); // C4996
            if (bSuccess = (perElementBufferUsed >= 0))
            {
               bufferUsed += perElementBufferUsed;
               bufferLeft -= perElementBufferUsed;
               if (bufferLeft > 0)
               {
                  int perElementBufferUsed = _snprintf(&buffer
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996
                  if (bSuccess = (perElementBufferUsed >= 0))
                  {
                     bufferUsed += perElementBufferUsed;
                     bufferLeft -= perElementBufferUsed;
                     if (bufferLeft > 0)
                     {
                        int perElementBufferUsed = _snprintf(&buffer
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996
                        if (bSuccess = (perElementBufferUsed >= 0))
                        {
                           bufferUsed += perElementBufferUsed;
                        }
                     }
                  }
               }
            }
         }
      }
   }

   if (!bSuccess)
   {
      printf("%s\n", "failure");
   }
   else
   {
      /* !store null because _snprintf doesn't necessarily (if the string
       * fits without the terminal null, but not with it)!
       * bufferUsed might be as large as bufferSize, which normally is
       * like going one element beyond a buffer, but in this case
       * subtracted one from bufferSize, so we're ok.
       */
      buffer[bufferUsed] = 0;
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );
   }
   return EXIT_SUCCESS;
}
```

```Output
Output:
   String: computer
   Character: l
   Integer: 35
   Real: 1.732053

character count = 69
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[Функции vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
