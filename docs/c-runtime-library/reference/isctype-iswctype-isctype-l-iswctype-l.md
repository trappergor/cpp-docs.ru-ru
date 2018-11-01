---
title: _isctype, iswctype, _isctype_l, _iswctype_l
ms.date: 11/04/2016
apiname:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
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
apitype: DLLExport
f1_keywords:
- iswctype
- _isctype
- _isctype_l
- _iswctype
- isctype
- iswctype_l
- isctype_l
- _iswctype_l
helpviewer_keywords:
- isctype_l function
- iswctype_l function
- iswctype function
- _isctype function
- _isctype_l function
- _iswctype_l function
- isctype function
- _iswctype function
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
ms.openlocfilehash: c5eb0b51cf0371100ed884221ee04885dfbe9ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563167"
---
# <a name="isctype-iswctype-isctypel-iswctypel"></a>_isctype, iswctype, _isctype_l, _iswctype_l

Тесты *c* для свойства ctype, определяемое *desc* аргумент. Для каждого допустимого значения *desc*, имеется подпрограмма эквивалентная расширенных символов.

## <a name="syntax"></a>Синтаксис

```C
int _isctype(
   int c,
   _ctype_t desc
);
int _isctype_l(
   int c,
   _ctype_t desc,
   _locale_t locale
);
int iswctype(
   wint_t c,
   wctype_t desc
);
int _iswctype_l(
   wint_t c,
   wctype_t desc,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Проверяемое целое число.

*DESC*<br/>
Свойство для проверки. Как правило, извлекается с использованием ctype или [wctype](wctype.md).

*locale*<br/>
Языковой стандарт, используемый для любых зависящих от языкового стандарта проверок.

## <a name="return-value"></a>Возвращаемое значение

**_isctype** и **iswctype** возвращают ненулевое значение, если *c* имеет свойство, указанное *desc* в текущем языковом стандарте, или 0, если это не так. Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **_isctype** и **_isctype_l** не определено, если *c* не является символом EOF или в диапазоне от 0 до 0xFF включительно. Если используется библиотека отладки CRT и *c* не является одним из следующих значений, функции вызывают утверждение.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|Н/Д|**_isctype**|Н/Д|**_iswctype**|
|Н/Д|**_isctype_l**|Н/Д|**_iswctype_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_isctype**|\<ctype.h>|
|**iswctype**|\<ctype.h> или \<wchar.h>|
|**_isctype_l**|\<ctype.h>|
|**_iswctype_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
