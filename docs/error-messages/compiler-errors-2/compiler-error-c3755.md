---
title: Ошибка компилятора C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 90dc3b7a0e1dbc4e0dc6c42ca722ca1db462fca9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558214"
---
# <a name="compiler-error-c3755"></a>Ошибка компилятора C3755

«делегат»: делегат не могут быть определены

Объект [delegate (расширения компонентов C++)](../../windows/delegate-cpp-component-extensions.md) может быть объявлен, но не определен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3755.

```
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>Пример

C3755 также может возникать при попытке создания шаблона делегата. Следующий пример приводит к возникновению ошибки C3755.

```
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```