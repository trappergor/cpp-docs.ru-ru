---
title: Предупреждение компилятора (уровень 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: 0a14b99a7c4c222bbb8020a27c630a42b1cf0329
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186599"
---
# <a name="compiler-warning-level-1-c4490"></a>Предупреждение компилятора (уровень 1) C4490

"override": неправильное использование спецификатора переопределения; "функция" не соответствует базовому методу ссылочного класса

Спецификатор переопределения был использован неправильно. Например, вы не переопределяете функцию интерфейса, а реализуете ее.

Дополнительные сведения см. в разделе [Описатели переопределения](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4490.

```cpp
// C4490.cpp
// compile with: /clr /c /W1

interface struct IFace {
   void Test();
};

ref struct Class1 : public IFace {
   virtual void Test() override {}   // C4490
   // try the following line instead
   // virtual void Test() {}
};
```
