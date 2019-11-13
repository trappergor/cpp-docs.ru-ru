---
title: Предупреждение компилятора (уровень 1) C4739
ms.date: 11/04/2016
f1_keywords:
- C4739
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
ms.openlocfilehash: df8f3bcf6cfcc9feb2a400526285ccd9cb0396e4
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052409"
---
# <a name="compiler-warning-level-1-c4739"></a>Предупреждение компилятора (уровень 1) C4739

ссылка на переменную var выходит за пределы ее области хранения

Переменной было назначено значение, но это значение больше, чем размер переменной. Запись в память будет выполнена за пределами расположения этой переменной в памяти, и возможна потеря данных.

Чтобы устранить это предупреждение, просто назначьте значение той переменной, размер которой может вместить это значение.

В следующем примере возникает ошибка C4739:

```cpp
// C4739.cpp
// compile with: /RTCs /Zi /W1 /c
char *pc;
int main() {
   char c;
   *(int *)&c = 1;   // C4739

   // OK
   *(char *)&c = 1;
}
```