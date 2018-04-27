---
title: snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _snwprintf
- _snprintf
- _snprintf_l
- _snwprintf_l
- snprintf
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
dev_langs:
- C++
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
caps.latest.revision: 35
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8c47f3d1a65d9a48f0a76cd6dd9876d799e583f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="snprintf-snprintf-snprintfl-snwprintf-snwprintfl"></a>snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
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

*buffer*<br/>
Место хранения выходных данных.

*count*<br/>
Наибольшее число символов для хранения.

*format*<br/>
Строка управления форматом.

*Аргумент*<br/>
Необязательные аргументы.

*locale*<br/>
Используемый языковой стандарт.

Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Возвращаемое значение

Разрешить **len** будет длиной строки форматированных данных, не включая конечное значение null. Оба **len** и *число* в байтах для **snprintf** и **_snprintf**, расширенных символах для **_snwprintf**.

Для всех функций Если **len** < *число*, **len** символы хранятся в *буфера*, добавляется символ конца строки и **len** возвращается.

**Snprintf** функция усекает выходные данные при **len** больше или равно *число*, помещая знак завершения null в `buffer[count-1]`. Возвращаемое значение — **len**, количество символов, которые стали бы выходными данными при *число* был достаточно велик. **Snprintf** функция возвращает отрицательное значение, если возникает ошибка кодирования.

Для всех функций, кроме **snprintf**, если **len** = *число*, **len** символы хранятся в  *буфер*, знак null не добавляется, и **len** возвращается. Если **len** > *число*, *число* символы хранятся в *буфера*, знак завершения null, добавленных и отрицательный результат Возвращаемое значение отсутствует.

Если *буфера* является указателем null и *число* равен нулю, **len** возвращается как число символов, необходимых для форматирования выходных данных, не включая конечное значение null. Для выполнения успешного вызова с тем же *аргумент* и *языкового стандарта* параметров, выделите буфер, содержащий по крайней мере **len** + 1 символов.

Если *буфера* является указателем null и *число* имеет ненулевое значение, или если *формат* является пустым указателем, вызывается обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают значение -1 и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Snprintf** функции и **_snprintf** семейство функций форматируют и сохраняют *число* или меньше символов в *буфера*. **Snprintf** функция всегда хранит завершающий символ null, усечение выходных данных, при необходимости. **_Snprintf** семейство функций только добавляет знак завершения null, если длина форматированной строки строго меньше, чем *число* символов. Каждый *аргумент* (если есть) преобразуется и выводится согласно соответствующей спецификацией формата в *формат*. Формат состоит из обычных символов и имеет те же форму и функциональные возможности, что *формат* аргумент для [printf](printf-printf-l-wprintf-wprintf-l.md). Если копирование производится между перекрывающимися строками, поведение не определено.

> [!IMPORTANT]
> Убедитесь, что *format* не является строкой, определяемой пользователем. Поскольку **_snprintf** функции не гарантируют завершение знаком NULL, в частности, если возвращаемое значение равно *число*— убедитесь, что Далее следует код, добавляющий знак завершения null. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Начиная с UCRT в Visual Studio 2015 и Windows 10 **snprintf** больше не идентичен **_snprintf**. **Snprintf** поведение функции — теперь соответствует стандарту C99.

**_snwprintf** — это двухбайтовая версия **_snprintf**; аргументы указателя для **_snwprintf** представляют собой строки расширенных символов. Определение кодировки ошибок в **_snwprintf** могут отличаться от того, **_snprintf**. **_snwprintf**, так же, как **swprintf**, записывает выходные данные в строку вместо назначения типа **ФАЙЛ**.

Версии этих функций, имеющих **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают их более новые и безопасные аналоги. Для получения дополнительной информации см. [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sntprintf**|**_snprintf**|**_snprintf**|**_snwprintf**|
|**_sntprintf_l**|**_snprintf_l**|**_snprintf_l**|**_snwprintf_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**snprintf**, **_snprintf**, **_snprintf_l**|\<stdio.h>|
|**_snwprintf**, **_snwprintf_l**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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
   /* !subtract one to prevent "squeezing out" the terminal nul! */
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
      /* !store nul because _snprintf doesn't necessarily (if the string
       * fits without the terminal nul, but not with it)!
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
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[Функции vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
