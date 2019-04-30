---
title: Ошибка компилятора C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 68845b446541b8d76ebd2b873a34b7e32ef314e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400192"
---
# <a name="compiler-error-c3769"></a>Ошибка компилятора C3769

«Тип»: вложенный класс не может иметь имя, совпадающее с именем немедленно включающего класса

Вложенный класс не может иметь имя, совпадающее с именем немедленно включающего класса.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3769.

```
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```