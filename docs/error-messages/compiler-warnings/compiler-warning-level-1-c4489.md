---
title: Предупреждение компилятора (уровень 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: dd150621ad3474444861982c095ae8a6addb52fa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768241"
---
# <a name="compiler-warning-level-1-c4489"></a>Предупреждение компилятора (уровень 1) C4489

«спецификатор»: не допускается в методе интерфейса «метод»; переопределить спецификаторы допустимы только в методы класса ref класса и значение

Ключевое слово спецификатора неправильно был использован для метода интерфейса.

Дополнительные сведения см. в разделе [спецификаторы переопределения](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4489.

```
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```