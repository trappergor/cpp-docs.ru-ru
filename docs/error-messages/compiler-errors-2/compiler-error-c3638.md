---
title: Ошибка компилятора C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 8b1ef7f4cb38653f0ccdfae5684eb2907a735af7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486896"
---
# <a name="compiler-error-c3638"></a>Ошибка компилятора C3638

«operator»: стандартный упаковки-преобразования и распаковки-операторы преобразования не может быть переопределен

Компилятор определяет оператор преобразования для каждого управляемого класса для поддержки неявная упаковка-преобразование. Этот оператор не может быть переопределен.

Дополнительные сведения см. в разделе [неявная упаковка-преобразование](../../windows/boxing-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3638:

```
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```