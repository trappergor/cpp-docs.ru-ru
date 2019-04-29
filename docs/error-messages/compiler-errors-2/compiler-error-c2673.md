---
title: Ошибка компилятора C2673
ms.date: 11/04/2016
f1_keywords:
- C2673
helpviewer_keywords:
- C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
ms.openlocfilehash: 8a544b6d96089195d7d28f9a62b091b4f1cfc537
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386841"
---
# <a name="compiler-error-c2673"></a>Ошибка компилятора C2673

«функция»: глобальные функции не имеют указателей «this»

Глобальная функция попытался получить доступ к `this`.

Следующий пример приводит к возникновению ошибки C2673:

```
// C2673.cpp
int main() {
   this = 0;   // C2673
}
```