---
title: Предупреждение компилятора (уровень 1) C4540 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e3f553bd1f910c7b17e079dc1f03664c78383e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042771"
---
# <a name="compiler-warning-level-1-c4540"></a>Предупреждение компилятора (уровень 1) C4540

приведение dynamic_cast использовано для преобразования к недоступной или неоднозначной базе; Проверка во время выполнения не удастся («тип1» в «тип2»)

Вы использовали `dynamic_cast` преобразования из одного типа в другой. Определен, приведение будут завершаться ошибкой (вернуть **NULL**), так как базовый класс недоступен (`private`, например) или является неоднозначным (более одного раза в иерархии классов, к примеру).

Ниже показан пример этого предупреждения. Класс **B** является производным от класса **объект**. Программа использует `dynamic_cast` для приведения из класса **B** (производный класс) класс **объект**, который всегда завершается ошибкой, так как класс **B** является `private` и, следовательно, Нет доступа. Изменения доступа к **объект** для **открытый** устранить предупреждение.

```
// C4540.cpp
// compile with: /W1

struct A {
   virtual void g() {}
};

struct B : private A {
   virtual void g() {}
};

int main() {
   B b;
   A * ap = dynamic_cast<A*>(&b);   // C4540
}
```