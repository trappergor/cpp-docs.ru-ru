---
title: "Предупреждение компилятора C4986 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4986
dev_langs:
- C++
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 67e4ad3f5170b4f7dc0e938e7b7830dacbde0e26
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4986"></a>Предупреждение компилятора C4986
«функция»: спецификация исключения не соответствует предыдущему объявлению  
  
 Это предупреждение может возникать, когда спецификацией исключений в одном объявлении, а не другой.  
  
 По умолчанию C4986 — off. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4986.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1()  
{  
    // ...  
}    
```  
  
## <a name="example"></a>Пример  
 Следующий пример позволяет устранить это предупреждение.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1() throw (X*)  
{  
    // ...  
}    
```
