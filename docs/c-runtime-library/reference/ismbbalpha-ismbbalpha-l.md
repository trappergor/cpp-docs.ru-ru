---
title: _ismbbalpha, _ismbbalpha_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ismbbalpha
- _ismbbalpha_l
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
- ismbbalpha
- ismbbalpha_l
- _ismbbalpha
- _ismbbalpha_l
dev_langs:
- C++
helpviewer_keywords:
- ismbbalpha function
- ismbbalpha_l function
- _ismbbalpha function
- _ismbbalpha_l function
ms.assetid: 8e54cb92-fc2b-41f5-8ab4-b22ac8aa9ad0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fa4708cf4c5c297d5a537728d4e5988f21e21b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ismbbalpha-ismbbalphal"></a>_ismbbalpha, _ismbbalpha_l

Определяет, является ли указанный многобайтовой символ альфа-символом.

## <a name="syntax"></a>Синтаксис

```C
int _ismbbalpha(
   unsigned int c
);
int _ismbbalpha_l(
   unsigned int c
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Целое число, которое требуется проверить.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_ismbbalpha** возвращает ненулевое значение, если выражение:

`isalpha(c) || _ismbbkalnum(c)`

имеет ненулевое значение для *c*, или 0, если это не так. **_ismbbalpha** использует текущий языковой стандарт для любых параметров символов, зависящих от языкового стандарта. **_ismbbalpha_l** идентична за исключением того, что она использует переданный языковой стандарт.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbbalpha**|\<mbctype.h>|
|**_ismbbalpha_l**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
