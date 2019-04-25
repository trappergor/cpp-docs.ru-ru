---
title: Ошибка компилятора C2430
ms.date: 11/04/2016
f1_keywords:
- C2430
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
ms.openlocfilehash: 754758e652539e4f2d9b12e568b8ef5ccf41d8db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165701"
---
# <a name="compiler-error-c2430"></a>Ошибка компилятора C2430

несколько индексных регистров в «идентификатор»

Масштабируется несколько регистров. Компилятор поддерживает масштабированную индексацию, но можно масштабировать только одного регистра.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2430.

```
// C2430.cpp
// processor: x86
int main() {
   _asm mov eax, [ebx*2+ecx*4] // C2430
}
```