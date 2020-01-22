---
title: модуль, импорт, экспорт
ms.date: 12/12/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Используйте объявления импорта и экспорта для доступа к типам и функциям, определенным в указанном модуле, и для публикации типов и функций.
ms.openlocfilehash: 7406bf75595bef20775ee1b67c27bd62bff1a932
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518287"
---
# <a name="module-import-export"></a>модуль, импорт, экспорт

Объявления **модуля**, **импорта**и **экспорта** доступны в c++ 20, и для них требуется параметр компилятора [/експериментал: module](../build/reference/experimental-module.md) вместе с [/std: C + + Latest](../build/reference/std-specify-language-standard-version.md). Дополнительные сведения см. [в разделе Обзор модулей в C++ ](modules-cpp.md).

## <a name="module"></a>module

Поместите объявление **модуля** в начало файла реализации модуля, чтобы указать, что содержимое файла принадлежит к именованному модулю.

```cpp
module ModuleA;
```

## <a name="export"></a>export

Используйте объявление **модуля экспорта** для основного файла интерфейса модуля, который должен иметь расширение **. икскс**:

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

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

Ключевое слово **Export** не может присутствовать в файле реализации модуля. При применении **экспорта** к имени пространства имен экспортируются все имена в пространстве имен.

## <a name="import"></a>импорт

Используйте объявление **импорта** , чтобы сделать имена модуля видимыми в программе. Объявление импорта должно располагаться после объявления модуля и после любой директивы #include, но перед любыми объявлениями в файле.

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

## <a name="remarks"></a>Заметки

**Импорт** и **модуль** рассматриваются как ключевые слова, только если они появляются в начале логической строки:

```cpp

// OK:
module ;
module module-name
import :
import <
import "
import module-name
export module ;
export module module-name
export import :
export import <
export import "
export import module-name

// Error:
int i; module ;
```

**Блок, относящийся только к системам Майкрософт**

В корпорации C++Майкрософт **Импорт** и **модуль** маркеров всегда являются идентификаторами и не являются ключевыми словами, когда они используются в качестве аргументов макроса.

### <a name="example"></a>Пример

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Общие сведения о модулях вC++](modules-cpp.md)
