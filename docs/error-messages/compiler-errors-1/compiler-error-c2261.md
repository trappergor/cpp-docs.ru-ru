---
title: Ошибка компилятора C2261 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed43dc43fb6ceaf514a8e7452b06eb7bdaf7362
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051650"
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