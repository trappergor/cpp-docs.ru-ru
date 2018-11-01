---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 202d5b23a5e2e8e673e3c220b9618cfe6cd4f0d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525610"
---
# <a name="embeddedidl"></a>embedded_idl

**Конкретных C++**

Указывает, что библиотека типов записывается в файл .tlh с сохранением кода, созданного с атрибутами.

## <a name="syntax"></a>Синтаксис

```
embedded_idl[("param")]
```

### <a name="parameters"></a>Параметры

*param*<br/>
Допустимо одно из двух значений:

- **emitidl**: сведения о типах, импортированные из библиотеки типов, которые будут представлены в IDL-ФАЙЛЕ, созданный для помеченного атрибутом проекта.  Это значение по умолчанию, которое будет действовать, если параметр для `embedded_idl` не указан.

- **no_emitidl**: сведения о типах, импортированные из библиотеки типов не присутствовать в IDL-ФАЙЛЕ, созданный для помеченного атрибутом проекта.

## <a name="example"></a>Пример

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

## <a name="remarks"></a>Примечания

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)