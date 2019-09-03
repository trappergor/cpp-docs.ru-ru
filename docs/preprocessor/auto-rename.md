---
title: auto_rename, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- auto_rename
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
ms.openlocfilehash: b43773741701997b48c321cb01ebeba3fed1fb7b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70215946"
---
# <a name="auto_rename-import-attribute"></a>auto_rename, атрибут импорта

**C++Зависящ**

Переименовывает зарезервированные слова C++ путем добавления двух знаков подчеркивания (__) к именам переменных, чтобы разрешить потенциальные конфликты имен.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **auto_rename**

## <a name="remarks"></a>Примечания

Этот атрибут используется при импорте библиотеки типов, в которой в качестве имен переменных используется одно или несколько зарезервированных слов C или C++ (ключевых слов или макросов).

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
