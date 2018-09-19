---
title: Ошибка компилятора C2464 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff74085364d6638772ab2376aace93fea741056b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103149"
---
# <a name="compiler-error-c2464"></a>Ошибка компилятора C2464

«Идентификатор»: нельзя использовать «new» для выделения памяти для ссылки

Идентификатор ссылки был выделен с помощью `new` оператор. Ссылки не являются объектами памяти, поэтому `new` не может вернуть указатель на них. Используйте стандартные объявление переменной синтаксис для объявления ссылки.

Следующий пример приводит к возникновению ошибки C2464:

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```