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
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 63f9c9172daffe11f91c521f514f0e8e53331b22
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4463"></a>Компилятор C4463 предупреждение (уровень 4)  
  
> переполнения; Назначение *значение* к битовому полю может содержать только значения из *low_value* для *high_value*  
  
Назначенные *значение* находится вне диапазона значений, который может содержать битового поля. Типы со знаком битового поля используйте старший бит знака, поэтому если  *n*  — размер битового поля диапазон для знаком битовые поля — -2<sup>n-1</sup> 2<sup>n-1</sup>-1, тогда как битовые поля без знака в диапазоне от 0 до 2<sup>n</sup>-1.  
  
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

