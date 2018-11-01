---
title: Ошибка компилятора C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: a30efa264a4e7be387c3c2363940bd5ceca1bcc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540950"
---
# <a name="compiler-error-c2687"></a>Ошибка компилятора C2687

«Тип»: объявление исключения не может быть «void» и не может обозначать неполный тип либо указатель или ссылку на неполный тип

Для типа как часть объявления исключения он должен быть определен и не void.

Следующий пример приводит к возникновению ошибки C2687:

```
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Возможное решение

```
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```