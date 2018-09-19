---
title: Константы setvbuf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a367522c2f22007abcf24cdf74ada467d94b104
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032826"
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