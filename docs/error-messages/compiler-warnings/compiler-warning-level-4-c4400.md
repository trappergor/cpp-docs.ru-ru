---
title: Предупреждение компилятора (уровень 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: 61a6d3090355c9bda8aa11c041b302e4ec77ec8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391547"
---
# <a name="compiler-warning-level-4-c4400"></a>Предупреждение компилятора (уровень 4) C4400

«Тип»: квалификаторы const или volatile для этого типа не поддерживаются.

[Const](../../cpp/const-cpp.md)и [volatile](../../cpp/volatile-cpp.md)квалификаторы не будет работать с переменными типов среды выполнения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4400.

```
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```