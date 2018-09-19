---
title: Ошибка компилятора C3755 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 647f62fa75226fd2c80d1bf6285d76e1c2f8c4be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026730"
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