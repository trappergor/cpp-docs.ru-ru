---
title: btowc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d0e56649218e6249550638af4e198cbd1284bc2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393320"
---
# <a name="btowc"></a>btowc

Определяет, представляет ли целое число допустимый однобайтовый символ в начальном состоянии сдвига.

## <a name="syntax"></a>Синтаксис

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Параметры

*Символ*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Возвращает представление символа в виде расширенного символа, если целое число представляет допустимый однобайтовый символ в начальном состоянии сдвига. Возвращает символ WEOF, если целое число является символом EOF или не является допустимым однобайтовым символом в начальном состоянии сдвига. Выходные данные этой функции определяется текущим **LC_TYPE** языкового стандарта.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**btowc**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
