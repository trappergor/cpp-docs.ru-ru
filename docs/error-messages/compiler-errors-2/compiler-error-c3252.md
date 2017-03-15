---
title: "C3252 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3252
dev_langs:
- C++
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 46bef88947138e1fb072c3d97ae005e11a856a94
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3252"></a>Ошибка компилятора C3252
method: нельзя уменьшить доступность виртуального метода в управляемом типе или типе WinRT  
  
 Класс, реализующий виртуальный метод из базового класса или любой метод интерфейса, не может понизить уровень доступа этого метода.  
  
 Обратите внимание, что все методы интерфейса являются открытыми.  
  
 В следующем примере показано возникновение ошибки C3252 и приводятся сведения по ее устранению.  
  
```  
// C3252.cpp  
// compile with: /clr /c  
ref class A {  
public:  
   virtual void f1() {}  
};  
  
ref class B : public A {  
// To fix, uncomment the following line:   
// public:      
   virtual void f1() override sealed {}   // C3252, make this method public  
};  
```
