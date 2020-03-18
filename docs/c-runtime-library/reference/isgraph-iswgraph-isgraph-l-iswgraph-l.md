---
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l
ms.date: 11/04/2016
api_name:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
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
ms.openlocfilehash: 282f11dfa6a4545b672419d42fe960c0e5001fbf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442959"
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

*c*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм возвращает ненулевое значение, если *c* — конкретное представление печатного символа, отличного от пробела. Функция **Graph** возвращает ненулевое значение, если *c* является печатным символом, отличным от пробела. **исвграф** возвращает ненулевое значение, если *c* — широкий печатный символ, отличный от расширенного пространства символов. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста.

Версии этих функций с суффиксом **_l** используют переданный языковой стандарт вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта. Дополнительные сведения см. в разделе [Locale](../../c-runtime-library/locale.md).

Поведение функций и **isgraph** **_isgraph_l** не определено, если *c* не является EOF или находится в диапазоне от 0 до 0xFF включительно. Если используется библиотека отладки CRT и *c* не является одним из этих значений, функции создают утверждение.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraph**|**isgraph**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraph**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isgraph**|\<ctype.h>|
|**iswgraph**|\<ctype.h> или \<wchar.h>|
|**_isgraph_l**|\<ctype.h>|
|**_iswgraph_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
