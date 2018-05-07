---
title: Ошибка компилятора C2803 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51cf2a8b38a86fcd97ab693b3853fe25527a0bb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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