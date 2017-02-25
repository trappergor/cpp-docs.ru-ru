---
title: "_vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vcprintf_p"
  - "_vcwprintf_p_l"
  - "_vcprintf_p_l"
  - "_vcwprintf_p"
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
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vcwprintf_p"
  - "vcprintf_p_l"
  - "_vcprintf_p"
  - "_vcprintf_p_l"
  - "vcwprintf_p_l"
  - "vcprintf_p"
  - "_vcwprintf_p"
  - "_vcwprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vcprintf_p - функция"
  - "_vcprintf_p_l - функция"
  - "_vcwprintf_p - функция"
  - "_vcwprintf_p_l - функция"
  - "_vtcprintf_p - функция"
  - "_vtcprintf_p_l - функция"
  - "vcprintf_p - функция"
  - "vcprintf_p_l - функция"
  - "vcwprintf_p - функция"
  - "vcwprintf_p_l - функция"
  - "vtcprintf_p - функция"
  - "vtcprintf_p_l - функция"
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывает форматированные выходные данные в консоль, используя указатель на список аргументов, и поддерживает позиционные параметры в строке формата.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _vcprintf_p(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_p_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_p(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_p_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### Параметры  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Синтаксис описания формата: функции printf и wprintf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  
  
## Возвращаемое значение  
 Число выведенных символов или отрицательное значение в случае ошибки.  Если параметр `format` является пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, для `errno` задается значение `EINVAL` и возвращается значение –1.  
  
## Заметки  
 Каждая из этих функций принимает указатель на список аргументов, а затем использует функцию `_putch` для форматирования и записи данных в консоль.  \(`_vcwprintf_p` использует `_putwch` вместо `_putch`.  `_vcwprintf_p` — версия `_vcprintf_p` с расширенными символами.  Она принимает строку расширенных символов в качестве аргумента.\)  
  
 Версии этих функций с суффиксом `_l` идентичны версиям без суффикса, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  
  
 Каждый `argument` \(при наличии\) преобразуется и выводится согласно соответствующей спецификации формата в `format`.  Спецификация формата поддерживает позиционные параметры, позволяющие определить порядок, в котором аргументы используются в строке форматирования.  Подробнее: [Позиционные параметры printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Эти функции не заменяют символы конца строки на сочетание символов конца строки и возврата каретки \(CR\-LF\) при выводе.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Кроме того, эти функции проверяют входной указатель и строку форматирования.  Если параметр `format` или `argument` имеет значение `NULL` либо строка форматирования содержит недопустимые символы форматирования, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если разрешается продолжать выполнение, эти функции возвращают \-1 и задают `errno` значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vtcprintf_p`|`_vcprintf_p`|`_vcprintf_p`|`_vcwprintf_p`|  
|`_vtcprintf_p_l`|`_vcprintf_p_l`|`_vcprintf_p_l`|`_vcwprintf_p_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_vcprintf_p`, `_vcprintf_p_l`|\<conio.h\> и \<stdarg.h\>|  
|`_vcwprintf_p`, `_vcwprintf_p_l`|\<conio.h\> и \<stdarg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_vcprintf_p.c  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function that's used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf_p(format, args);  
}  
  
int main()  
{  
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",  
      "one", 222);  
   _cprintf_s("%d characters printed\r\n");  
}  
```  
  
  **параметр 2 \= 222; параметр 1 \= один**  
**Напечатано 38 символов**   
## См. также  
 [Ввод\-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [Позиционные параметры printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)