---
title: Ошибка компилятора C2650 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37690727b76ec89ae9dffda2699e20e0a43f6938
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101051"
---
# <a name="compiler-error-c2650"></a>Ошибка компилятора C2650

«operator»: не может быть виртуальная функция

Объект `new` или `delete` оператор объявлен `virtual`. Эти операторы являются `static` члена функции и не может быть `virtual`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2650:

```
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```