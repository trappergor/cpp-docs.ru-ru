---
title: "Предупреждение компилятора C4867 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 352b38744d83b3dc163125ff5ec8d80165f60c9a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4867"></a>Предупреждение компилятора C4867
«функция»: вызов функции отсутствует список аргументов; Используйте «вызов» для создания указателя на член  
  
 Неправильная инициализация указателя на функцию-член.  
  
 Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: расширенным соответствием указателя на член.  Код, скомпилированный в версии до Visual C++ 2005, теперь будет создавать C4867.  
  
 Это предупреждение всегда выдается как ошибка. Используйте прагму [warning](../../preprocessor/warning.md) , чтобы отключить это предупреждение. Дополнительные сведения о C4867 и MFC/ATL см. в разделе [также библиотеках](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4867.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```
