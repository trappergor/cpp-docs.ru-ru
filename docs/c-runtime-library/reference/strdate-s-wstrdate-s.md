---
title: "_strdate_s, _wstrdate_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate_s
- _wstrdate_s
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
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
dev_langs: C++
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71117aed66d83c2c2ae1651c4de9c91e06a43653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s
Скопируйте текущую системную дату в буфер. Это версии функции [_strdate, _wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `buffer`  
 Указатель на буфер, в который будет записана отформатированная строка с датой.  
  
 [in] `numberOfElements`  
 Размер буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определены в ERRNO. H; см. в таблице ниже точные ошибки, создаваемые этой функцией. Дополнительные сведения о кодах ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md).  
  
## <a name="error-conditions"></a>Условия ошибок  
  
|`buffer`|`numberOfElements`|Назад|Содержимое `buffer`|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|(любые)|`EINVAL`|Без изменений|  
|Не `NULL` (указывает на допустимый буфер)|0|`EINVAL`|Без изменений|  
|Не `NULL` (указывает на допустимый буфер)|0 < `numberOfElements` < 9|`EINVAL`|Пустая строка|  
|Не `NULL` (указывает на допустимый буфер)|`numberOfElements` >= 9|0|Текущая дата, отформатированная, как указано в разделе «Примечания»|  
  
## <a name="security-issues"></a>Проблемы безопасности  
 Передача недействительного значения, отличного от `NULL`, для буфера приведет к нарушению прав доступа, если значение параметра `numberOfElements` больше 9.  
  
 Передача значений для размера, который больше фактического размера `buffer`, приведет к переполнению буфера.  
  
## <a name="remarks"></a>Примечания  
 Эти функции обеспечивают более безопасные версии `_strdate` и `_wstrdate`. Функция `_strdate_s` копирует текущую системную дату в буфер, на который указывает `buffer`, в формате `mm` / `dd` / `yy`, где `mm` состоит из двух цифр, представляющих месяц, `dd` состоит из двух цифр, представляющих день, а `yy` представляет две последние цифры года. Например, строка `12/05/99` представляет 5 декабря 1999 г. Буфер должен содержать по крайней мере 9 символов.  
  
 `_wstrdate_s` — это версия с расширенными символами для `_strdate_s`; аргумент и возвращаемое значение `_wstrdate_s` являются строками с расширенными символами. В остальном эти функции ведут себя одинаково.  
  
 Если параметр `buffer` является указателем `NULL` или значение параметра `numberOfElements` меньше 9 символов, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если разрешается продолжить выполнение, эти функции возвращают значение -1 и присваивают `errno` значение `EINVAL`, если буфер имеет значение `NULL` или если значение `numberOfElements` меньше или равно 0, или присваивают `errno` значение `ERANGE`, если `numberOfElements` меньше 9.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций:  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> или \<wchar.h>|  
|`_strdate_s`|\<time.h>|  
  
## <a name="example"></a>Пример  
 См. пример для [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)