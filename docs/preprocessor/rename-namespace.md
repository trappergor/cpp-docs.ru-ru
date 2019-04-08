---
title: rename_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 7b3917a7114ca44d092f10a7831bb35bc64e9387
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039881"
---
# <a name="renamenamespace"></a>rename_namespace

**Блок, относящийся только к языку C++**

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

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)