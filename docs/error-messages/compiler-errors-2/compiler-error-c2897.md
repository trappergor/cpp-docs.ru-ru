---
title: Ошибка компилятора C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: 22e63ce92a6d526f08e68bedb35de104be339dc3
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743377"
---
# <a name="compiler-error-c2897"></a>Ошибка компилятора C2897

деструктор/финализатор не может быть шаблоном функции

Деструкторы или методы завершения не могут быть перегружены, поэтому объявление деструктора как шаблона (определяющего набор деструкторов) не допускается.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2897.

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

Следующий пример приводит к возникновению ошибки C2897.

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```
