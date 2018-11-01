---
title: rename_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 6521fe0a5bfbe482bf2aed8f5a32221abdc6d6d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531603"
---
# <a name="renamenamespace"></a>rename_namespace

**Конкретных C++**

Переименовывает пространство имен, к которому относится содержимое библиотеки типов.

## <a name="syntax"></a>Синтаксис

```
rename_namespace("NewName")
```

### <a name="parameters"></a>Параметры

*NewName*<br/>
Новое имя пространства имен.

## <a name="remarks"></a>Примечания

Он принимает один аргумент, *NewName*, который задает новое имя для пространства имен.

Чтобы удалить пространство имен, используйте [no_namespace](../preprocessor/no-namespace.md) атрибутом.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)