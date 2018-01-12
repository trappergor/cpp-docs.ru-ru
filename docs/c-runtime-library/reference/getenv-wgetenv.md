---
title: "getenv, _wgetenv | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getenv
- _wgetenv
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
- _wgetenv
- getenv
- _tgetenv
dev_langs: C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0d010e7b04093446792eb122a67227880b7a395
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv
Получает значение из текущей среды. Существуют более безопасные версии этих функций; см. раздел [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `varname`  
 Имя переменной среды.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на запись таблицы среды, содержащую `varname`. Изменять значение переменной среды с помощью возвращенного указателя небезопасно. Чтобы изменить значение переменной среды, используйте функцию `_putenv`. Если имя `NULL` не найдено в таблице среды, возвращается значение `varname`.  
  
## <a name="remarks"></a>Примечания  
 Функция `getenv` выполняет поиск в списке переменных среды для `varname`. `getenv` не учитывает регистр в операционной системе Windows. Функции `getenv` и `_putenv` для доступа к среде используют копию среды, указанную в глобальной переменной `_environ`. Функция `getenv` работает только в структурах данных, доступных в библиотеке времени выполнения, а не в "сегменте" среды, созданном для процесса операционной системой. Поэтому программы, использующих аргумент `envp` в [main](../../cpp/main-program-startup.md) или [wmain](../../cpp/main-program-startup.md) могут извлекать неверную информацию.  
  
 Если `varname` является указателем `NULL`, эта функция вызывает обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `NULL`.  
  
 `_wgetenv` — это версия с расширенными символами для `getenv`; аргумент и возвращаемое значение `_wgetenv` являются строками с расширенными символами. Глобальная переменная `_wenviron` — это версия `_environ` с расширенными символами.  
  
 В программе с многобайтовой кодировкой (например, в программе с однобайтовой кодировкой ASCII) переменная `_wenviron` инициализируется значением `NULL`, поскольку среда состоит из строк многобайтовой кодировки. Затем если при первом вызове функции `_wputenv` или `_wgetenv` среда (многобайтовой кодировки) уже существует, создается соответствующая среда для поддержки расширенных строк и на нее устанавливается указатель `_wenviron`.  
  
 Аналогично в программе Юникода (`_wmain`) переменная `_environ` инициализируется значением `NULL`, поскольку среда состоит из расширенных строк. Затем, если при первом вызове функции `_putenv` или `getenv` среда (Юникода) уже существует, создается соответствующая среда для поддержки многобайтовых строк, на которую указывает `_environ`.  
  
 Если в программе одновременно существуют две копии среды (многобайтовой кодировки и Юникода), система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при вызове функции `_putenv` также автоматически производится вызов функции `_wputenv`, чтобы строки в двух средах совпадали.  
  
> [!CAUTION]
>  В редких случаях, когда система времени выполнения поддерживает и версию Юникода, и многобайтовую версию, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная расширенная строка сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv` и `_getenv` не являются потокобезопасными. Функция `_getenv` может вернуть указатель строки, в то время как функция `_putenv` изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 Для проверки или изменения значения переменной среды `TZ` используйте функции `getenv`, `_putenv` и `_tzset`, как требуется. Дополнительные сведения о переменной `TZ` см. в разделах [_tzset](../../c-runtime-library/reference/tzset.md), а также [_daylight, timezone и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`getenv`|\<stdlib.h>|  
|`_wgetenv`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
Original LIB variable is: C:\progra~1\devstu~1\vc\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)