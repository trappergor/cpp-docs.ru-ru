---
title: "_putenv, _wputenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putenv"
  - "_wputenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tputenv"
  - "_wputenv"
  - "_putenv"
  - "wputenv"
  - "tputenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putenv - функция"
  - "_tputenv - функция"
  - "_wputenv - функция"
  - "переменные среды, создание"
  - "переменные среды, удаление"
  - "переменные среды, изменение"
  - "putenv - функция"
  - "tputenv - функция"
  - "wputenv - функция"
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _putenv, _wputenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает, изменяет или удаляет переменные среды.  Существуют более безопасные версии этих функций; см. раздел [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### Параметры  
 `envstring`  
 Определение строки среды.  
  
## Возвращаемое значение  
 Возвращает 0 в случае успешного выполнения или –1 в случае ошибки.  
  
## Заметки  
 Функция `_putenv` добавляет новые переменные среды или изменяет значения существующих переменных среды.  Переменные среды определяют среду, в которой выполняется процесс \(например, путь поиска по умолчанию для библиотек, связываемых с программой\).  `_wputenv` — двухбайтовая версия `_putenv`; аргумент `envstring` для `_wputenv` \- строка двухбайтовых знаков.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 Аргумент `envstring` должен быть указателем на строку вида `varname=string`, где `varname` — имя переменной среды, добавляемой или измененяемой, а `string` — значение переменной.  Если `varname` уже является частью среды, ее значение заменяется `string`; в противном случае новая переменная `varname` и ее значение `string` добавляются в эту среду.  Можно удалить переменную среды, указав пустой `string` — другими словами, указав только `varname=`.  
  
 `_putenv` и `_wputenv` затрагивают только среду, являющуюся локальной для текущего процесса; нельзя использовать их для изменения среды командного уровня.  Таким образом, эти функции работают только в структурах данных, доступных в библиотеке среды выполнения, а не в сегменте среды, созданном для процесса операционной системой.  При завершении текущего процесса среда возвращается на уровень вызывающего процесса \(в большинстве случаев — уровень операционной системы\).  Однако, измененную среду можно передать всем новым процессам, созданным `_spawn`, `_exec` или `system`, и эти новые процессы получают все новые элементы, добавленные `_putenv` и `_wputenv`.  
  
 Не изменяйте запись среды напрямую: вместо этого используйте `_putenv` или `_wputenv`, чтобы изменить ее.  В частности, непосредственное освобождение элементов глобального массива `_environ[]` может привести к адресации недопустимой памяти.  
  
 `getenv` и `_putenv` используют глобальную переменную `_environ` для доступа к таблице среды; `_wgetenv` и `_wputenv` используют `_wenviron`.  `_putenv` и `_wputenv` могут изменять значение `_environ` и `_wenviron`, таким образом делая недействительным аргумент `_envp` в `main` и аргумент \_`wenvp` в `wmain`.  Следовательно, безопаснее использовать `_environ` или `_wenviron` для получения данных о среде.  Дополнительные сведения о связи `_putenv` и `_wputenv` с глобальными переменными см. [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv` и `_getenv` не являются потокобезопасными.  `_getenv` может вернуть указатель строки, в то время как `_putenv` изменяет строку, вызывая случайные сбои.  Убедитесь, что вызовы этих функций синхронизированы.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_putenv`|\<stdlib.h\>|  
|`_wputenv`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 Пример использования `_putenv`, см. в [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)