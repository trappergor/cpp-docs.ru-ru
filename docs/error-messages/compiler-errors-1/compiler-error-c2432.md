---
title: Ошибка компилятора C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: e2983d966a6290ce19713c63feb502c8ffc74bf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631254"
---
# <a name="compiler-error-c2432"></a>Ошибка компилятора C2432

Недопустимая ссылка на 16-разрядные данные в «идентификатор»

16-битный регистр используется в качестве индекса или базовым регистром. Компилятор не поддерживает ссылки на 16-разрядные данные. 16-разрядные регистры не может использоваться как индекс или базовых при компиляции для 32-разрядного кода.

Следующий пример приводит к возникновению ошибки C2432:

```
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```