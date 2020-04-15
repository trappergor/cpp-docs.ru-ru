---
title: _strdate_s, _wstrdate_s
description: _strdate_s и _wstrdate_s являются безопасными ВЕРСИЯми CRT _strdate и _wstrdate функций, которые ставят текущую дату в буфер.
ms.date: 4/2/2020
api_name:
- _strdate_s
- _wstrdate_s
- _o__strdate_s
- _o__wstrdate_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b4d977ba3546eae17218c63b1786fd26c784d340
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359821"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Скопируйте текущую системную дату в буфер. Эти функции являются версиями [_strdate, _wstrdate](strdate-wstrdate.md) с улучшениями безопасности, как описано в [функциях безопасности в CRT.](../../c-runtime-library/security-features-in-the-crt.md)

## <a name="syntax"></a>Синтаксис

```C
errno_t _strdate_s(
   char *buffer,
   size_t size
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t size
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

*Буфера*\
Указатель на буфер для того, чтобы поместить отформатированную строку даты.

*Размер*\
Размер буфера в единицах символов.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. Значение возврата — это код ошибки при сбое. Коды ошибок определены в ERRNO. H; см. в таблице ниже точные ошибки, создаваемые этой функцией. Дополнительные сведения о кодах ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Условия ошибок

|*Буфера*|*Размер*|Возвращает|Содержимое *буфера*|
|--------------|------------------------|------------|--------------------------|
|**Null**|(любые)|**EINVAL**|Без изменений|
|Не **NULL** (указывая на действительный буфер)|0|**EINVAL**|Без изменений|
|Не **NULL** (указывая на действительный буфер)|0 *< размер* < 9|**EINVAL**|Пустая строка.|
|Не **NULL** (указывая на действительный буфер)|*размер* >No 9|0|Текущая дата, отформатированная, как указано в разделе «Примечания»|

## <a name="security-issues"></a>Проблемы с безопасностью

Прохождение в недействительное, неnull значение для *буфера* приводит к нарушению доступа, если параметр *размера* больше девяти.

Прохождение значения для *размера,* превышающее фактический размер *буфера,* приводит к перезапуску буфера.

## <a name="remarks"></a>Remarks

Эти функции обеспечивают более безопасные версии **_strdate** и **_wstrdate.** **Функция _strdate_s** копирует текущую дату системы в буфер, на который указывает *буфер.* Он `mm/dd/yy`отформатирован, `mm` где двузначный `dd` месяц, является двузначным днем, и `yy` последние две цифры года. Например, строка `12/05/99` представляет 5 декабря 1999 г. Буфер должен быть не менее девяти символов в длину.

**_wstrdate_s** является широкохарактерным вариантом **_strdate_s;** аргументивация и значение возврата **_wstrdate_s** являются широкохарактерными строками. В остальном эти функции ведут себя одинаково.

Когда *буфер* является указателем **NULL** или *размер* меньше девяти символов, вызывается обработчик параметров недействительного. Это описано в [параметре проверки](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции возвращаются -1. Они устанавливают **errno** к **EINVAL,** если буфер **null** или если *размер* меньше или равен 0. Или, они устанавливают **errno** к **ERANGE** если *размер* меньш чем 9.

В СЗ использование этих функций упрощается с помощью перегрузок шаблонов. Перегрузки могут автоматически выводить длину буфера, что устраняет необходимость указать аргумент *размера.* Кроме того, они могут автоматически заменять незащищенные функции новыми, более безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладка библиотеки версии этих функций сначала заполнить буфер с 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Общий текст рутинного отображения:

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

## <a name="see-also"></a>См. также раздел

[Управление временем](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[время, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
