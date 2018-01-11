---
title: "_strdate, _wstrdate | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate
- _wstrdate
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tstrdate
- wstrdate
- _wstrdate
- _strdate
- strdate
dev_langs: C++
helpviewer_keywords:
- strdate function
- dates, copying
- tstrdate function
- _wstrdate function
- wstrdate function
- _strdate function
- _tstrdate function
- copying dates
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54c7aa7fda123e811f23c2cc4b9e8d81f76966df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="strdate-wstrdate"></a>_strdate, _wstrdate
Скопируйте текущую системную дату в буфер. Существуют более безопасные версии этих функций; см. статью [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_strdate(  
   char *datestr   
);  
wchar_t *_wstrdate(  
   wchar_t *datestr   
);  
template <size_t size>  
char *_strdate(  
   char (&datestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrdate(  
   wchar_t (&datestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `datestr`  
 Указатель на буфер, содержащий отформатированную строку с датой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на результирующую строку символов `datestr`.  
  
## <a name="remarks"></a>Примечания  
 Существуют более безопасные версии этих функций; см. статью [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md). По возможности рекомендуется использовать более безопасные функции.  
  
 Функция `_strdate` копирует текущую системную дату в буфер, на который указывает `datestr`, в формате `mm` / `dd` / `yy`, где `mm` состоит из двух цифр, представляющих месяц, `dd` состоит из двух цифр, представляющих день, а `yy` представляет две последние цифры года. Например, строка `12/05/99` представляет 5 декабря 1999 г. Размер буфера должен быть не менее 9 байтов.  
  
 Если `datestr` является указателем `NULL`, вызывается обработчик недопустимых параметров (см. раздел [Проверка параметров](../../c-runtime-library/parameter-validation.md)). Если разрешается продолжать выполнение, эти функции возвращают -1 и задают `errno` значение `EINVAL`.  
  
 `_wstrdate` — это версия с расширенными символами для `_strdate`; аргумент и возвращаемое значение `_wstrdate` являются строками с расширенными символами. В остальном эти функции ведут себя одинаково.  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// strdate.c  
// compile with: /W3  
#include <time.h>  
#include <stdio.h>  
int main()  
{  
    char tmpbuf[9];  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996  
    // Note: _strdate is deprecated; consider using _strdate_s instead  
}  
```  
  
```Output  
OS date: 04/25/03  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)