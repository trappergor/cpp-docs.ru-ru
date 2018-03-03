---
title: "Ошибка компилятора C3195 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840aa93a7955c6eda2720da8457624e00fe97fca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3195"></a>Ошибка компилятора C3195
operator: зарезервирован и не может использоваться как элемент ссылочного класса или типа значения. Операторы среды CLR или WinRT должны быть определены с помощью ключевого слова operator  
  
Компилятор обнаружил определение оператора с использованием синтаксиса управляемых расширений для C++. Для операторов, необходимо использовать синтаксис C++.  
  
В следующем примере показано возникновение ошибки C3195 и приводятся сведения по ее устранению.  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```