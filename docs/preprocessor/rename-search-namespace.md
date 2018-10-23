---
title: rename_search_namespace | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_search_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0cc95851c4aa7127e690ec013b9d06d57f2730d
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808892"
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