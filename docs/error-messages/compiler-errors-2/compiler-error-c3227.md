---
title: Ошибка компилятора C3227 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3227
dev_langs:
- C++
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4d156e70a1ac2c0b05e212ace81b8ccc32d8f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3227"></a>Ошибка компилятора C3227
«параметр»: нельзя использовать «ключевое слово» для размещения универсального типа  
  
 Чтобы создать экземпляр типа, требуется соответствующий конструктор. Однако компилятор не может гарантировать доступность соответствующего конструктора.  
  
 Чтобы устранить эту ошибку, можно использовать шаблоны вместо универсальных типов, или можно использовать один из нескольких методов для создания экземпляра типа.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3227.  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```