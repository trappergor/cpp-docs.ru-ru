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
ms.openlocfilehash: 67599ced3ee775d9e6d702a9fb9e66e0580240e4
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519156"
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