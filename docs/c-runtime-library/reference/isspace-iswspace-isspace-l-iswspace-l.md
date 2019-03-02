---
title: isspace, iswspace, _isspace_l, _iswspace_l
ms.date: 11/04/2016
apiname:
- iswspace
- _isspace_l
- _iswspace_l
- isspace
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
- iswspace
- _istspace
- isspace
helpviewer_keywords:
- iswspace function
- isspace function
- _iswspace_l function
- _isspace_l function
- iswspace_l function
- isspace_l function
- _istspace function
- istspace function
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
ms.openlocfilehash: bb3d18e5034be50d69531d2686b6c270ba55a1cb
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210215"
---
# <a name="isspace-iswspace-isspacel-iswspacel"></a>isspace, iswspace, _isspace_l, _iswspace_l

Определяет, представляет ли целое число символ пробела.

## <a name="syntax"></a>Синтаксис

```C
int isspace(
   int c
);
int iswspace(
   wint_t c
);
int _isspace_l(
   int c,
   _locale_t locale
);
int _iswspace_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Проверяемое целое число.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждый из этих подпрограмм возвращает ненулевое значение, если *c* — конкретное представление символа пробела. **isspace** возвращает ненулевое значение, если *c* является символом пробела (0x09 – 0x0D или 0x20). Результат проверки условия для **isspace** функция зависит от **LC_CTYPE** категории языкового стандарта; см. описание [setlocale, _wsetlocale](setlocale-wsetlocale.md) Дополнительные сведения. Версии этих функций, у которых нет **_l** суффикс используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; версии, которые имеют **_l** суффиксом идентичны, за исключением того, что они используют языковой стандарт, переданный в качестве. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

**iswspace** возвращает ненулевое значение, если *c* представляет собой расширенный символ, соответствующий стандартный символ пробела.

Поведение **isspace** и **_isspace_l** не определено, если *c* не является символом EOF или в диапазоне от 0 до 0xFF включительно. Если используется библиотека отладки CRT и *c* не является одним из следующих значений, функции вызывают утверждение.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istspace**|**isspace**|[_ismbcspace](ismbcgraph-functions.md)|**iswspace**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isspace**|\<ctype.h>|
|**iswspace**|\<ctype.h> или \<wchar.h>|
|**_isspace_l**|\<ctype.h>|
|**_iswspace_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
