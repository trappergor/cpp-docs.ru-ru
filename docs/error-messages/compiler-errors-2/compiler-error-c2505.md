---
title: Ошибка компилятора C2505 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2505
dev_langs:
- C++
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6bd22d7a25311b14ed599c6693bfa0c7913b304
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109175"
---
# <a name="compiler-error-c2505"></a>Ошибка компилятора C2505

«символ»: параметр «__declspec(модификатор)» может применяться только в объявлениях или определениях глобальных объектов или статические данные-члены

Объект `__declspec` модификатор, который должен использоваться только в глобальной области видимости был использован в функции.

Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).

Следующий пример приводит к возникновению ошибки C2505:

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```