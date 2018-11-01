---
title: rename_search_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_search_namespace
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
ms.openlocfilehash: 1e8d682b3d52c80779d62443074614480ed514ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510740"
---
# <a name="renamesearchnamespace"></a>rename_search_namespace

**Конкретных C++**

Имеет ту же функциональность, что [rename_namespace](../preprocessor/rename-namespace.md) атрибут, однако применяется для библиотек типов, используемых вами `#import` директиву [auto_search](../preprocessor/auto-search.md) атрибута.

## <a name="syntax"></a>Синтаксис

```
rename_search_namespace("NewName")
```

### <a name="parameters"></a>Параметры

*NewName*<br/>
Новое имя пространства имен.

## <a name="remarks"></a>Примечания

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)