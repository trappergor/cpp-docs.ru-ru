---
title: Предупреждение компилятора (уровень 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 6a20effcebe1a36fa1356fffefa3a23a0056a0f0
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052259"
---
# <a name="compiler-warning-level-1-c4945"></a>Предупреждение компилятора (уровень 1) C4945

"символ": невозможно импортировать символ из "Assembly2": AS "Symbol" уже был импортирован из другой сборки "сборка Assembly1"

Символ был импортирован из упоминаемой сборки, но этот символ уже импортирован из другой упоминаемой сборки. Либо не ссылаются на одну из сборок, либо не изменяют имя символа в одной из сборок.

В следующих примерах создается C4945.

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

И потом

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

И потом

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```