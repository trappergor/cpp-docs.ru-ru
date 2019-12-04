---
title: Ошибка компилятора C2262
ms.date: 11/04/2016
f1_keywords:
- C2262
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
ms.openlocfilehash: e8723c03d37c04a5b99dc4b30cd2604718369c49
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758766"
---
# <a name="compiler-error-c2262"></a>Ошибка компилятора C2262

"спецификаторы_атрибутов": в объявлениях InternalsVisibleTo невозможно указывать версию, культуру или архитектуру процессора

Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> указан неправильно.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2262:

```cpp
// C2262.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262
[assembly: InternalsVisibleTo("assembly_name ")];   // OK
```
