---
title: "_cprintf, _cprintf_l, _cwprintf, _cwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwprintf_l"
  - "_cprintf_l"
  - "_cwprintf"
  - "_cprintf"
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
  - "_cwprintf"
  - "cwprintf"
  - "tcprintf"
  - "_tcprintf"
  - "_cprintf"
  - "cwprintf_l"
  - "tcprintf_l"
  - "_tcprintf_l"
  - "cprintf_l"
  - "_cprintf_l"
  - "_cwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cprintf - функция"
  - "_cprintf_l - функция"
  - "_cwprintf - функция"
  - "_cwprintf_l - функция"
  - "_tcprintf - функция"
  - "_tcprintf_l - функция"
  - "знаки, печать в консоль"
  - "cprintf_l - функция"
  - "cwprintf - функция"
  - "cwprintf_l - функция"
  - "печать символов в консоль"
  - "tcprintf - функция"
  - "tcprintf_l - функция"
ms.assetid: 67ffefd4-45b3-4be0-9833-d8d26ac7c4e2
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# _cprintf, _cprintf_l, _cwprintf, _cwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Форматирует и выводит на консоль.  Доступны более безопасные версии; см. раздел [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _cprintf(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_l(   
   const char * format,  
   locale_t locale [,  
   argument] …   
);  
int _cwprintf(  
   const wchar * format [,   
   argument] …  
);  
int _cwprintf_l(  
   const wchar * format,  
   locale_t locale [,   
   argument] …  
);  
```  
  
#### Параметры  
 `format`  
 Строка управления форматом.  
  
 `argument`  
 Необязательные параметры.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Число печатаемых знаков.  
  
## Заметки  
 Эти функции `` форматируют и печатают наборы символов и значений напрямую на консоль, используя для вывода символов функцию `_putch` \(`_putwch` для `_cwprintf`\).  Каждый `argument` \(если он есть\) преобразуется и выводится согласно соответствующей спецификацией формата в `format`.  Формат имеет те же форму и функцию, что и параметр `format` для функции [printf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  В отличие от функций `fprintf`, `printf` и `sprintf`, ни `_cprintf`, ни `_cwprintf` не заменяют символы конца строки на сочетание символов конца строки и возврата каретки \(CR\-LF\) при выводе.  
  
 Важное отличие заключается в том, что `_cwprintf` показывает символы юникода при использовании в Windows NT.  В отличие от `_cprintf`, `_cwprintf` использует текущие параметры языкового стандарта консоли.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  
  
 `_cprintf` проверяет параметр `format`.  Если `format` \- указатель на null, то функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает \-1 и устанавливает `errno` в значение `EINVAL`.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcprintf`|`_cprintf`|`_cprintf`|`_cwprintf`|  
|`_tcprintf_l`|`_cprintf_l`|`_cprintf_l`|`_cwprintf_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_cprintf`,`_cprintf_l`|\<conio.h\>|  
|`_cwprintf`, `_cwprintf_l`|\<conio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
  **\-16  001d  62511  A Test**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Ввод\-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)   
 [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)   
 [Синтаксис описания формата: функции printf и wprintf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)