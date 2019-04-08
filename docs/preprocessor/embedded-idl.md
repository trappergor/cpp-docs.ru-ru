---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: c46924d2757d01a934c21a70f23e6556f6a10fd3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034093"
---
# <a name="embeddedidl"></a>embedded_idl

**Блок, относящийся только к языку C++**

Указывает, что библиотека типов записывается в файл .tlh с сохранением кода, созданного с атрибутами.

## <a name="syntax"></a>Синтаксис

```
embedded_idl[("param")]
```

### <a name="parameters"></a>Параметры

*param*<br/>
Допустимо одно из двух значений:

- **emitidl**: Сведения о типах, импортированные из библиотеки типов будет присутствовать в IDL-ФАЙЛЕ, созданный для помеченного атрибутом проекта.  Это значение по умолчанию, которое будет действовать, если параметр для `embedded_idl` не указан.

- **no_emitidl**: Сведения о типах, импортированные из библиотеки типов будет отсутствовать в IDL-ФАЙЛЕ, созданный для помеченного атрибутом проекта.

## <a name="example"></a>Пример

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

## <a name="remarks"></a>Примечания

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)