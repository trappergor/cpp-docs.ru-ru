---
title: "Ошибка компилятора C2842 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47130ec2bf73889130d64f3ca8411bbc38dabf93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2842"></a>Ошибка компилятора C2842
class: управляемый тип или тип WinRT не может определять свой собственный operator new или operator delete  
  
 Можно определить собственные ** оператор new или **оператор delete** для управления выделением памяти в неуправляемой куче. Однако эти операторы не могут быть определены в ссылочных классах , так как только они выделяются в управляемой куче.  

  
 Дополнительные сведения см. в разделе [определяемые пользователем операторы (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2842:  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
