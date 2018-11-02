---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
ms.date: 11/04/2016
apiname:
- _ismbcpunct_l
- _ismbcblank
- _ismbcprint
- _ismbcgraph_l
- _ismbcblank_l
- _ismbcpunct
- _ismbcprint_l
- _ismbcspace_l
- _ismbcspace
- _ismbcgraph
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbcspace
- _ismbcgraph
- _ismbcpunct
- ismbcspace_l
- ismbcgraph
- _ismbcgraph_l
- _ismbcprint
- _ismbcspace_l
- ismbcprint
- ismbcgraph_l
- ismbcspace
- ismbcpunct
helpviewer_keywords:
- ismbcspace_l function
- _ismbcprint_l function
- ismbcspace function
- ismbcpunct function
- _ismbcspace_l function
- _ismbcprint function
- ismbcprint function
- _ismbcgraph function
- ismbcgraph_l function
- _ismbcpunct_l function
- ismbcpunct_l function
- ismbcprint_l function
- _ismbcpunct function
- ismbcgraph function
- _ismbcgraph_l function
- _ismbcspace function
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
ms.openlocfilehash: 05946def8c4d832751554a1653afa98c9965fee9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626217"
---
# <a name="ismbcgraph-ismbcgraphl-ismbcprint-ismbcprintl-ismbcpunct-ismbcpunctl-ismbcblank-ismbcblankl-ismbcspace-ismbcspacel"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l

Определяет, является ли символ графическим, отображаемым символом, знаком препинания или пробелом.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _ismbcgraph(
   unsigned int c
);
int _ismbcgraph_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcprint(
   unsigned int c
);
int _ismbcprint_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcpunct(
   unsigned int c
);
int _ismbcpunct_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcblank(
   unsigned int c
);
int _ismbcblank_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcspace(
   unsigned int c
);
int _ismbcspace_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется определить.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет. Если *c* < = 255 и есть соответствующая **_ismbb** подпрограммы (например, **_ismbcalnum** соответствует **_ismbbalnum**), результат является возвращаемым значением соответствующего **_ismbb** подпрограммы.

Версии этих функций идентичны, за исключением тех, которые имеют **_l** суффикс используют языковой стандарт, переданный для поведения, зависящего от языкового стандарта вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Примечания

Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.

|Подпрограмма|Условие теста|Пример кодовой страницы 932|
|-------------|--------------------|---------------------------|
|**_ismbcgraph**|Графические символы|Возвращает ненулевое значение, только если *c* является однобайтовым представлением любого ASCII или катаканы печатного символа, за исключением пробел ().|
|**_ismbcprint**|Печатные символы|Возвращает ненулевое значение, только если *c* — это — однобайтовое представление любой ASCII или катаканы печатного символа, включая пробел ().|
|**_ismbcpunct**|Пунктуация|Возвращает ненулевое значение, только если *c* является однобайтовым представлением любого знака препинания ASCII или катаканы.|
|**_ismbcblank**|Пробелы или символы горизонтальной табуляции|Возвращает ненулевое значение, только если *c* является пробел или символ горизонтальной табуляции: *c*= 0x20 или *c*= 0x09.|
|**_ismbcspace**|Пробел|Возвращает ненулевое значение, только если *c* является символом пробела: *c*= 0x20 или 0x09 < =*c*< = 0x0D.|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbcgraph**|\<mbstring.h>|
|**_ismbcgraph_l**|\<mbstring.h>|
|**_ismbcprint**|\<mbstring.h>|
|**_ismbcprint_l**|\<mbstring.h>|
|**_ismbcpunct**|\<mbstring.h>|
|**_ismbcpunct_l**|\<mbstring.h>|
|**_ismbcblank**|\<mbstring.h>|
|**_ismbcblank_l**|\<mbstring.h>|
|**_ismbcspace**|\<mbstring.h>|
|**_ismbcspace_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Подпрограммы _ismbc](../../c-runtime-library/ismbc-routines.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
