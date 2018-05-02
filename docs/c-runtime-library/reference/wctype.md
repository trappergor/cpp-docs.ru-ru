---
title: wctype | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbad04d3c56015ddea10a058ae8b262d7f94d40f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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

Если **LC_CTYPE** категории текущего языкового стандарта не определяет правило классификации, имя которого соответствует строке свойства *свойство*, функция возвращает ноль. В противном случае возвращается ненулевое значение, подходящее для использования в качестве второго аргумента последующего вызова [towctrans](towctrans.md).

## <a name="remarks"></a>Примечания

Функция определяет правило классификации кодов расширенных символов. Следующие пары вызовов имеют аналогичное поведение во всех языковых стандартах (но реализация позволяет определить дополнительные правила классификации даже в языковом стандарте "C").

|Функция|Эквивалентно|
|--------------|-------------|
|iswalnum(c)|iswctype (c, wctype ("alnum"))|
|iswalpha(c)|iswctype (c, wctype ("альфа"))|
|iswcntrl(c)|iswctype (c, wctype («комбинации клавиш CTRL»))|
|iswdigit(c)|iswctype (c, wctype («цифра"))|
|iswgraph(c)|iswctype (c, wctype («график»))|
|iswlower(c)|iswctype (c, wctype («ниже»))|
|iswprint(c)|iswctype (c, wctype ("print"))|
|iswpunct(c)|iswctype (c, wctype («пунктуация»))|
|iswspace(c)|iswctype (c, wctype ("space"))|
|iswupper(c)|iswctype (c, wctype («верхний»))|
|iswxdigit(c)|iswctype (c, wctype («xdigit»))|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
