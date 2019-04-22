---
title: Практическое руководство. Использование gcnew для создания типов значений и использование неявной упаковки-преобразования
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: c67f8e0b9511f4ed1610e72e4a7df41c949b1d27
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770823"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Практическое руководство. Использование gcnew для создания типов значений и использование неявной упаковки-преобразования

С помощью [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) в значение типа создает это упакованный тип значений, который можно поместить в управляемый, сборщиком мусора куче.

## <a name="example"></a>Пример

```
// vcmcppv2_explicit_boxing4.cpp
// compile with: /clr
public value class V {
public:
   int m_i;
   V(int i) : m_i(i) {}
};

public ref struct TC {
   void do_test(V^ v) {
      if (v != nullptr)
         ;
      else
         ;
   }
};

int main() {
   V^ v = gcnew V(42);
   TC^ tc = gcnew TC;
   tc->do_test(v);
}
```

## <a name="see-also"></a>См. также

[Упаковка-преобразование](../extensions/boxing-cpp-component-extensions.md)
