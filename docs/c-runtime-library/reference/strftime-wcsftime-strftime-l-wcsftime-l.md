---
title: "strftime, wcsftime, _strftime_l, _wcsftime_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- _tcsftime
- strftime
- wcsftime
dev_langs:
- C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 1a5331b77e218c5fe5796b2df6d0f61578657758
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l
Форматируют строку времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `strDest`  
 Выходная строка.  
  
 `maxsize`  
 Размер буфера `strDest`, измеренный в символах (`char` или `wchart_t`).  
  
 `format`  
 Строка управления форматом.  
  
 `timeptr`  
Структура данных  `tm`.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `strftime` возвращает количество символов в `strDest`, а функция `wcsftime` возвращает соответствующее количество расширенных символов.  
  
 Если общее количество символов, включая NULL в конце строки, больше `maxsize`, функции `strftime` и `wcsftime` возвращают значение "0" и содержимое `strDest` не определено.  
  
 Количество символов в буфере `strDest` равно числу строковых литералов в параметре `format` плюс все символы, которые могут быть добавлены в параметр `format` через коды форматирования. нуль-символ, завершающий строку, не учитывается в возвращаемом значении.  
  
## <a name="remarks"></a>Примечания  
 `strftime` И `wcsftime` формат функции `tm` время значение в `timeptr` в соответствии с предоставленной `format` аргумент и хранилище результатов в буфер `strDest`. В строку помещается не более `maxsize` символов. Описание полей структуры `timeptr` см. в разделе [asctime](../../c-runtime-library/reference/asctime-wasctime.md). `wcsftime` — это эквивалент функции `strftime` для расширенных символов; ее указывающий на строку аргумент указывает на строку из расширенных символов. В остальном эти функции ведут себя одинаково.  
  
> [!NOTE]
>  В версиях до Visual C++ 2005 документация описывала параметр `format` функции `wcsftime` как имеющий тип данных `const wchar_t *`, но фактической реализацией типа данных `format` был тип `const char *`. Реализация `format` тип данных был обновлен в соответствии с предыдущей и текущей документации, то есть `const wchar_t *`.  
  
 Эта функция проверяет свои параметры. Если `strDest`, `format`, или `timeptr` является пустым указателем, или если `tm` обращаться структуру данных, `timeptr` является недопустимым (например, если он содержит выходящих за пределы диапазона значений для время или дата) или если `format` строка содержит недопустимый код форматирования, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает 0 и устанавливает `errno` в значение `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 Аргумент `format` состоит из одного или нескольких кодов; как и для функции `printf`, коды форматирования начинаются знаком процента (`%`). Символы, которые не начинаются с `%` копируются без изменений для `strDest`. Категория `LC_TIME` текущего языкового стандарта влияет на форматирование выходных данных функции `strftime`. (Дополнительные сведения по `LC_TIME` см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).) Функции без суффикса `_l` используют текущий языковой стандарт. Версии этих функций с суффиксом `_l` идентичны функциям без суффикса, за исключением того, что они принимают языковой стандарт в качестве параметра и используют его вместо текущего языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Коды форматирования для функции `strftime` перечислены ниже:  
  
 `%a`  
 Сокращенное название дня недели  
  
 `%A`  
 Полное название дня недели  
  
 `%b`  
 Сокращенное название месяца  
  
 `%B`  
 Полное название месяца  
  
 `%c`  
 Представление даты и времени, соответствующее языковому стандарту  
  
 `%d`  
 День месяца в виде десятичного числа (01 – 31)  
  
 `%H`  
 Час в 24-часовом формате (00 - 23)  
  
 `%I`  
 Час в 12-часовом формате (01 – 12)  
  
 `%j`  
 День года как десятичное число (001-366)  
  
 `%m`  
 Месяц как десятичное число (01 – 12)  
  
 `%M`  
 Минуты как десятичное число (00 - 59)  
  
 `%p`  
 Индикатор A.M./P.M. текущего языкового стандарта для 12-часового формата  
  
 `%S`  
 Секунды как десятичное число (00 - 59)  
  
 `%U`  
 Неделя года как десятичное число, воскресенье первым днем недели (00 – 53)  
  
 `%w`  
 День недели как десятичное число (0 – 6; 0 соответствует воскресенью)  
  
 `%W`  
 Неделя года как десятичное число, первым днем недели с понедельника (00 – 53)  
  
 `%x`  
 Представление дат для текущего языкового стандарта  
  
 `%X`  
 Представление времени для текущего языкового стандарта  
  
 `%y`  
 Год без века как десятичное число (00 - 99)  
  
 `%Y`  
 Год с веком как десятичное число  
  
 `%z, %Z`  
 Либо название часового пояса, либо его аббревиатура, в зависимости от настроек реестра; если часовой пояс неизвестен, символы отсутствуют  
  
 `%%`  
 Знак процента  
  
 Как и в функции `printf`, любому коду форматирования может предшествовать флаг `#`. В этом случае значение кода формата изменяется следующим образом.  
  
|Код формата|Значение|  
|-----------------|-------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|Флаг `#` игнорируется.|  
|`%#c`|Длинный формат даты и времени в соответствии с текущим языковым стандартом. Например: "Tuesday, March 14, 1995, 12:41:29".|  
|`%#x`|Длинный формат даты в соответствии с текущим языковым стандартом. Например: "Tuesday, March 14, 1995".|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Удаление начальных нулей (если они есть).|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strftime`|\<time.h>|  
|`wcsftime`|\<time.h> или \<wchar.h>|  
|`_strftime_l`|\<time.h>|  
|`_wcsftime_l`|\<time.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>См. также  
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Управление временем](../../c-runtime-library/time-management.md)   
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
