---
title: Ошибка компилятора C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 4e26742de6c294018f81c6f49c1719fdb11d5149
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328540"
---
# <a name="compiler-error-c3704"></a>Ошибка компилятора C3704

«функция»: метод vararg не может порождать события

Вы попытались использовать [__event](../../cpp/event.md) в методе с переменным количеством аргументов. Чтобы устранить эту ошибку, замените `fireEvent(int i, ...)` вызов с `fireEvent(int i)` вызвать, как показано в следующем образце кода.

Следующий пример приводит к возникновению ошибки C3704:

```
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```