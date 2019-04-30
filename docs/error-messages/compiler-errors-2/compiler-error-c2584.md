---
title: Ошибка компилятора C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: b61ad65555b5d5232468206f6170223c5f160a34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360480"
---
# <a name="compiler-error-c2584"></a>Ошибка компилятора C2584

«Класс»: прямой базовый «база2» недоступен; уже является базовым «База1»

`Class` уже является производным непосредственно от `Base1`. `Base2` также является производным от `Base1`. `Class` не может наследовать от `Base2` так, как это будет означать наследование из `Base1` опять же, который не является допустимым поскольку `Base1` уже является прямым базовым классом.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2584.

```
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```