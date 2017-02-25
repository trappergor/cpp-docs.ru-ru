---
title: "vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsnwprintf_s"
  - "_vsnwprintf_s_l"
  - "_vsnprintf_s"
  - "vsnprintf_s"
  - "_vsnprintf_s_l"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf_s"
  - "_vsntprintf_s"
  - "_vsnwprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vsnprintf_s - функция"
  - "_vsnprintf_s_l - функция"
  - "_vsntprintf_s - функция"
  - "_vsntprintf_s_l - функция"
  - "_vsnwprintf_s - функция"
  - "_vsnwprintf_s_l - функция"
  - "форматированный текст [C++]"
  - "vsnprintf_s - функция"
  - "vsnprintf_s_l - функция"
  - "vsntprintf_s - функция"
  - "vsntprintf_s_l - функция"
  - "vsnwprintf_s - функция"
  - "vsnwprintf_s_l - функция"
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывают форматированные выходные данные с помощью указателя на список аргументов.  Здесь представлены версии [vsnprintf, \_vsnprintf, \_vsnprintf\_l, \_vsnwprintf, \_vsnwprintf\_l](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int _vsnprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Место хранения выходных данных.  
  
 `sizeOfBuffer`  
 Размер `buffer` для вывода, как количество символов.  
  
 `count`  
 Максимальное количество символов для записи \(не включая завершающий символ null\) или [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  
  
## Возвращаемое значение  
 `vsnprintf_s`,`_vsnprintf_s` и `_vsnwprintf_s` возвращают число записанных символов, не включая конечный символ null, или отрицательное значение, если произошла ошибка вывода.  `vsnprintf_s` идентична `_vsnprintf_s`.  `vsnprintf_s` добавлена для соответствия стандарту ANSI.  `_vnsprintf` поддерживается для совместимости с предыдущими версиями.  
  
 Если объем памяти, необходимый для хранения данных и конечного символа null, превышает `sizeOfBuffer`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md), если `count` не равен [\_TRUNCATE](../../c-runtime-library/truncate.md); в этом случае запись выполняется до тех пор, пока `buffer` не будет заполнен, и возвращается \-1.  Если после обработчика недопустимых параметров выполнение приложения продолжается, эти функции устанавливают значение параметра `buffer` равным пустой строке, устанавливают для `errno` значение `ERANGE` и возвращают \-1.  
  
 Если `buffer` или `format` является пустым \(`NULL`\) указателем или если значение параметра `count` меньше или равно нулю, то вызывается обработчик недопустимых параметров.  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  
  
### Условия возникновения ошибки  
  
|`Condition`|Return|`errno`|  
|-----------------|------------|-------------|  
|Параметр `buffer` имеет значение `NULL`|\-1|`EINVAL`|  
|Параметр `format` имеет значение `NULL`|\-1|`EINVAL`|  
|`count` \<\= 0|\-1|`EINVAL`|  
|значение `sizeOfBuffer` слишком мало \(и `count` \!\= `_TRUNCATE`\)|\-1 \(и `buffer` задается равным пустой строке\)|`ERANGE`|  
  
## Заметки  
 Каждая из этих функций принимает указатель на список аргументов, затем форматирует и записывает до `count` символов заданных данные в область памяти, на которую указывает `buffer`, и добавляет завершающий символ null.  
  
 Если значение параметра `count` равно [\_TRUNCATE](../../c-runtime-library/truncate.md), эти функции выполняют запись до тех пор, пока `buffer` не будет заполнен с учетом завершающего символа null.  Если вся строка \(с учетом завершающего символа null\) помещается в `buffer`, эти функции возвращают количество записанных символов \(не включая завершающее значение null\); в противном случае эти функции возвращают значение \-1, что указывает на то, что произошло усечение.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Чтобы убедиться, что для завершающего символа null есть место, удостоверьтесь, что значение параметра `count` строго меньше размера буфера, или используйте `_TRUNCATE`.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vsntprintf_s`|`_vsnprintf_s`|`_vsnprintf_s`|`_vsnwprintf_s`|  
|`_vsntprintf_s_l`|`_vsnprintf_s_l`|`_vsnprintf_s_l`|`_vsnwprintf_s_l`|  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`vsnprintf_s`|\<stdio.h\> и \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnprintf_s`, `_vsnprintf_s_l`|\<stdio.h\> и \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnwprintf_s`, `_vsnwprintf_s_l`|\<stdio.h\> или \<wchar.h\> и \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Требуется для обеспечения совместимости с UNIX V.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_vsnprintf_s.cpp  
#include <stdio.h>  
#include <wtypes.h>  
  
void FormatOutput(LPCSTR formatstring, ...)   
{  
   int nSize = 0;  
   char buff[10];  
   memset(buff, 0, sizeof(buff));  
   va_list args;  
   va_start(args, formatstring);  
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);  
   printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
   FormatOutput("%s %s", "Hi", "there");  
   FormatOutput("%s %s", "Hi", "there!");  
   FormatOutput("%s %s", "Hi", "there!!");  
}  
```  
  
  **nSize: 8, buff: Hi there**  
**nSize: 9, buff: Hi there\!**  
**nSize: \-1, buff: Hi there\!**   
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)