---
title: auto_rename | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_rename
dev_langs:
- C++
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52147dcf79c73e1f931a3e9b52241308def864c4
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234429"
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