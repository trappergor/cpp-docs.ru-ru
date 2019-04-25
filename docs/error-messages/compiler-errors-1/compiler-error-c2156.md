---
title: Ошибка компилятора C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: e2637a54249c37f3872d87959f2cf6d7bf73481e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174891"
---
# <a name="compiler-error-c2156"></a>Ошибка компилятора C2156

директива pragma должна находиться вне функции

Директива pragma, которая должна быть определена на глобальном уровне (вне тела функции), находится внутри функции.

Следующий пример приводит к возникновению ошибки C2156:

```
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```