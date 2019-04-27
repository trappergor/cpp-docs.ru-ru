---
title: rename_search_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_search_namespace
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
ms.openlocfilehash: ca5d24ca9cc12e9defaa395cf150bc3c04ee4439
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179780"
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