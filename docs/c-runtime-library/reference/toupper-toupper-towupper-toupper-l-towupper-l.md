---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 4/2/2020
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
- _o__toupper
- _o__toupper_l
- _o__towupper_l
- _o_toupper
- _o_towupper
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
ms.openlocfilehash: 85c218fdb3f5153e572e434bffbdb64510554d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362322"
---
# <a name="toupper-_toupper-towupper-_toupper_l-_towupper_l"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

Преобразуют символ в верхний регистр.

## <a name="syntax"></a>Синтаксис

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Символ для преобразования.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм преобразует копию *c,* если это возможно, и возвращает результат.

Если *c* является широким символом, для которого **swlower** является незеролевым и есть соответствующий широкий характер, для которого [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) является ненулевым, **буксир** возвращает соответствующий широкий характер; в противном случае, **буксир возвращается** *c* неизменным.

Возвращаемое значение для указания ошибки не зарезервировано.

Для того, чтобы **toupper** дать ожидаемые результаты, [__isascii](isascii-isascii-iswascii.md) и [более медленно](islower-iswlower-islower-l-iswlower-l.md) должны как вернуться ненулевой.

## <a name="remarks"></a>Remarks

Каждая из этих подпрограмм преобразует указанную строчную букву в прописную, если это возможно и уместно. Преобразование случая **towupper** locale-специфически. Изменяются только символы, соответствующие текущему языковому стандарту. Функции без **_l** суффикса используют в настоящее время установленный локали. Версии этих функций с **_l** суффикса принимают локали в качестве параметра и используют его вместо установленного в настоящее время локали. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Для того, чтобы **toupper** дать ожидаемые результаты, [__isascii](isascii-isascii-iswascii.md) и [изупер](isupper-isupper-l-iswupper-iswupper-l.md) должны как вернуться ненулевой.

[Процедуры преобразования данных](../../c-runtime-library/data-conversion.md)

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**Toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** и **_towupper_l** не имеют локальной зависимости и не должны называться напрямую. Они предоставляются для внутреннего использования **_totupper_l.**

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции to](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>См. также раздел

[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Функции to](../../c-runtime-library/to-functions.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
