---
title: "vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsnprintf"
  - "_vsnprintf_l"
  - "_vsnwprintf"
  - "_vsnwprintf_l"
  - "_vsnprintf"
  - "_vsnprintf;"
  - "vsnprintf; _vsnprintf"
  - "_vsnwprintf;"
  - "_vsnprintf_l;"
  - "_vsnwprintf_l;"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ntoskrnl.exe"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf"
  - "_vsnwprintf"
  - "_vsntprintf"
  - "vsnprintf"
  - "stdio/vsnprintf"
  - "stdio/_vsnprintf"
  - "stdio/_vsnprintf_l"
  - "stdio/_vsnwprintf"
  - "stdio/_vsnwprintf_l"
  - "_vsnprintf_l"
  - "_vsnwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vsntprintf - функция"
  - "_vsnwprintf_l - функция"
  - "vsnwprintf_l - функция"
  - "vsntprintf_l - функция"
  - "_vsntprintf - функция"
  - "_vsnprintf_l - функция"
  - "vsnprintf - функция"
  - "_vsntprintf_l - функция"
  - "vsnprintf_l - функция"
  - "_vsnwprintf - функция"
  - "_vsnprintf - функция"
  - "форматированный текст [C++]"
  - "vsnwprintf - функция"
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывают форматированные выходные данные с помощью указателя на список аргументов. Существуют более безопасные версии этих функций; см. статью [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).  
  
## Синтаксис  
  
```  
int vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Место хранения выходных данных.  
  
 `count`  
 Наибольшее количество символов для записи.  
  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  
  
## Возвращаемое значение  
 `vsnprintf` Функция возвращает число записанных символов, не считая завершающий символ null. Если размер буфера, заданный параметром `count` не является достаточно большим, чтобы содержать заданные выходные данные `format` и `argptr`, возвращаемое значение `vsnprintf` число символов, которые будут записаны, не считая символ null, если `count` были достаточно большой. Если возвращаемое значение больше, чем `count` \- 1, выходные данные будут усечены. Возвращаемое значение –1 указывает, что произошла ошибка кодирования.  
  
 Оба `_vsnprintf` и `_vsnwprintf` функции возвращают количество символов, записанных, если количество символов для записи меньше или равно `count`; Если количество символов для записи больше, чем `count`, эти функции, возвращаемое значение \-1, указывающее, что выходные данные будут усечены.  
  
 Эти функции возвращают значение отсутствует в конечное значение null ли одной записи или нет. Когда `count` равно нулю, возвращается значение — число символов, написать функции, не включая любой символ, завершающий. Можно использовать этот результат для выделения места в буфере строки и ее завершающий и затем вызвать функцию снова для заполнения буфера.  
  
 Если `format` является `NULL`, или если `buffer` имеет значение NULL и `count` не равен нулю, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если разрешается продолжать выполнение, эти функции возвращают \-1 и задают `errno` значение `EINVAL`.  
  
## Заметки  
 Каждая из этих функций принимает указатель на список аргументов, затем форматирует данные и записывает в память, на которую указывает `buffer`, не более следующего числа символов: `count`. Функция `vsnprintf` всегда записывает знак завершения NULL, даже если усекает выходные данные. При использовании `_vsnprintf` и `_vsnwprintf` буфер будет завершен знаком NULL, только если есть место в конце \(то есть если число символов для записи меньше `count`\).  
  
> [!IMPORTANT]
>  Чтобы избежать ряда угроз безопасности, убедитесь в том, что `format` не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Чтобы при вызове `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` и `_vsnwprintf_l` было достаточно места для знака завершения NULL, убедитесь в том, что значение параметра `count` строго меньше размера буфера, и инициализируйте буфер как NULL до вызова функции.  
>   
>  Так как `vsnprintf` всегда записывает завершающий `count` параметр может быть равен размеру буфера.  
  
 Начиная с UCRT в Visual Studio 2015 и Windows 10, `vsnprintf` больше не идентичен `_vsnprintf`.`vsnprintf` Функция соответствует стандарту C99; `_vnsprintf` сохраняется для обеспечения обратной совместимости со старым кодом, Visual Studio.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок \(C\)|Обязательный заголовок \(C\+\+\)|  
|------------------|----------------------------------|--------------------------------------|  
|`vsnprintf`, `_vsnprintf`, `_vsnprintf_l`|\<stdio.h\>|\<stdio.h\> или \<cstdio\>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h\> или \<wchar.h\>|\<stdio.h\>, \<wchar.h\>, \<cstdio\> или \<cwchar\>|  
  
 Функции `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` и `_vsnwprintf_l` относятся только к системам Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```c  
// crt_vsnwprintf.c  
// compile by using: cl /W3 crt_vsnwprintf.c  
  
// To turn off error C4996, define this symbol:  
#define _CRT_SECURE_NO_WARNINGS  
  
#include <stdio.h>  
#include <wtypes.h>  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(LPCWSTR formatstring, ...)  
{  
    int nSize = 0;  
    wchar_t buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead  
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996  
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize: 8, Подробности: Привет есть nSize: 9, Подробности: Привет существует! nSize: -1, Подробности: Привет существует!  
```  
  
 Изменения поведения в случае, если вместо этого использовать vsnprintf вместе с параметрами в узкий строковый.`count` Может быть весь размер буфера, и возвращаемое значение — количество символов, которые были бы записаны Если `count` был достаточно велик:  
  
## Пример  
  
```c  
// crt_vsnprintf.c  
// compile by using: cl /W4 crt_vsnprintf.c  
#include <stdio.h>  
#include <stdarg.h> // for va_list, va_start  
#include <string.h> // for memset  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(char* formatstring, ...)  
{  
    int nSize = 0;  
    char buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);  
    printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize: 8, Подробности: Привет есть nSize: 9, Подробности: Привет существует! nSize: 10, Подробности: Привет существует!  
```  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [Синтаксис описания формата: функции printf и wprintf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)