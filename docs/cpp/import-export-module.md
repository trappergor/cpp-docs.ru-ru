---
title: Модуль, импорт, экспорт
ms.date: 07/15/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Используйте инструкцию import для доступа к типам и функциям, определенным в указанном модуле.
ms.openlocfilehash: fbb9c45ec816c859edb4df38ad67dc7778247e87
ms.sourcegitcommit: 7b039b5f32f6c59be6c6bb1cffafd69c3bfadd35
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68537790"
---
# <a name="module-import-export"></a>Модуль, импорт, экспорт

Ключевые слова **module**, **Import**и **Export** доступны в `/experimental:modules` c++ 20, и для них требуется параметр компилятора вместе с. `/std:c++latest` Дополнительные сведения см. [в разделе Обзор модулей в C++ ](modules-cpp.md).

## <a name="module"></a>module

Используйте оператор **module** в начале файла реализации модуля, чтобы указать, что содержимое файла принадлежит к именованному модулю. 

```cpp
module ModuleA;
```

## <a name="export"></a>экспорт

Используйте инструкцию **Export Module** для основного файла интерфейса модуля, который должен иметь расширение **. икскс**:

```cpp
export module ModuleA;
```

В файле интерфейса используйте модификатор **Export** для имен, которые должны быть частью общего интерфейса:

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

Неэкспортированные имена невидимы для кода, который импортирует модуль:

```cpp
//MyProgram.cpp

import module ModuleA;

void main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

Ключевое слово **Export** не может присутствовать в файле реализации модуля. Если к имени пространства имен применяется модификатор **экспорта** , то экспортируются все имена в пространстве имен.

## <a name="import"></a>импорт

Используйте инструкцию **Import** , чтобы сделать имена модуля видимыми в программе. Оператор import должен находиться после оператора Module и после любой директивы #include, но перед любыми объявлениями в файле.

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="see-also"></a>См. также
[Общие сведения о модулях вC++](modules-cpp.md)
