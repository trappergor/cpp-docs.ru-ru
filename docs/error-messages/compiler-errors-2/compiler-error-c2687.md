---
title: Ошибка компилятора C2687 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2687
dev_langs:
- C++
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b54c3be7a3706dd5471b21c2a1779e9990eae678
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233022"
---
# <a name="compiler-error-c2687"></a>Ошибка компилятора C2687
«Тип»: объявление исключения не может быть «void» и не может обозначать неполный тип, указатель или ссылку на неполный тип  
  
 Для типа частью объявления исключения он должен быть определен и не пустой.  
  
 Следующий пример приводит к возникновению ошибки C2687:  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 Возможное решение  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```