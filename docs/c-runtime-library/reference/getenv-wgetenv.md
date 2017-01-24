---
title: "getenv, _wgetenv | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getenv"
  - "_wgetenv"
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
  - "_wgetenv"
  - "getenv"
  - "_tgetenv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tgetenv - функция"
  - "_wgetenv - функция"
  - "значения среды"
  - "переменные среды"
  - "getenv - функция"
  - "tgetenv - функция"
  - "wgetenv - функция"
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 31
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getenv, _wgetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает значение из текущей среды.  Существуют более безопасные версии этих функций; см. раздел [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### Параметры  
 `varname`  
 Имя переменной среды.  
  
## Возвращаемое значение  
 Возвращает указатель на запись таблицы среды, содержащий `varname`.  Изменять значение переменной среды с помощью возвращенного указателя небезопасно.  Используйте функцию `_putenv`, чтобы изменять значение переменной среды.  Возвращаемое значение `NULL`, если `varname` не найдено в таблице среды.  
  
## Заметки  
 Функция `getenv` ищет список переменных среды для `varname`.  `getenv` не учитывает регистр в операционной системе Windows.  `getenv` и `_putenv` используют копию среды, указанную в глобальной переменной `_environ`, для получения среды.  `getenv` работает только в структурах данных, доступных в библиотеке времени выполнения, а не в «сегменте» среды, созданном для процесса операционной системой.  Поэтому программы, использующих аргумент `envp` в [main](../Topic/main:%20Program%20Startup.md) или [wmain](../Topic/main:%20Program%20Startup.md) могут извлекать неверную информацию.  
  
 Если параметр `varname` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `NULL`.  
  
 `_wgetenv` — это двухбайтовая версия функции `getenv`; аргумент и возвращаемое значение `_wgetenv` являются строками двухбайтовых символов.  Глобальная переменная `_wenviron` является версией `_environ` для расширенных символов.  
  
 В программе с кодировкой MBCS \(например, в программе с кодировкой SBCS ASCII\), `_wenviron` инициализируется `NULL`, поскольку среда состоит из строк многобайтовой кодировки.  Затем, при первом вызове функции `_wputenv` или `_wgetenv`, если среда \(многобайтовой кодировки\) уже существует, создается среда для поддержки расширенных строк, на нее затем устанавливается указатель `_wenviron`.  
  
 Аналогично в программе Юникода \(`_wmain`\), `_environ` инициализируется `NULL`, поскольку среда состоит из расширенных строк.  При первом вызове функции `_putenv` или `getenv`, если среда \(Юникода\) уже существует, создается среда для поддержки многобайтовых строк, на нее затем устанавливается указатель `_environ`.  
  
 Когда две копии среды \(многобайтовой кодировки и Юникода\) существуют одновременно в программе, система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы.  Например, при вызове `_putenv`, вызов `_wputenv` также выполняется автоматически, чтобы две строки среды совпадали.  
  
> [!CAUTION]
>  В редких случаях, когда во система времени выполнения поддерживает и версию Юникода, и многобайтовую версию, эти две версии среды могут не соответствовать точно.  Это происходит потому, что, хотя любая уникальная расширенная строка сопоставлена уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными.  Для получения дополнительной информации см. [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv` и `_getenv` не являются потокобезопасными.  `_getenv` может вернуть указатель строки, в то время как `_putenv` изменяет строку, вызывая случайные сбои.  Убедитесь, что вызовы этих функций синхронизированы.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 Для проверки или изменения значения переменной среды `TZ`, используйте `getenv`, `_putenv` и `_tzset` по мере необходимости.  Дополнительные сведения о `TZ` см. в разделах [\_tzset](../Topic/_tzset.md) и [\_daylight, timezone, и \_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`getenv`|\<stdlib.h\>|  
|`_wgetenv`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_getenv.c  
// compile with: /W3  
// This program uses getenv to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *libvar;  
  
   // Get the value of the LIB environment variable.  
   libvar = getenv( "LIB" ); // C4996  
   // Note: getenv is deprecated; consider using getenv_s instead  
  
   if( libvar != NULL )  
      printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects the environment  
   // variable of the current process. The command processor's  
   // environment is not changed.  
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996  
   // Note: _putenv is deprecated; consider using putenv_s instead  
  
   // Get new value.  
   libvar = getenv( "LIB" ); // C4996  
  
   if( libvar != NULL )  
      printf( "New LIB variable is: %s\n", libvar );  
}  
```  
  
  **Original LIB variable is: C:\\progra~1\\devstu~1\\vc\\lib**  
**New LIB variable is: c:\\mylib;c:\\yourlib**   
## Эквивалент в .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)