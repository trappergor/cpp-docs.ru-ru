---
title: _ismbbalnum, _ismbbalnum_l
ms.date: 11/04/2016
apiname:
- _ismbbalnum
- _ismbbalnum_l
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
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
ms.openlocfilehash: 5b5f54754907c09a34b0f4c3bae3e5c27336ca36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554847"
---
# <a name="ismbbalnum-ismbbalnuml"></a>_ismbbalnum, _ismbbalnum_l

Определяет, является ли указанный многобайтовый символ буквой или цифрой.

## <a name="syntax"></a>Синтаксис

```C
int _ismbbalnum(
   unsigned int c
);
int _ismbbalnum_l(
   unsigned int c
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Целое число, которое требуется проверить.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_ismbbalnum** возвращает ненулевое значение, если выражение:

`isalnum(c) || _ismbbkalnum(c)`

имеет ненулевое значение для *c*, или 0, если это не так.

Версия этой функции с **_l** суффиксом идентичны, за исключением того, что она использует переданный параметр языкового стандарта вместо текущего языкового стандарта для его поведения, зависящего от языкового стандарта.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbbalnum**|\<mbctype.h>|
|**_ismbbalnum_l**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
