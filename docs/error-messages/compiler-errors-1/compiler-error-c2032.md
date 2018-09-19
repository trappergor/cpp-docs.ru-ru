---
title: Ошибка компилятора C2032 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab02ca695ec94f25054e3490232b782a46a53a4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064013"
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