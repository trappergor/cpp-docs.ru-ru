---
title: Предупреждение компилятора (уровень 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: 80794d270b40a8f40d44630da70455c015158423
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541245"
---
# <a name="compiler-warning-level-4-c4100"></a>Предупреждение компилятора (уровень 4) C4100

"идентификатор": формальный параметр без ссылки

В теле функции отсутствует ссылка на формальный параметр. Параметр без ссылки игнорируется.

C4100 также можно выдавать, когда код вызывает деструктор для параметра-примитива, не ссылающегося на другой тип.  Это ограничение для компилятора Майкрософт C++ .

Следующий пример приводит к возникновению ошибки C4100:

```cpp
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```