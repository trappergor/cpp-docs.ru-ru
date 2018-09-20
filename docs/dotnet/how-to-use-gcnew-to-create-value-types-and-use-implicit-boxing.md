---
title: 'Практическое: использование gcnew для создания типов значений и использование неявной упаковки-преобразования | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b4d4a1a8a4531aa3de669acf48c4e37d556097a8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397849"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Практическое руководство. Использование gcnew для создания типов значений, а также использование неявной упаковки-преобразования

С помощью [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) в значение типа создает это упакованный тип значений, который можно поместить в управляемый, сборщиком мусора куче.

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

[Упаковка-преобразование](../windows/boxing-cpp-component-extensions.md)