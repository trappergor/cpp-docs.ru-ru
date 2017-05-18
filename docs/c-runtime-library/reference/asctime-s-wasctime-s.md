---
title: "asctime_s _wasctime_s | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wasctime_s
- asctime_s
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
- asctime_s
- _wasctime_s
- _tasctime_s
dev_langs:
- C++
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4d4b2bf3c4fb4180b6da1d39ca26bfe819971f31
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="asctimes-wasctimes"></a>asctime_s, _wasctime_s
Преобразуют структуру времени `tm` в символьную строку. Это версии функций [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 [out] Указатель на буфер для хранения полученной символьной строки. Эта функция принимает указатель на допустимое расположение в памяти, размер которого указан в `numberOfElements`.  
  
 `numberOfElements`  
 [in] Размер буфера, используемого для хранения результатов.  
  
 `_tm`  
 [in] Структура даты/времени. Эта функция принимает указатель на допустимый объект `struct tm`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае отказа вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки. Коды ошибок определенны в ERRNO.H. Дополнительные сведения см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md). Фактические коды ошибок, возвращаемые для каждого условия ошибки, приведены в следующей таблице.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`buffer`|`numberOfElements`|`tm`|Назад|Значение в `buffer`|  
|--------------|------------------------|----------|------------|-----------------------|  
|`NULL`|Любой|Любой|`EINVAL`|Без изменений|  
|Не `NULL` (указывает на допустимую память)|0|Любой|`EINVAL`|Без изменений|  
|Не `NULL`|0< size < 26|Любой|`EINVAL`|Пустая строка|  
|Не `NULL`|>= 26|`NULL`|`EINVAL`|Пустая строка|  
|Не `NULL`|>= 26|Недопустимая структура времени или компоненты времени выходят за пределы допустимого диапазона|`EINVAL`|Пустая строка|  
  
> [!NOTE]
>  Условия ошибки для функции `wasctime_s` аналогичны таковым для функции `asctime_s`, но ограничение размера измеряется в словах.  
  
## <a name="remarks"></a>Примечания  
 Функция `asctime` преобразует время, хранящееся в виде структуры, в символьную строку. Значение `_tm` обычно получается из вызова функции `gmtime` или `localtime`. Обе функции могут использоваться для заполнения структуры `tm`, как определено в файле TIME.H.  
  
|Член timeptr|Значение|  
|--------------------|-----------|  
|`tm_hour`|Часы после полуночи (0-23)|  
|`tm_isdst`|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно. Библиотека времени выполнения C принимает правила Соединенных Штатов для реализации проверки на летнее время (DST).|  
|`tm_mday`|День месяца (1-31)|  
|`tm_min`|Минуты после часа (0-59)|  
|`tm_mon`|Месяц (0-11; Январь = 0)|  
|`tm_sec`|Секунды после минуты (0-59)|  
|`tm_wday`|День недели (0 – 6; Воскресенье = 0)|  
|`tm_yday`|День года (0-365; 1 января = 0)|  
|`tm_year`|Год (текущий год минус 1900)|  
  
 Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Обратитесь к функциям [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md), [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) за сведениями о настройке местного времени и к функции [_tzset](../../c-runtime-library/reference/tzset.md) за сведениями об определении среды часового пояса и глобальных переменных.  
  
 Итоговая строка, полученная с помощью `asctime_s`, содержит ровно 26 символов и имеет вид `Wed Jan 02 02:03:55 1980\n\0`. Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки и нуль-символ занимают две последние позиции строки. Значение, переданное в качестве второго параметра, должно иметь по крайней мере такое значение. Если оно меньше, возвращается код ошибки `EINVAL`.  
  
 `_wasctime_s` — это версия функции `asctime_s` для расширенных символов. Поведение `_wasctime_s` и `asctime_s` идентично в противном случае.  
  
### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`asctime_s`|\<time.h>|  
|`_wasctime_s`|\<time.h> или \<wchar.h>|  
  
## <a name="security"></a>Безопасность  
 Если указатель буфера не `NULL` и указатель не указывает на допустимый буфер, функция перезапишет все в указанном месте. Это также может привести к нарушению прав доступа.  
  
 Если переданный аргумент size превышает фактический размер буфера, может возникать ошибка [переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## <a name="example"></a>Пример  
 Эта программа помещает системное время в целочисленную переменную `aclock`, преобразует его в структуру `newtime` и затем преобразует его в строку для вывода с помощью функции `asctime_s`.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
```Output  
Current date and time: Wed May 14 15:30:17 2003  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
