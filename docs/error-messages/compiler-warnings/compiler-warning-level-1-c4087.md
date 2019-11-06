---
title: Предупреждение компилятора (уровень 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: fe2b4fadfb87726e81178a3530299dbb8620aec9
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626841"
---
# <a name="compiler-warning-level-1-c4087"></a>Предупреждение компилятора (уровень 1) C4087

"функция": объявлена со списком параметров void

Объявление функции не имеет формальных параметров, но вызов функции содержит фактические параметры. Лишние параметры передаются в соответствии с соглашением о вызовах функции.

Это предупреждение для компилятора C.

## <a name="example"></a>Пример

```c
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```