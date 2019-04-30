---
title: no_namespace
ms.date: 11/04/2016
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: f6bd60de02bf0166d5cf0b0cd1bc1de56ceda5bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326564"
---
# <a name="nonamespace"></a>no_namespace
**Конкретных C++**

Указывает, что пространство имен не генерируется компилятором.

## <a name="syntax"></a>Синтаксис

```
no_namespace
```

## <a name="remarks"></a>Примечания

Содержимое библиотеки типов в файле заголовка `#import` обычно определяется в пространстве имен. Имя пространства имен, указанное в `library` инструкции исходного файла IDL. Если **no_namespace** атрибут указан, то это пространство имен не генерируется компилятором.

Если вы хотите использовать другое имя пространства имен, используйте [rename_namespace](../preprocessor/rename-namespace.md) атрибутом.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)