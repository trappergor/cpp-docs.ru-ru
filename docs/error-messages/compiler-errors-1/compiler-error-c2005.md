---
title: Ошибка компилятора C2005 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2005
dev_langs:
- C++
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6dfba3b960a046bf40751c135c3b99fbe843545
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100685"
---
# <a name="compiler-error-c2005"></a>Ошибка компилятора C2005

\#строки требуется номер строки, найден «токен»

`#line` Должен располагаться после директивы с номером строки.

Следующий пример приводит к возникновению ошибки C2005:

```
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

Возможное решение

```
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```