---
title: "Предупреждение (уровень 4) C4463 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4463
dev_langs:
- C++
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71b438de515a4fd01e7714de685ee0a89adb609e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4463"></a>Компилятор C4463 предупреждение (уровень 4)  
  
> переполнения; Назначение *значение* к битовому полю может содержать только значения из *low_value* для *high_value*  
  
Назначенные *значение* находится вне диапазона значений, который может содержать битового поля. Типы со знаком битового поля используйте старший бит знака, поэтому если  *n*  — размер битового поля диапазон для знаком битовые поля — -2<sup>n-1</sup> 2<sup>n-1</sup>-1, во время битовые поля без знака быть в диапазоне от 0 до 2<sup>n</sup>-1.  
  
## <a name="example"></a>Пример  
  
Этот пример создает C4463, так как она попытается назначить значение 3 к битовому полю типа `int` с размером 2, который имеет в диапазоне от -2 до 1.  
  
Чтобы устранить эту проблему, можно изменить присвоенное значение на что-нибудь в диапазон допустимых значений. Если битовое поле предназначен для хранения значений без знака в диапазоне от 0 до 3, можно изменить тип объявления для `unsigned`. Если поле предназначен для хранения значений в диапазоне -4-3, 3 можно изменить размер битового поля.  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  
