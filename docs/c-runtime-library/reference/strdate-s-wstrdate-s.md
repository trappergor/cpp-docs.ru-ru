---
title: _strdate_s, _wstrdate_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e4e9ff3783fc7a89e7af42ebf283209c034c0d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414315"
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s

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
|Не **NULL** (с указанием допустимый буфер)|0|**EINVAL**|Без изменений|
|Не **NULL** (с указанием допустимый буфер)|0 < *numberOfElements* < 9|**EINVAL**|Пустая строка|
|Не **NULL** (с указанием допустимый буфер)|*numberOfElements* > = 9|0|Текущая дата, отформатированная, как указано в разделе «Примечания»|

## <a name="security-issues"></a>Проблемы безопасности

Передача в недопустимом не **NULL** значение для буфера приводит к нарушению прав доступа, если *numberOfElements* параметра больше 9.

Передача значения для размера, который больше, чем фактический размер *буфера* приведет к переполнению буфера.

## <a name="remarks"></a>Примечания

Эти функции предоставляют более безопасные версии **_strdate** и **_wstrdate**. **_Strdate_s** функция копирует текущую системную дату в буфер, который указывает *буфера*, в формате **мм**/**дд** / **гг**, где **мм** состоит из двух цифр, представляющее месяц, **дд** состоит из двух цифр, представляющее день, и **гг**  имеет две последние цифры года. Например, строка **12/05/99** представляет 5 декабря, 1999. Буфер должен содержать по крайней мере 9 символов.

**_wstrdate_s** — это двухбайтовая версия **_strdate_s**; аргумент и возвращаемое значение **_wstrdate_s** представляют собой строки расширенных символов. В остальном эти функции ведут себя одинаково.

Если *буфера* — **NULL** указателя, или если *numberOfElements* составляет не более 9 символов, вызывается обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают значение -1 и задайте **errno** для **EINVAL** если буфер **NULL** или если *numberOfElements*меньше или равно 0 или набор **errno** для **ERANGE** Если *numberOfElements* меньше 9.

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
