---
title: Ошибка компилятора C2534 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2534
dev_langs:
- C++
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae52374e09852ffb68c5807353155d9928924eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228250"
---
# <a name="compiler-error-c2534"></a>Ошибка компилятора C2534
«Идентификатор»: конструктор не может возвращать значение  
  
 Конструктор не может возвращать значение или иметь тип возвращаемого значения (даже `void` тип возвращаемого значения).  
  
 Чтобы устранить эту ошибку, удалив `return` оператора из определения конструктора.  
  
 Следующий пример приводит к возникновению ошибки C2534:  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```