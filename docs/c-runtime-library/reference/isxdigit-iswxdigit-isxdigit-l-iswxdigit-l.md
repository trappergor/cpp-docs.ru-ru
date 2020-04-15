---
title: isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l
ms.date: 4/2/2020
api_name:
- _iswxdigit_l
- iswxdigit
- isxdigit
- _isxdigit_l
- _o_iswxdigit
- _o_isxdigit
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
- iswxdigit
- isxdigit
- _istxdigit
helpviewer_keywords:
- isxdigit function
- istxdigit function
- _iswxdigit_l function
- _istxdigit function
- _isxdigit_l function
- iswxdigit_l function
- isxdigit_l function
- hexadecimal characters
- iswxdigit function
ms.assetid: c8bc5146-0b58-4e3f-bee3-f2318dd0f829
ms.openlocfilehash: c2f6e7956048a30313ba8eb9a11a37fccdc49197
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342745"
---
# <a name="isxdigit-iswxdigit-_isxdigit_l-_iswxdigit_l"></a>isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l

Определяет, представляет ли целое число шестнадцатеричный символ.

## <a name="syntax"></a>Синтаксис

```C
int isxdigit(
   int c
);
int iswxdigit(
   wint_t c
);
int _isxdigit_l(
   int c,
   _locale_t locale
);
int _iswxdigit_l(
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

Каждая из этих процедур возвращается ненулевой, если *c* является особым представлением гексадецимальной цифры. **isxdigit** возвращает ненулевое значение, если *c* является гексадецимальной цифрой (A - F, a - f, или 0 - 9). **iswxdigit** возвращает ненулевое значение, если *c* является широким символом, который соответствует гексадецмальной цифре. Каждая из этих процедур возвращает 0, если *c* не удовлетворяет условию теста.

Для локализации "C" функция **iswxdigit** не поддерживает полноширинные гексадецимальные символы Unicode.

Версии этих функций, которые имеют **_l** суффикса, используют место, которое передается в вместо текущего локализации для их поведения, зависящем от локализации. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isxdigit** и **_isxdigit_l** не определено, если *c* не eOF или в диапазоне от 0 до 0xFF, включительно. При использовании библиотеки CRT отладки и *c* не является одним из этих значений, функции повышают утверждение.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istxdigit**|**isxdigit**|**isxdigit**|**iswxdigit**|

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isxdigit**|\<ctype.h>|
|**iswxdigit**|\<ctype.h> или \<wchar.h>|
|**_isxdigit_l**|\<ctype.h>|
|**_iswxdigit_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
