---
title: Ошибка компилятора C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: ba1dbf08fb56364d2ab5b8c40847ab89484dc005
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328802"
---
# <a name="compiler-error-c3375"></a>Ошибка компилятора C3375

"функция": неоднозначная функция делегата

Создание экземпляра делегата могло быть выполнено в статической функции-члене или как непривязанного делегата для функции экземпляра, поэтому компилятор выдал данную ошибку.

Дополнительные сведения см. в разделе [delegate (расширения компонентов C++)](../../extensions/delegate-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3375:

```
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```