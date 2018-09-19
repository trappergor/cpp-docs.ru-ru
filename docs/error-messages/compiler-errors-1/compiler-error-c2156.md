---
title: Ошибка компилятора C2156 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2156
dev_langs:
- C++
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37e0810fa31e66b62553825892b53374b22e4263
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038645"
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