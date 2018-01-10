---
title: "Ошибка компилятора C3803 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3803
dev_langs: C++
helpviewer_keywords: C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1729991d1e8649e79a924fc61203bac57194696
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3803"></a>Ошибка компилятора C3803
«свойство»: свойство имеет тип, несовместимый с помощью одного из его методов доступа «метод_доступа»  
  
 Тип свойства, определенные с [свойство](../../cpp/property-cpp.md) не соответствует возвращаемому типу одной из функций его методов доступа.  
  
 Следующий пример приводит к возникновению ошибки C3803:  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```