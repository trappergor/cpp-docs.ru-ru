---
title: Предупреждение компилятора C4986 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4986
dev_langs:
- C++
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5c5342a65e9f900582246bb007d9dd67338dd8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275166"
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