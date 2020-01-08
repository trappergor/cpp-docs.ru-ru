---
title: Ошибка компилятора C2053
ms.date: 11/04/2016
f1_keywords:
- C2053
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
ms.openlocfilehash: a74e8104ec55e465875846b48186b9abdcb0f2f0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302072"
---
# <a name="compiler-error-c2053"></a>Ошибка компилятора C2053

"идентификатор": несоответствие расширенной строки

Расширенная строка присваивается несовместимому типу.

Следующий пример приводит к возникновению ошибки C2053:

```c
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```
