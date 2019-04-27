---
title: Ошибка компилятора C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 63739989d737527e3f136bb3aac2269eda6231c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222561"
---
# <a name="compiler-error-c3295"></a>Ошибка компилятора C3295

"#pragma <директива pragma>" может использоваться только в глобальной области или в области пространства имен

Некоторые директивы pragma нельзя использовать в функции.  См. в разделе [директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3295:

```
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```