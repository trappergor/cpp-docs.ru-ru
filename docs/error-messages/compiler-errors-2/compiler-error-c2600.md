---
title: "Ошибка компилятора C2600 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 407598a68df37aa130ce26e4f02e98de975ab527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2600"></a>Ошибка компилятора C2600
'функция' : невозможно определить особую функцию-член, созданную компилятором (сначала требуется объявить ее в классе)  
  
 Перед определением функций-членов, таких как конструкторы или деструкторы, для класса они должны быть объявлены в этом классе. Компилятор может создать конструкторы и деструкторы по умолчанию (особые функции-члены), если они не объявлены в классе. Если же определить одну из этих функций без соответствующего объявления в классе, то компилятор обнаружит конфликт.  
  
 Чтобы устранить эту ошибку нужно в объявлении класса объявить каждую функцию-член, которая определена вне объявления класса.  
  
 Следующий пример приводит к возникновению ошибки C2600:  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```