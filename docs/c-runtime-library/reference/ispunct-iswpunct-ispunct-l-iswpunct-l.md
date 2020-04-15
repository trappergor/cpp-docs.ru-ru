---
title: ispunct, iswpunct, _ispunct_l, _iswpunct_l
ms.date: 4/2/2020
api_name:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
- _o_ispunct
- _o_iswpunct
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
- iswpunct
- _istpunct
- ispunct
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
ms.openlocfilehash: 3072f147d2adff2c50304d2d2052947ca32cb060
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342810"
---
# <a name="ispunct-iswpunct-_ispunct_l-_iswpunct_l"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l

Определяет, представляет ли целое число знак препинания.

## <a name="syntax"></a>Синтаксис

```C
int ispunct(
   int c
);
int iswpunct(
   wint_t c
);
int _ispunct_l(
   int c,
   _locale_t locale
);
int _iswpunct_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемое целое число.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращается ненулевой, если *c* является особым представлением знака пунктуации. **ispunct** возвращает ненулевое значение для любого символа, который не является космическим персонажем или символом, для которого **isalnum** является ненулевым. **iswpunct** возвращает ненулевое значение для любого широкопечатаемого символа, который не является ни широкоугольным персонажем, ни широким символом, для которого **iswalnum** является ненулевым. Каждая из этих процедур возвращает 0, если *c* не удовлетворяет условию теста.

Результат тестового условия для функции **ispunct** зависит от **LC_CTYPE** настройки категории локализуем; см [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. Версии этих функций, которые не имеют **_l** суффикса, используют текущий локали для любого поведения, зависящем от локали; версии, которые имеют **_l** суффикс идентичны, за исключением того, что они используют локали, который прошел в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **ispunct** и **_ispunct_l** не определено, если *c* не eOF или в диапазоне от 0 до 0xFF, включительно. При использовании библиотеки CRT отладки и *c* не является одним из этих значений, функции повышают утверждение.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**-** **istpunct**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ispunct**|\<ctype.h>|
|**iswpunct**|\<ctype.h> или \<wchar.h>|
|**_ispunct_l**|\<ctype.h>|
|**_iswpunct_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
