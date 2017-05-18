---
title: "C4355 Предупреждение компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 93b6a78365e493cbfea656e608b7bd3d77e600eb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4355"></a>Предупреждение компилятора C4355
'this': используется в основном списке инициализации членов  
  
 **Это** указатель допустим только в нестатических функциях-членах. Он не может использоваться в списке инициализаторов для базового класса.  
  
 Конструкторы базового класса и конструкторы члена класса были вызваны перед **это** конструктор. Фактически Вы передали указатель на сконструированным объект другому конструктору. Если эти другие конструкторы доступ к любым элементам или вызов функций-членов на это, результат будет неопределенным. Не следует использовать **это** указателя до завершения всех построения.  
  
 Это предупреждение отключено по умолчанию. В разделе [компилятора предупреждения, — это отключение по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) подробнее.  
  
 Следующий пример приводит к возникновению ошибки C4355:  
  
```  
// C4355.cpp  
// compile with: /w14355 /c  
#include <tchar.h>  
  
class CDerived;  
class CBase {  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function() = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase {  
public:  
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor  
   virtual void function() {};  
};  
  
CBase::~CBase() {  
   m_pDerived -> function();  
}  
  
int main() {  
   CDerived myDerived;  
}  
```
