---
title: Ошибка компилятора C3365
ms.date: 11/04/2016
f1_keywords:
- C3365
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
ms.openlocfilehash: 355c4530fffa89470ac495aff8bc2822278e2da3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201199"
---
# <a name="compiler-error-c3365"></a>Ошибка компилятора C3365

оператор "оператор": отличающиеся операнды типов "тип1" и "тип2"

Попытка компоновки делегатов различного типа.  Дополнительные сведения о делегатах см. [в разделеC++инструкции. Определение и использование делегатов (/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3365:

```cpp
// C3365.cpp
// compile with: /clr
delegate void D1();
delegate void D2(int);

ref class R {
public:
   void f(){}
   void g(int){}
};

int main() {
   D1^ d1 = gcnew D1(gcnew R, &R::f);
   D2^ d2 = gcnew D2(gcnew R, &R::g);
   D1^ d3 = gcnew D1(gcnew R, &R::f);

   d1 += d2;   // C3365
   d1 += d3;   // OK
   d1();
}
```
