---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 11/04/2016
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
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
ms.openlocfilehash: 6dd564a27ee7f3c2bb095564e5c9423249d6babc
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210618"
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

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

Каждая из этих подпрограмм преобразует копию *c*, если это возможно и возвращает результат.

Если *c* представляет собой расширенный символ, для которого **iswlower** имеет ненулевое значение и существует соответствующий расширенный символ, для которого [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) не равно нулю, **towupper** возвращает соответствующий расширенный символ; в противном случае **towupper** возвращает *c* без изменений.

Возвращаемое значение для указания ошибки не зарезервировано.

Чтобы **toupper** давала ожидаемые результаты, [__isascii](isascii-isascii-iswascii.md) и [islower](islower-iswlower-islower-l-iswlower-l.md) должны возвращать ненулевое значение.

## <a name="remarks"></a>Примечания

Каждая из этих подпрограмм преобразует указанную строчную букву в прописную, если это возможно и уместно. Преобразование регистра **towupper** является языковым стандартом. Изменяются только символы, соответствующие текущему языковому стандарту. Функции, не имеющие **_l** суффикс используют текущий языковой языкового стандарта. Версии этих функций с **_l** суффикс, принимают языковой стандарт как параметр и использовать его вместо текущего языкового языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Чтобы **toupper** давала ожидаемые результаты, [__isascii](isascii-isascii-iswascii.md) и [isupper](isupper-isupper-l-iswupper-iswupper-l.md) должны возвращать ненулевое значение.

[Процедуры преобразования данных](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** и **_towupper_l** не зависят от языкового стандарта и не предназначены для непосредственного вызова. Они предназначены для внутреннего использования **_totupper_l**.

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
