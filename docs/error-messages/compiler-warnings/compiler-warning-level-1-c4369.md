---
title: Предупреждение компилятора (уровень 1) C4369 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4369
dev_langs:
- C++
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c8b292717168f7f6ead676528a5b7769b7c8ec4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024155"
---
# <a name="compiler-warning-level-1-c4369"></a>Предупреждение компилятора (уровень 1) C4369

«Перечислитель»: значение перечислителя «значение» нельзя представить в виде «тип», значение — «новое_значение»

Перечислитель полученное значение больше, чем максимальное значение для указанного базового типа.  Это привело к переполнению и компилятор изменил значение перечислителя минимальное возможное значение для типа.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4369.

```
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```