---
title: auto_rename
ms.date: 11/04/2016
f1_keywords:
- auto_rename
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
ms.openlocfilehash: ba07b8532ba64c99f835e59d7c71aac8e3f2b03d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035124"
---
# <a name="autorename"></a>auto_rename

**Конкретных C++**

Переименовывает зарезервированные слова C++ путем добавления двух знаков подчеркивания (__) к именам переменных, чтобы разрешить потенциальные конфликты имен.

## <a name="syntax"></a>Синтаксис

```
auto_rename
```

## <a name="remarks"></a>Примечания

Этот атрибут используется при импорте библиотеки типов, в которой в качестве имен переменных используется одно или несколько зарезервированных слов C или C++ (ключевых слов или макросов).

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)