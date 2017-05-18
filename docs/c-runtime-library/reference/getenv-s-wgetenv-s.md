---
title: "getenv_s, _wgetenv_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getenv_s
- _wgetenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getenv_s
- _tgetenv_s
- _wgetenv_s
dev_langs:
- C++
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 42
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: de79cb66e33564f321dd3277528d67a8d7e0ddc0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/28/2017

---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s
Получает значение из текущей среды. Это версии функций [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md) с повышенной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pReturnValue`  
 Требуемый размер буфера или 0, если переменная не найдена.  
  
 `buffer`  
 Буфер для хранения значения переменной среды.  
  
 `numberOfElements`  
 Размер `buffer`.  
  
 `varname`  
 Имя переменной среды.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ноль при успехе; код ошибки при неудаче.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|Возвращаемое значение|  
|--------------------|--------------|------------------------|---------------|------------------|  
|`NULL`|любые|любые|любые|`EINVAL`|  
|любые|`NULL`|>0|любые|`EINVAL`|  
|любые|любые|любые|`NULL`|`EINVAL`|  
  
 При любом из этих условий ошибки вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции задают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
 Кроме того, если буфер слишком мал, эти функции возвращают `ERANGE`. Они не вызывают обработчик недопустимого параметра. Они записывают необходимый размер буфера в `pReturnValue`, поэтому программы могут вызвать функцию снова с большим буфером.  
  
## <a name="remarks"></a>Примечания  
 Функция `getenv_s` выполняет поиск в списке переменных среды для `varname`. `getenv_s` не учитывает регистр в операционной системе Windows. `getenv_s` и `_putenv_s` используют копию среды, указанную глобальной переменной `_environ`, для получения среды. `getenv_s` работает только в структурах данных, доступных в библиотеке времени выполнения, а не в "сегменте" среды, созданном для процесса операционной системой. Поэтому программы, использующие аргумент `envp` в [main](../../cpp/main-program-startup.md) или [wmain](../../cpp/main-program-startup.md), могут извлекать неверную информацию.  
  
 `_wgetenv_s` — это версия с расширенными символами для `getenv_s`; аргумент и возвращаемое значение `_wgetenv_s` являются строками с расширенными символами. Глобальная переменная `_wenviron` — это версия `_environ` с расширенными символами.  
  
 В программе с многобайтовой кодировкой (например, в программе с однобайтовой кодировкой ASCII) переменная `_wenviron` инициализируется значением `NULL`, поскольку среда состоит из строк многобайтовой кодировки. Затем, если при первом вызове функции `_wputenv` или `_wgetenv_s` среда (многобайтовой кодировки) уже существует, создается соответствующая среда для поддержки расширенных строк, и на нее устанавливается указатель `_wenviron`.  
  
 Аналогично в программе Юникода (`(_wmain`) переменная `_environ` сначала получает значение `NULL`, поскольку среда состоит из расширенных строк. Затем, если при первом вызове функции `_putenv` или `getenv_s` среда (Юникода) уже существует, создается соответствующая среда для поддержки многобайтовых строк, на которую указывает `_environ`.  
  
 Если две копии среды (многобайтовой кодировки и Юникода) существуют одновременно в программе, система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при вызове функции `_putenv` также автоматически производится вызов функции `_wputenv`, чтобы строки в двух средах совпадали друг с другом.  
  
> [!CAUTION]
>  В редких случаях, когда система времени выполнения поддерживает как версию Юникода, так и многобайтовую версию среды, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная строка с многобайтовыми символами сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv_s` и `_getenv_s` не являются потокобезопасными. `_getenv_s` может вернуть указатель строки, в то время как `_putenv_s` изменяет строку, что может вызвать случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 Для проверки или изменения значения переменной среды `TZ` используйте `getenv_s`, `_putenv` и `_tzset` по мере необходимости. Дополнительные сведения о переменной `TZ` см. в разделах [_tzset](../../c-runtime-library/reference/tzset.md), а также [_daylight, _dstbias, _timezone и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`getenv_s`|\<stdlib.h>|  
|`_wgetenv_s`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
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
  
```Output  
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_dupenv_s, _wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)
