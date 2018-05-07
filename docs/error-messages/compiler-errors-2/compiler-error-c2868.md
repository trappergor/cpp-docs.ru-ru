---
title: Ошибка компилятора C2868 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84465453ca7a1d76a9dd6b199232384c2ef9124b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2868"></a>Ошибка компилятора C2868  
  
> "*идентификатор*": недопустимый синтаксис для объявления использования; требуется полное имя  
  
Объект [объявление using](../../cpp/using-declaration.md) требует *полное имя*, оператор области (`::`) запятыми последовательность имен пространства имен, класса или перечисления, заканчивается именем идентификатора. Оператор разрешения области один может использоваться для вводят имя из глобального пространства имен.  
  
## <a name="example"></a>Пример  
  
Следующий пример приводит к возникновению ошибки C2868 и также показано правильное использование:  
  
```cpp  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```