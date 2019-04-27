---
title: wctype
ms.date: 11/04/2016
apiname:
- wctype
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
apitype: DLLExport
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 81caf8e1ab04635d205d7b01af2d4c2896eec01c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155320"
---
# <a name="wctype"></a>wctype

Определяет правило классификации кодов расширенных символов.

## <a name="syntax"></a>Синтаксис

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Параметры

*свойство*<br/>
Строка свойства.

## <a name="return-value"></a>Возвращаемое значение

Если **LC_CTYPE** категории текущего языкового стандарта не определяет правило классификации, имя которого соответствует строке свойства *свойство*, функция возвращает нуль. В противном случае возвращается ненулевое значение, подходящее для использования в качестве второго аргумента последующего вызова [towctrans](towctrans.md).

## <a name="remarks"></a>Примечания

Функция определяет правило классификации кодов расширенных символов. Следующие пары вызовов имеют аналогичное поведение во всех языковых стандартах (но реализация позволяет определить дополнительные правила классификации даже в языковом стандарте "C").

|Функция|Эквивалентно|
|--------------|-------------|
|iswalnum(c)|iswctype (c, wctype ("alnum"))|
|iswalpha(c)|iswctype (c, wctype ("альфа"))|
|iswcntrl(c)|iswctype(c, wctype( "cntrl" ) )|
|iswdigit(c)|iswctype(c, wctype( "digit" ) )|
|iswgraph(c)|iswctype(c, wctype( "graph" ) )|
|iswlower(c)|iswctype (c, wctype («ниже»))|
|iswprint(c)|iswctype(c, wctype( "print" ) )|
|iswpunct(c)|iswctype (c, wctype ("punct"))|
|iswspace(c)|iswctype(c, wctype( "space" ) )|
|iswupper(c)|iswctype (c, wctype ("верхний"))|
|iswxdigit(c)|iswctype (c, wctype ("xdigit"))|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
