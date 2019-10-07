---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 11/04/2016
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
ms.openlocfilehash: e17f139789b2c37292764f2e4508b59cddd2c03e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957909"
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

*c*<br/>
Символ для преобразования.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм преобразует копию *c*, если это возможно, и возвращает результат.

Если *c* является расширенным символом, для которого **iswlower** не равен нулю и имеется соответствующий широкий символ, для которого [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) имеет ненулевое значение, **товуппер** возвращает соответствующий расширенный символ. в противном случае **товуппер** возвращает *c* без изменений.

Возвращаемое значение для указания ошибки не зарезервировано.

Чтобы обеспечить ожидаемые результаты, [__isascii](isascii-isascii-iswascii.md) и " [Нижний](islower-iswlower-islower-l-iswlower-l.md) " должны возвращать ненулевое **значение.**

## <a name="remarks"></a>Примечания

Каждая из этих подпрограмм преобразует указанную строчную букву в прописную, если это возможно и уместно. Преобразование регистра **товуппер** зависит от языкового стандарта. Изменяются только символы, соответствующие текущему языковому стандарту. Функции без суффикса **_l** используют текущую национальную настройку. Версии этих функций с суффиксом **_l** принимают языковой стандарт в качестве параметра и используют его вместо текущего установленного языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Чтобы дать ожидаемые результаты, [__isascii](isascii-isascii-iswascii.md) и [Upper](isupper-isupper-l-iswupper-iswupper-l.md) должны возвращать ненулевое **значение.**

[Процедуры преобразования данных](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** и **_towupper_l** не имеют зависимости от языкового стандарта и не предназначены для непосредственного вызова. Они предоставляются для внутреннего использования **_totupper_l**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [Функции to](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>См. также

[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Функции to](../../c-runtime-library/to-functions.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
