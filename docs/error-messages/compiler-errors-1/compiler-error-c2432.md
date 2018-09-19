---
title: Ошибка компилятора C2432 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca8c2c62415b6ec3c29c820a23677a87a2695c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055914"
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