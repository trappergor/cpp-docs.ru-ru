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
ms.openlocfilehash: 661cf64c71e06c222503388df198d47429566602
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523810"
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
|`_IOFBF`|Полная буферизация. Используется буфер, указанный в вызове функции `setvbuf`, и его размер равен указанному в вызове функции `setvbuf`. Если указатель буфера имеет значение **NULL**, используется автоматически выделенный буфер указанного размера.|
|`_IOLBF`|Эквивалентно `_IOFBF`.|
|`_IONBF`|Буфер не используется, независимо от аргументов в вызове функции `setvbuf`.|

## <a name="see-also"></a>См. также

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)