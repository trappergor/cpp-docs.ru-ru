---
title: Предупреждение компилятора (уровень 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 96e1077ce3c9e60823a11aa41719738265ee703b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535984"
---
# <a name="compiler-warning-level-2-c4285"></a>Предупреждение компилятора (уровень 2) C4285

Тип возвращаемого значения для «identifier::operator ->» является рекурсивным, если используется инфиксная запись

Указанный **operator -> ()** функция не может возвращать тип, для которого она определена, или ссылку на тип, для которого она определена.

Следующий пример приводит к возникновению ошибки C4285:

```
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