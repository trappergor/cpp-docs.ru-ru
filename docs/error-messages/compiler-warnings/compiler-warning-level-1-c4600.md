---
title: Предупреждение компилятора (уровень 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: fcfefd5b858df653551e7f3061a41d168c8ff3f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489613"
---
# <a name="compiler-warning-level-1-c4600"></a>Предупреждение компилятора (уровень 1) C4600

\#Директива pragma «имя_макроса»: ожидается является допустимой непустой строкой

Нельзя указывать пустую строку при передаче или имени макроса с помощью [pop_macro](../../preprocessor/pop-macro.md) или [push_macro](../../preprocessor/push-macro.md).

Следующий пример приводит к возникновению ошибки C4600:

```
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```