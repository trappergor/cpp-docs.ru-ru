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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: a052194893db90177b88eea8f80435777ae37773
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4867"></a>Предупреждение компилятора C4867
«функция»: вызов функции отсутствует список аргументов; Используйте «вызов» для создания указателя на член  
  
 Неправильная инициализация указателя на функцию-член.  
  
 Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: расширенным соответствием указателя на член.  Код, скомпилированный в версии до Visual C++ 2005, теперь будет создавать C4867.  
  
 Это предупреждение всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) pragma, чтобы отключить это предупреждение. Дополнительные сведения о C4867 и MFC/ATL см. в разделе [также библиотеках](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).  
  
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
