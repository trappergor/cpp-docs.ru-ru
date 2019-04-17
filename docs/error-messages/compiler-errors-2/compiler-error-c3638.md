---
title: Ошибка компилятора C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 33bb248faf946c39543de4a14a44e2ebbda49880
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775235"
---
# <a name="compiler-error-c3638"></a>Ошибка компилятора C3638

«operator»: стандартный упаковки-преобразования и распаковки-операторы преобразования не может быть переопределен

Компилятор определяет оператор преобразования для каждого управляемого класса для поддержки неявная упаковка-преобразование. Этот оператор не может быть переопределен.

Дополнительные сведения см. в разделе [неявная упаковка-преобразование](../../extensions/boxing-cpp-component-extensions.md).

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