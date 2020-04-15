---
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l
ms.date: 4/2/2020
api_name:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
- _o_isgraph
- _o_iswgraph
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
- _isgraph_l
- _iswgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
ms.openlocfilehash: b10038a783f05512f12f25a231dd553a1863c143
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343828"
---
# <a name="isgraph-iswgraph-_isgraph_l-_iswgraph_l"></a>isgraph, iswgraph, _isgraph_l, _iswgraph_l

Определяет, представляет ли целое число графический символ.

## <a name="syntax"></a>Синтаксис

```C
int isgraph(
   int c
);
int iswgraph(
   wint_t c
);
int _isgraph_l(
   int c,
   _locale_t locale
);
int _iswgraph_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращается ненулевой, если *c* является конкретным представлением печатаемого символа, кроме пространства. **isgraph** возвращает ненулевое значение, если *c* является распечатанный символ, кроме пространства. **iswgraph** возвращает ненулевое значение, если *c* является распечатанный широкий символ, кроме широкого пространства символов. Каждая из этих процедур возвращает 0, если *c* не удовлетворяет условию теста.

Версии этих функций, которые имеют **_l** суффикса, используют место, которое передается в вместо текущего локализации для их поведения, зависящем от локализации. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isgraph** и **_isgraph_l** не определено, если *c* не EOF или в диапазоне от 0 до 0xFF, включительно. При использовании библиотеки CRT отладки и *c* не является одним из этих значений, функции повышают утверждение.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraph**|**isgraph**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraph**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isgraph**|\<ctype.h>|
|**iswgraph**|\<ctype.h> или \<wchar.h>|
|**_isgraph_l**|\<ctype.h>|
|**_iswgraph_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
