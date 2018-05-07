---
title: __max | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __max
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
- max
- __max
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d223f4288ccf40646e8f560cec7243b7e8f9f649
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="max"></a>__max

Макрос препроцессора, который возвращает большее из двух значений.

## <a name="syntax"></a>Синтаксис

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>Параметры

*a*, *b*<br/>
Сравниваемые значения любого числового типа данных.

## <a name="return-value"></a>Возвращаемое значение

**__max-** возвращает большее из его аргументов.

## <a name="remarks"></a>Примечания

**__Max-** макрос сравнивает два значения и возвращает значение больше одного. Аргументы могут быть любого числового типа данных со знаком или без знака. Оба аргумента и возвращаемое значение должны принадлежать к одному типу данных.

Аргумента, возвращаемого вычисляется дважды макросом. Это может привести к непредвиденным результатам, если аргумент представляет собой выражение, изменяет его значение, когда оно вычисляется, такие как `*p++`.

## <a name="requirements"></a>Требования

|Макрос|Обязательный заголовок|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в приведенных ниже примерах для функции [__min](min.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>