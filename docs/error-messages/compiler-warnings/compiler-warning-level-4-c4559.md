---
title: Предупреждение компилятора (уровень 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: afb4fb493c7c3e34ca691720a30d74517b0ab5b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220880"
---
# <a name="compiler-warning-level-4-c4559"></a>Предупреждение компилятора (уровень 4) C4559

> "*функция*": переопределение; __declspec прирост функция (*модификатор*)

## <a name="remarks"></a>Примечания

Функция была или определении и добавить второе определение или объявление **__declspec** модификатор (*модификатор*). Это предупреждение носит информационный характер. Чтобы устранить это предупреждение, удалите одно из определений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4559:

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```