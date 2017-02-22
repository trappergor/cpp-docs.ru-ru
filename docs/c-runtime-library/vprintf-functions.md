---
title: "Функции vprintf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "форматированный текст [C++]"
  - "vprintf - функция"
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Функции vprintf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждая из функций `vprintf` принимает указатель на список аргументов, затем форматирует и записывает полученные данные в определенное местоположение.  Функции отличаются выполняемой проверкой параметров, тем, принимают ли функции многобайтовые или однобайтовые символьные строки, выходным местоназначением и поддержкой указания порядка, в котором параметры используются в строке форматирования.  
  
|||  
|-|-|  
|[\_vcprintf, \_vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../Topic/vfprintf_s,%20_vfprintf_s_l,%20vfwprintf_s,%20_vfwprintf_s_l.md)|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../Topic/_vsprintf_p,%20_vsprintf_p_l,%20_vswprintf_p,%20_vswprintf_p_l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[\_vscprintf, \_vscprintf\_l, \_vscwprintf, \_vscwprintf\_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[\_vsnprintf, \_vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## Заметки  
 Функции `vprintf` аналогичны эквивалентным им функциям, указанным в приведенной ниже таблице.  Однако каждая функция `vprintf` принимает указатель на список аргументов, в то время как каждая из функций\-аналогов принимает список аргументов.  
  
 Эти функции форматируют данные для вывода в местоназначение следующим образом.  
  
|Функция|Функция\-аналог|Назначение вывода|Проверка параметров|Поддержка позиционного параметра|  
|-------------|---------------------|-----------------------|-------------------------|--------------------------------------|  
|`_vcprintf`|[\_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|консоль|Проверка на значение null.|нет|  
|`_vcwprintf`|[\_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|консоль|Проверка на значение null.|нет|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Поток*|Проверка на значение null.|нет|  
|**vfprintf\_p**|[fprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Поток*|Проверка допустимого формата и проверка на значение null.|да|  
|`vfprintf_s`|[fprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Поток*|Проверка допустимого формата и проверка на значение null.|нет|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Поток*|Проверка на значение null.|нет|  
|**vfwprintf\_p**|[fwprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Поток*|Проверка допустимого формата и проверка на значение null.|да|  
|`vfwprintf_s`|[fwprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Поток*|Проверка допустимого формата и проверка на значение null.|нет|  
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Проверка на значение null.|нет|  
|**vprintf\_p**|[printf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Проверка допустимого формата и проверка на значение null.|да|  
|`vprintf_s`|[printf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Проверка допустимого формата и проверка на значение null.|нет|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Проверка на значение null.|нет|  
|**vwprintf\_p**|[wprintf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Проверка допустимого формата и проверка на значение null.|да|  
|`vwprintf_s`|[wprintf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Проверка допустимого формата и проверка на значение null.|нет|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|память, указанная в *buffer*|Проверка на значение null.|нет|  
|**vsprintf\_p**|[sprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|память, указанная в *buffer*|Проверка допустимого формата и проверка на значение null.|да|  
|`vsprintf_s`|[sprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|память, указанная в *buffer*|Проверка допустимого формата и проверка на значение null.|нет|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|память, указанная в *buffer*|Проверка на значение null.|нет|  
|**vswprintf\_p**|[swprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|память, указанная в *buffer*|Проверка допустимого формата и проверка на значение null.|да|  
|`vswprintf_s`|[swprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|память, указанная в *buffer*|Проверка допустимого формата и проверка на значение null.|нет|  
|`_vscprintf`|[\_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|память, указанная в *buffer*|Проверка на значение null.|нет|  
|`_vscwprintf`|[\_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|память, указанная в *buffer*|Проверка на значение null.|нет|  
|`_vsnprintf`|[\_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|память, указанная в *buffer*|Проверка на значение null.|нет|  
|`_vsnwprintf`|[\_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|память, указанная в *buffer*|Проверка на значение null.|нет|  
  
 Аргумент `argptr` имеет тип `va_list`, который определен в VARARGS.H и STDARG.H.  Переменная `argptr` должна быть инициализирована **va\_start,** и может быть повторно инициализирована последующими вызовами `va_arg`; `argptr` затем указывает на начало списка аргументов, которые конвертируются и передаются на выход в соответствии со спецификациями в аргументе *format*.  *format* имеет ту же форму и функцию, как и аргумента *format* для [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  Ни одна из этих функций не вызывает `va_end`.  Более полное описание каждой функции `vprintf` смотрите в описании ее функции\-аналога, как показано в приведенной выше таблице.  
  
 `_vsnprintf` отличается от **vsprintf** тем, что она записывает не более чем *count* байтов в *buffer*.  
  
 Версии этих функций с инфиксом **w** в имени являются версиями с многобайтовыми символами соответствующих функций без инфикса **w**; в каждой из этих функций с многобайтовыми символами *buffer* и *format* являются строками многобайтовых символов.  В противном случае каждая функция с многобайтовыми символами работает так же, как ее функция\-аналог со строками однобайтовых символов.  
  
 Версии этих функций с суффиксами **\_s** и **\_p** являются более безопасными.  Эти версии проверяют строки форматирования и создают исключение, если строка форматирования сформирована неправильно \(например, если используются недопустимые символы форматирования\).  
  
 Версии этих функций с суффиксом **\_p** предоставляют возможность определить порядок, в котором указанные аргументы подставляются в строке форматирования.  Для получения дополнительной информации см. [Позиционные параметры printf\_p](../c-runtime-library/printf-p-positional-parameters.md).  
  
 Для **vsprintf**, `vswprintf`, `_vsnprintf` и `_vsnwprintf`, для копирования, происходящего между строками, которые перекрываются, поведение не определено.  
  
> [!IMPORTANT]
>  Убедитесь, что *format* не является строкой, определяемой пользователем.  Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  При использовании безопасных версий этих функций \(либо суффикс **\_s**, либо **\_p** \) предоставленная пользователем строка форматирования может активировать исключение, связанное с недопустимым параметром, если эта строка содержит недопустимые символы форматирования.  
  
## См. также  
 [Потоковый ввод\-вывод](../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)