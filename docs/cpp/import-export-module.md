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
description: Используйте импортно-экспортные декларации для доступа и публикации типов и функций, определенных в указанном модуле.
ms.openlocfilehash: a765e9a406660d3c945ef3d70754178b0648458c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374116"
---
# <a name="module-import-export"></a>модуль, импорт, экспорт

**Модуль,** **импорт**, и **экспортные** декларации доступны в C-20 и требуют [/экспериментальный:модульком](../build/reference/experimental-module.md) компилятор переключатель вместе с [/std: c ' latest](../build/reference/std-specify-language-standard-version.md). Для получения дополнительной [информации см.](modules-cpp.md)

## <a name="module"></a>module

Разместите декларацию **модуля** в начале файла реализации модуля, чтобы указать, что содержимое файла относится к указанному модулю.

```cpp
module ModuleA;
```

## <a name="export"></a>экспорт

Используйте декларацию **экспортного модуля** для основного файла интерфейса модуля, который должен иметь расширение **.ixx:**

```cpp
export module ModuleA;
```

В файле интерфейса используйте **экспортный** модификатор на именах, которые должны быть частью общедоступного интерфейса:

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

Неэкспортированные имена не видны коду, импортируемому модулю:

```cpp
//MyProgram.cpp

import module ModuleA;

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

Ключевое слово **экспорта** может не отображаться в файле реализации модуля. Когда **экспорт** применяется к имени пространства имен, все имена в пространстве имен экспортируются.

## <a name="import"></a>импорт

Используйте объявление **импорта,** чтобы сделать имена модуля видимыми в вашей программе. Объявление об импорте должно отображаться после декларации модуля и после любых #include директив, но до каких-либо деклараций в файле.

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

## <a name="remarks"></a>Remarks

Как **импорт,** так и **модуль** рассматриваются как ключевые слова только тогда, когда они отображаются в начале логической линии:

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

**Microsoft Специфический**

В Microsoft C q **импорт** и **модуль** токенов всегда являются идентификаторами и никогда не являются ключевыми словами, когда они используются в качестве аргументов для макроса.

### <a name="example"></a>Пример

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Обзор модулей в C++](modules-cpp.md)
