---
title: Ошибка компилятора C3731 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3731
dev_langs:
- C++
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 526cd57bd18d379f7c85bbe98bc7fb2dc37b9c41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099935"
---
# <a name="compiler-error-c3731"></a>Ошибка компилятора C3731

несовместимые событие «функция1» и обработчик «функция2»; Источник события и обработчик событий должен иметь тот же тип

Источник и приемник событий должен иметь тот же тип (например `native` и `com` типов). Чтобы устранить эту ошибку, убедитесь в типы источника события и совпадают обработчика событий.

Следующий пример приводит к возникновению ошибки C3731:

```
// C3731.cpp
// compile with: /clr
#using <mscorlib.dll>
[event_source(native)]
struct A {
   __event void MyEvent();
};

[event_receiver(managed)]
// try the following line instead
// [event_receiver(native)]
struct B {
   void func();
   B(A a) {
      __hook(&A::MyEvent, &a, &B::func);   // C3731
   }
};

int main() {
}
```