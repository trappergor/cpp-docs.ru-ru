---
title: _strdate_s, _wstrdate_s
ms.date: 11/04/2016
api_name:
- _strdate_s
- _wstrdate_s
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
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
ms.openlocfilehash: fadd30ec81cff59d675212e59c8513656c7b2f35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940752"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Скопируйте текущую системную дату в буфер. Это версии функции [_strdate, _wstrdate](strdate-wstrdate.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
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

### <a name="parameters"></a>Параметры

*buffer*<br/>
Указатель на буфер, в который будет записана отформатированная строка с датой.

*numberOfElements*<br/>
Размер буфера.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определены в ERRNO. H; см. в таблице ниже точные ошибки, создаваемые этой функцией. Дополнительные сведения о кодах ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Условия ошибок

|*buffer*|*numberOfElements*|Назад|Содержимое *буфера*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(любые)|**EINVAL**|Без изменений|
|Not **null** (указывает на допустимый буфер)|0|**EINVAL**|Без изменений|
|Not **null** (указывает на допустимый буфер)|0 < *numberOfElements* < 9|**EINVAL**|Пустая строка|
|Not **null** (указывает на допустимый буфер)|*numberOfElements* > = 9|0|Текущая дата, отформатированная, как указано в разделе «Примечания»|

## <a name="security-issues"></a>Проблемы безопасности

Передача недопустимого значения, отличного от **null** , в буфер приведет к нарушению прав доступа, если параметр *numberOfElements* больше 9.

Передача значений для размера, превышающего фактический размер *буфера* , приведет к переполнению буфера.

## <a name="remarks"></a>Примечания

Эти функции предоставляют более безопасные версии **_strdate** и **_wstrdate**. Функция **_strdate_s** Копирует текущую системную дату в буфер, на который указывает *buffer*, в формате **мм**/**DD**/**гг**, где **mm** — две цифры, представляющие месяц, **дд** — две цифры, представляющие день, а **гг** — последние две цифры года. Например, строка **12/05/99** представляет 5 декабря 1999. Буфер должен содержать по крайней мере 9 символов.

**_wstrdate_s** — это версия **_strdate_s**для расширенных символов; аргумент и возвращаемое значение **_wstrdate_s** являются строками расширенных символов. В остальном эти функции ведут себя одинаково.

Если *buffer* является **пустым** указателем или если *numberOfElements* меньше 9 символов, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают-1 и **задают значение** **еинвал** , если буфер равен **null** или если *numberOfElements* меньше или равен 0, или если значение параметра "переполнять **" равно "** **ERANGE** ", если *numberOfElements* меньше 9.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций:

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> или \<wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>Пример

См. пример для [time](time-time32-time64.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
