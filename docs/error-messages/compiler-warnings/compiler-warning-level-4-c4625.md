---
title: Предупреждение компилятора (уровень 4) C4625
ms.date: 11/04/2016
f1_keywords:
- C4625
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
ms.openlocfilehash: d98e295a9a48da16b58202bc172e112b5c0287d9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990708"
---
# <a name="compiler-warning-level-4-c4625"></a>Предупреждение компилятора (уровень 4) C4625

"производный класс": не удалось создать конструктор копии, так как конструктор копии для базового класса недоступен или удален

Конструктор копирования был удален или недоступен для базового класса, поэтому он не был создан для производного класса. Любая попытка создать объект этого типа приведет к ошибке компилятора.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C4625 и приводятся сведения по ее устранению.

```cpp
// C4625.cpp
// compile with: /W4 /c
#pragma warning(default : 4625)

struct A {
   A() {}

private:
   A(const A&) {}
};

struct C : private virtual A {};
struct B :  C {};   // C4625 no copy constructor

struct D : A {};
struct E :  D {};   // OK
```
