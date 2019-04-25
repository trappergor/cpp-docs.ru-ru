---
title: Ошибка компилятора C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 4a0cf849f7b87bd8d61b0ef087cf91d15669d719
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173838"
---
# <a name="compiler-error-c3233"></a>Ошибка компилятора C3233

"тип": параметр универсального типа уже ограничен

Ограничение универсального параметра в нескольких предложениях `where` недопустимо.

Следующий пример приводит к возникновению ошибки C3233:

```
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```