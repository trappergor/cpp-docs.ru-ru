---
title: атрибут импорта embedded_idl
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 01948b171b20ad0a3bf3e7a41047f1fe3df185b0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216325"
---
# <a name="embedded_idl-import-attribute"></a>атрибут импорта embedded_idl

**C++Зависящ**

Указывает, записывается ли библиотека типов в `.tlh` файл с сохраненным кодом, сформированным атрибутом.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **embedded_idl** [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>Параметры

**emitidl**\
Сведения о типе, импортированные из *библиотеки типов* , находятся в IDL, созданном для проекта с атрибутами. Это поведение является значением по умолчанию и действует, если параметр не указан в `embedded_idl`.

**"no_emitidl"** \
Сведения о типе, импортированные из *библиотеки типов* , ОТСУТСТВУЮТ в IDL, созданном для проекта с атрибутами.

## <a name="example"></a>Пример

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
