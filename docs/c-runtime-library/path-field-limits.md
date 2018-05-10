---
title: Пределы поля "Путь" | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs:
- C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0672245a87cdbcf2a4a6dba6d36c675f3faafbc5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="path-field-limits"></a>Пределы поля "Путь"

## <a name="syntax"></a>Синтаксис

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>Примечания

Эти константы определяют максимальную длину пути и отдельных полей в пути.

|Константа|Значение|
|--------------|-------------|
|`_MAX_DIR`|Максимальная длина компонента каталога|
|`_MAX_DRIVE`|Максимальная длина компонента диска|
|`_MAX_EXT`|Максимальная длина компонента расширения|
|`_MAX_FNAME`|Максимальная длина компонента имени файла|
|`_MAX_PATH`|Максимальная длина полного пути|

> [!NOTE]
> Среда выполнения языка C поддерживает длину пути до 32768 символов, но поддержка таких длинных путей зависит от операционной системы, а именно, от файловой системы. Для полной обратной совместимости с файловыми системами FAT32 общая длина полей не должна превышать `_MAX_PATH`. Файловая система Windows NTFS поддерживает пути длиной до 32 768 символов, но только при использовании API Юникода. Если вы используете длинные пути, указывайте в начале пути символы \\\\?\ и используйте версии для Юникода функций среды выполнения языка С.

## <a name="see-also"></a>См. также

[Глобальные константы](../c-runtime-library/global-constants.md)