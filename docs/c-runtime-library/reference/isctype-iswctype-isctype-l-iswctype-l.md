---
title: _isctype, iswctype, _isctype_l, _iswctype_l
ms.date: 4/2/2020
api_name:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
- _o__isctype
- _o__isctype_l
- _o__iswctype_l
- _o_iswctype
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 5beedd8a5da6848fc8c43ab1a27ee52402fe394e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343855"
---
# <a name="_isctype-iswctype-_isctype_l-_iswctype_l"></a>_isctype, iswctype, _isctype_l, _iswctype_l

Тесты *c* для свойства ctype, указанные аргументом *desc.* Для каждого допустимого значения *desc*существует эквивалентная процедура классификации широкого характера.

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

*C*<br/>
Проверяемое целое число.

*Desc*<br/>
Свойство для проверки. Как правило, извлекается с использованием ctype или [wctype](wctype.md).

*Языкового стандарта*<br/>
Языковой стандарт, используемый для любых зависящих от языкового стандарта проверок.

## <a name="return-value"></a>Возвращаемое значение

**_isctype** и **iswctype** возвращают ненулевое значение, если *c* имеет свойство, указанное *desc* в текущем локаль или 0, если это не так. Версии этих функций с **_l** суффикса идентичны, за исключением того, что они используют локали, передаваемые в вместо текущего локализации для их поведения, зависящем от локализации. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **_isctype** и **_isctype_l** не определено, если *c* не EOF или в диапазоне от 0 до 0xFF, включительно. При использовании библиотеки CRT отладки и *c* не является одним из этих значений, функции повышают утверждение.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|Недоступно|**_isctype**|Недоступно|**_iswctype**|
|Недоступно|**_isctype_l**|Недоступно|**_iswctype_l**|

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_isctype**|\<ctype.h>|
|**iswctype**|\<ctype.h> или \<wchar.h>|
|**_isctype_l**|\<ctype.h>|
|**_iswctype_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
