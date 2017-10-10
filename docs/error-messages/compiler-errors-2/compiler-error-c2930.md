---
title: "Ошибка компилятора C2930 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2930
dev_langs:
- C++
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0c3b539b8a2aa3952a77ae3f81ad56ec29cd77ba
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2930"></a>Ошибка компилятора C2930
"класс": идентификатор типа класса переопределен как перечислитель "идентификатор_перечисления"  
  
 Универсальный класс или класс шаблона нельзя использовать в качестве члена перечисления.  
  
 Эта ошибка может возникнуть при неправильной расстановке скобок.  
  
 В следующем примере возникает ошибка C2930:  
  
```  
// C2930.cpp  
// compile with: /c  
template<class T>   
class x{};  
enum SomeEnum { x };   // C2930  
  
class y{};  
enum SomeEnum { y };  
```  
  
 Ошибка C2930 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2930c.cpp  
// compile with: /clr /c  
generic<class T>   
ref struct GC {};  
enum SomeEnum { GC };   // C2930  
  
ref struct GC2 {};  
enum SomeEnum2 { GC2 };  
```
