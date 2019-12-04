---
title: Ошибка компилятора C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: f23c2a38f8e4d6781af73fb70a25cf4737e2c4e8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758779"
---
# <a name="compiler-error-c2261"></a>Ошибка компилятора C2261

"строка": ссылка на сборку недопустима и не может быть разрешена

Недопустимое значение.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется для указания дружественной сборки. Например, если DLL-файл хочет указать b. dll как дружественную сборку, следует указать (в DLL-библиотеке): InternalsVisibleTo ("b"). Затем среда выполнения предоставляет библиотеке b. dll доступ ко всем файлам в библиотеке DLL (за исключением закрытых типов).

Дополнительные сведения о правильном синтаксисе при указании дружественных сборок см. в разделе [дружественные сборкиC++()](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2261.

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```
