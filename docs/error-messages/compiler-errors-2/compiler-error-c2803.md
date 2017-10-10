---
title: "Ошибка компилятора C2803 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: efa9efa2dc204d302f69d873c0199d4431efccb1
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2803"></a>Ошибка компилятора C2803
«оператор» должен иметь по крайней мере один формальный параметр типа класса  
  
 Перегруженный оператор не имеет параметра типа класса.  
  
 Нужно передать хотя бы один параметр по ссылке (без использования указателей, но ссылки на) или по значению, чтобы иметь возможность писать «< b» (тип класса A и b).  
  
 Если оба параметра являются указателями, они будут простое сравнение адресов указателей и не будет использовать определенное пользователем преобразование.  
  
 Следующий пример приводит к возникновению ошибки C2803:  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```
