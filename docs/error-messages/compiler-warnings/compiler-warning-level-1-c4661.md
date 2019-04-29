---
title: Предупреждение компилятора (уровень 1) C4661
ms.date: 11/04/2016
f1_keywords:
- C4661
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
ms.openlocfilehash: 7566ba3d1db8e15d2919904d3dc2316e10a7ff59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374707"
---
# <a name="compiler-warning-level-1-c4661"></a>Предупреждение компилятора (уровень 1) C4661

«Идентификатор»: отсутствует подходящее определение для запроса при создании экземпляра шаблона

Член класса шаблона не определен.

## <a name="example"></a>Пример

```
// C4661.cpp
// compile with: /W1 /LD
template<class T> class MyClass {
public:
   void i();   // declaration but not definition
};
template MyClass< int >;  // C4661
```