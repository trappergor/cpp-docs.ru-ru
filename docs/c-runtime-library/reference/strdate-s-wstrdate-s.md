---
title: _strdate_s, _wstrdate_s
description: _strdate_s и _wstrdate_s — это безопасные версии CRT функций _strdate и _wstrdate, которые помещают текущую дату в буфер.
ms.date: 11/01/2019
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
ms.openlocfilehash: 7d04c134fcd19753ac0cecf8cc3b87e902d92e83
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625761"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Скопируйте текущую системную дату в буфер. Эти функции являются версиями [_strdate, _wstrdate](strdate-wstrdate.md) с усовершенствованной безопасностью, как описано в разделе [функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

\ *буфера*
Указатель на буфер для размещения форматируемой строки даты.

*размер* \
Размер буфера в символьных единицах.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. Возвращаемое значение — это код ошибки, если произошел сбой. Коды ошибок определены в ERRNO. H; см. в таблице ниже точные ошибки, создаваемые этой функцией. Дополнительные сведения о кодах ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Условия ошибки

|*buffer*|*size*|Назад|Содержимое *буфера*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(любые)|**EINVAL**|Без изменений|
|Not **null** (указывает на допустимый буфер)|0|**EINVAL**|Без изменений|
|Not **null** (указывает на допустимый буфер)|0 < *размер* < 9|**EINVAL**|Пустая строка|
|Not **null** (указывает на допустимый буфер)|*размер* > = 9|0|Текущая дата, отформатированная, как указано в разделе «Примечания»|

## <a name="security-issues"></a>Проблемы безопасности

Передача недопустимого значения *buffer* , отличного от NULL, приводит к нарушению прав доступа, если значение параметра *size* больше девяти.

Передача значения *размера* , превышающего фактический размер *буфера* , приводит к переполнению буфера.

## <a name="remarks"></a>Заметки

Эти функции предоставляют более безопасные версии **_strdate** и **_wstrdate**. Функция **_strdate_s** Копирует текущую системную дату в буфер, на который указывает *buffer*. Отформатированные `mm/dd/yy`, где `mm` — месяц, состоящих из двух цифр, `dd` день, а `yy` — две последние цифры года. Например, строка `12/05/99` представляет 5 декабря 1999 г. Длина буфера должна составлять не менее девяти символов.

**_wstrdate_s** — это версия **_strdate_s**для расширенных символов; аргумент и возвращаемое значение **_wstrdate_s** являются строками расширенных символов. В остальном эти функции ведут себя одинаково.

Если параметр *buffer* является **пустым** указателем, или *его размер* меньше девяти символов, вызывается обработчик недопустимых параметров. Он описан в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают значение-1. Они устанавливают **значение** **еинвал** , если буфер имеет **значение NULL** , или если *Размер* меньше или равен 0. Или, если *Размер* меньше 9 **, устанавливается значение** **ERANGE** .

В C++использование этих функций упрощено с помощью перегрузок шаблонов. Перегрузки могут автоматически определять длину буфера, что устраняет необходимость указывать аргумент *размера* . Кроме того, они могут автоматически заменять небезопасные функции своими новыми, более безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых подпрограмм:

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

[Управление временем](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[time, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
