---
title: Константы setvbuf
ms.date: 11/04/2016
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
ms.openlocfilehash: 8936789f4e3c9349e9d79616c8506c044dc79f70
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220404"
---
# <a name="setvbuf-constants"></a>Константы setvbuf

## <a name="syntax"></a>Синтаксис

```
#include <stdio.h>
```

## <a name="remarks"></a>Примечания

Эти константы представляют тип буфера для `setvbuf`.

Возможные значения определяются следующими константами манифеста:

|Константа|Значение|
|--------------|-------------|
|`_IOFBF`|Полная буферизация Используется буфер, указанный в вызове функции `setvbuf`, и его размер равен указанному в вызове функции `setvbuf`. Если указатель буфера имеет значение **NULL**, используется автоматически выделенный буфер указанного размера.|
|`_IOLBF`|Эквивалентно `_IOFBF`.|
|`_IONBF`|Буфер не используется, независимо от аргументов в вызове функции `setvbuf`.|

## <a name="see-also"></a>См. также раздел

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
