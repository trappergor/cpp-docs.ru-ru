---
title: Предупреждение компилятора (уровень 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 326b73dcf4665c442926e68995bace60300b6ebf
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052104"
---
# <a name="compiler-warning-level-2-c4285"></a>Предупреждение компилятора (уровень 2) C4285

Тип возвращаемого значения для "идентификатор:: operator->" является рекурсивным при применении с помощью нотации инфиксные

Указанная функция **operator-> ()** не может возвращать тип, для которого она определена, или ссылку на тип, для которого она определена.

Следующий пример приводит к возникновению ошибки C4285:

```cpp
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```