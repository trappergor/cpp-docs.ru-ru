---
title: fseek, _lseek Constants
ms.date: 11/04/2016
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
ms.openlocfilehash: 2e6cb2e0d781212f3b5e7758554507dfa438a716
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743368"
---
# <a name="fseek-lseek-constants"></a>fseek, _lseek Constants

## <a name="syntax"></a>Синтаксис

```
#include <stdio.h>
```

## <a name="remarks"></a>Примечания

Аргумент *origin* определяет исходную позицию и может быть одной из следующих констант манифеста.

|Константа|Значение|
|--------------|-------------|
|`SEEK_END`|Конец файла|
|`SEEK_CUR`|Текущая позиция файлового указателя|
|`SEEK_SET`|Начало файла|

## <a name="see-also"></a>См. также

[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
