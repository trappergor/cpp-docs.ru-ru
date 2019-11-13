---
title: Предупреждение компилятора (уровень 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8402c6a2d0fcbb4704b833ac7ae2b070c7af3a48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051589"
---
# <a name="compiler-warning-level-3-c4390"></a>Предупреждение компилятора (уровень 3) C4390

";": найден пустой контролируемый оператор; является ли это намерением?

Точка с запятой обнаружена после оператора управления, который не содержит инструкций.

При получении C4390 из-за макроса следует использовать прагма-директиву [warning](../../preprocessor/warning.md) , чтобы отключить C4390 в модуле, содержащем макрос.

Следующий пример приводит к возникновению ошибки C4390:

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```