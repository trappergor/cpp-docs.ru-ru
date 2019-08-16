---
title: Предупреждение компилятора (уровень 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 6e44dafb6675882a1a62fba5144f85120378421d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510054"
---
# <a name="compiler-warning-level-1-c4311"></a>Предупреждение компилятора (уровень 1) C4311

"переменная" : усечение указателя из типа "тип" в "тип"

Данное предупреждение сообщает о проблемах с усечением 64-разрядного указателя. Например, если код компилируется для 64-разрядной архитектуры, значение указателя (64 бита) будет усечено, если он назначен `int` (32 бита). Дополнительные сведения см. в разделе [правила использования указателей](/windows/win32/WinProg64/rules-for-using-pointers).

Дополнительные сведения о распространенных причинах предупреждения C4311 см. в разделе [Общие ошибки компилятора](/windows/win32/WinProg64/common-compiler-errors).

В следующем примере показано возникновение ошибки C4311 при компиляции для 64-разрядной архитектуры и возможные способы ее устранения.

```
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```