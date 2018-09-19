---
title: Ошибка компилятора C2733 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42749c26f4a8a474f3dac076b80a1bfe71e89d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110449"
---
# <a name="compiler-error-c2733"></a>Ошибка компилятора C2733

вторая С-компоновка перегруженной функции «функция» не допускается

С компоновкой C объявляется несколько перегруженных функций. При использовании компоновкой, может быть внешним только одну форму указанной функции. Поскольку перегруженные функции имеют то же недекорированное имя, они не может использоваться с помощью программы C.

Следующий пример приводит к возникновению ошибки C2733:

```
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```