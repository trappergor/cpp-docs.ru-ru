---
title: Ошибка компилятора C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: 2df788efd93fb531822d858ea5aee1722487db81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535750"
---
# <a name="compiler-error-c2261"></a>Ошибка компилятора C2261

«Строка»: ссылка на сборку, является недопустимым и не может быть разрешена

Передано недопустимое значение.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется для указания дружественной сборки. Например, если указать в качестве дружественной сборки b.dll a.dll, следует указать (в a.dll): InternalsVisibleTo("b"). Затем среда выполнения позволяет b.dll, доступ к a.dll (за исключением закрытые типы).

Дополнительные сведения об использовании правильного синтаксиса при указании дружественных сборок, см. в разделе [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2261.

```
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```