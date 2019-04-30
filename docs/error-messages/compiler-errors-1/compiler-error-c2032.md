---
title: Ошибка компилятора C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: 5743aba880f23d7706940936fc4a3a1973a84ca1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400517"
---
# <a name="compiler-error-c2032"></a>Ошибка компилятора C2032

«Идентификатор»: функция не может быть членом структуры или объединения «structorunion»

Структуры или объединения имеет функцию-член, который допустим в C++, но не на языке C. Чтобы устранить эту ошибку, либо компилировать как программы на языке C++, либо удалить функцию-член.

Следующий пример приводит к возникновению ошибки C2032:

```
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

Возможное решение

```
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```