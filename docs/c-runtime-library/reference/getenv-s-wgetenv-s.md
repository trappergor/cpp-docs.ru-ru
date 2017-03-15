---
title: "getenv_s, _wgetenv_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getenv_s"
  - "_wgetenv_s"
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
  - "getenv_s"
  - "_tgetenv_s"
  - "_wgetenv_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tgetenv_s - функция"
  - "_wgetenv_s - функция"
  - "переменные среды"
  - "getenv_s - функция"
  - "tgetenv_s - функция"
  - "wgetenv_s - функция"
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 42
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 42
---
# getenv_s, _wgetenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает значение из текущей среды.  Это версии функций [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md) с повышенной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char* buffer,  
   size_t numberOfElements,  
   const char *varname   
);  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *varname   
);  
template <size_t size>  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char (&buffer)[size],  
   const char *varname   
); // C++ only  
template <size_t size>  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t (&buffer)[size],  
   const wchar_t *varname   
); // C++ only  
```  
  
#### Параметры  
 `pReturnValue`  
 Требуемый размер буфера или 0, если переменная не найдена.  
  
 `buffer`  
 Буфер для хранения значения переменной среды.  
  
 `numberOfElements`  
 Размер `buffer`.  
  
 `varname`  
 Имя переменной среды.  
  
## Возвращаемое значение  
 Ноль при успехе; код ошибки при неудаче.  
  
### Условия ошибок  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|Возвращаемое значение|  
|--------------------|--------------|------------------------|---------------|---------------------------|  
|`NULL`|любые|any|любые|`EINVAL`|  
|любые|`NULL`|\>0|любые|`EINVAL`|  
|любые|any|любые|`NULL`|`EINVAL`|  
  
 При любом из этих условий ошибки вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функции задают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
 Кроме того, если буфер слишком мал, эти функции возвращают `ERANGE`.  Они не вызывают обработчик недопустимого параметра.  Они записывают необходимый размер буфера в `pReturnValue`, поэтому программы могут вызвать функцию снова с большим буфером.  
  
## Заметки  
 Функция `getenv_s` выполняет поиск в списке переменных среды для `varname`.  `getenv_s` не учитывает регистр в операционной системе Windows.  `getenv_s` и `_putenv_s` используют копию среды, указанную глобальной переменной `_environ`, для получения среды.  `getenv_s` работает только в структурах данных, доступных в библиотеке времени выполнения, а не в "сегменте" среды, созданном для процесса операционной системой.  Поэтому программы, использующие аргумент `envp` в [main](../Topic/main:%20Program%20Startup.md) или [wmain](../Topic/main:%20Program%20Startup.md), могут извлекать неверную информацию.  
  
 `_wgetenv_s` — это версия с расширенными символами для `getenv_s`; аргумент и возвращаемое значение `_wgetenv_s` являются строками с расширенными символами.  Глобальная переменная `_wenviron` — это версия `_environ` с расширенными символами.  
  
 В программе с многобайтовой кодировкой \(например, в программе с однобайтовой кодировкой ASCII\) переменная `_wenviron` инициализируется значением `NULL`, поскольку среда состоит из строк многобайтовой кодировки.  Затем, если при первом вызове функции `_wputenv` или `_wgetenv_s` среда \(многобайтовой кодировки\) уже существует, создается соответствующая среда для поддержки расширенных строк, и на нее устанавливается указатель `_wenviron`.  
  
 Аналогично в программе Юникода \(`(_wmain`\) переменная `_environ` сначала получает значение `NULL`, поскольку среда состоит из расширенных строк.  Затем, если при первом вызове функции `_putenv` или `getenv_s` среда \(Юникода\) уже существует, создается соответствующая среда для поддержки многобайтовых строк, на которую указывает `_environ`.  
  
 Если две копии среды \(многобайтовой кодировки и Юникода\) существуют одновременно в программе, система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы.  Например, при вызове функции `_putenv` также автоматически производится вызов функции `_wputenv`, чтобы строки в двух средах совпадали друг с другом.  
  
> [!CAUTION]
>  В редких случаях, когда система времени выполнения поддерживает как версию Юникода, так и многобайтовую версию среды, эти две версии среды могут не полностью соответствовать друг другу.  Это происходит потому, что хотя любая уникальная строка с многобайтовыми символами сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными.  Для получения дополнительной информации см. раздел [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv_s` и `_getenv_s` не являются потокобезопасными.  `_getenv_s` может вернуть указатель строки, в то время как `_putenv_s` изменяет строку, что может вызвать случайные сбои.  Убедитесь, что вызовы этих функций синхронизированы.  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в статье [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 Для проверки или изменения значения переменной среды `TZ` используйте `getenv_s`, `_putenv` и `_tzset` по мере необходимости.  Дополнительные сведения о переменной `TZ` см. в разделах [\_tzset](../Topic/_tzset.md) и [\_daylight, \_dstbias, \_timezone и \_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`getenv_s`|\<stdlib.h\>|  
|`_wgetenv_s`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_getenv_s.c  
// This program uses getenv_s to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* libvar;  
   size_t requiredSize;  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
   if (requiredSize == 0)  
   {  
      printf("LIB doesn't exist!\n");  
      exit(1);  
   }  
  
   libvar = (char*) malloc(requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the value of the LIB environment variable.  
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects  
   // the environment variable of the current process. The command  
   // processor's environment is not changed.  
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
  
   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the new value of the LIB environment variable.   
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "New LIB variable is: %s\n", libvar );  
  
   free(libvar);  
}  
```  
  
  **Original LIB variable is: c:\\vctools\\lib;c:\\vctools\\atlmfc\\lib;c:\\vctools\\PlatformSDK\\lib;c:\\vctools\\Visual Studio SDKs\\DIA Sdk\\lib;c:\\vctools\\Visual Studio SDKs\\BSC Sdk\\lib**  
**New LIB variable is: c:\\mylib;c:\\yourlib**   
## Эквивалент в .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [\_dupenv\_s, \_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)