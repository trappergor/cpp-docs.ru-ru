---
title: "ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
dev_langs:
- C++
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 371ca59a6002cd5936771f1ac9cea7c39b192cee
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
Преобразуют значение времени в строку и настраивают его в соответствии с параметрами локального часового пояса. Это версии функции [ctime, _ctime64, _wctime, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `buffer`  
 Должен быть достаточно большим для хранения 26 символов. Указатель на результирующую строку символов или `NULL` если:  
  
-   `time` представляет дату перед полуночью 1-го января 1970 года, в формате UTC.  
  
-   Если используется функция `_ctime32_s` или `_wctime32_s`, а `time` представляет дату после 23:59:59 18-го января 2038 года.  
  
-   Если используется функция `_ctime64_s` или `_wctime64_s` и `time` представляет дату после 23:59:59 31-го декабря 3000 года (в формате UTC).  
  
-   Если используются `_ctime_s` или `_wctime_s`, эти функции служат оболочками для предыдущих функций. См. раздел примeчаний.  
  
 [in] `numberOfElements`  
 Размер буфера.  
  
 [in] `time`  
 Указатель на сохраненное время.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае отказа в связи с недопустимым параметром вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, возвращается код ошибки. Коды ошибок определены в файле ERRNO.H; список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md). Фактические коды ошибок, отображаемые для каждого условия ошибки, представлены в следующей таблице.  
  
## <a name="error-conditions"></a>Условия ошибок  
  
|`buffer`|`numberOfElements`|`time`|Назад|Значение в `buffer`|  
|--------------|------------------------|------------|------------|-----------------------|  
|`NULL`|любые|любые|`EINVAL`|Без изменений|  
|Не `NULL` (указывает на допустимую память)|0|любые|`EINVAL`|Без изменений|  
|Не `NULL`|0< size < 26|любые|`EINVAL`|Пустая строка|  
|Не `NULL`|>= 26|NULL|`EINVAL`|Пустая строка|  
|Не `NULL`|>= 26|< 0|`EINVAL`|Пустая строка|  
  
## <a name="remarks"></a>Примечания  
 Функция `ctime_s` преобразует значение времени, хранящееся в структуре [time_t](../../c-runtime-library/standard-types.md), в символьную строку. Значение `time` обычно получается из вызова функции [time](../../c-runtime-library/reference/time-time32-time64.md), которая возвращает количество секунд, истекших после полуночи (00:00:00) 1-го января 1970 года (в формате UTC). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки ("\n") и нуль-символ ("\0") занимают две последние позиции строки.  
  
 Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Дополнительные сведения о настройке местного времени см. в описании функций `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime32_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md). Сведения об определении среды часового пояса и глобальных переменных см. в описании функции [_tzset](../../c-runtime-library/reference/tzset.md).  
  
 `_wctime32_s` и `_wctime64_s` — версии функций `_ctime32_s` и `_ctime64_s` для расширенных символов; возвращают указатель на строку из расширенных символов. В остальном поведение функций `_ctime64_s`, `_wctime32_s` и `_wctime64_s` совпадает с поведением функции `_ctime32_s`.  
  
 `ctime_s` — встраиваемая функция, которая принимает значение `_ctime64_s`, и `time_t` эквивалентна `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. В результате `ctime_s` будет вычисляться как `_ctime32_s`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`ctime_s`, `_ctime32_s`, `_ctime64_s`|\<time.h>|  
|`_wctime_s`, `_wctime32_s`, `_wctime64_s`|\<time.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
