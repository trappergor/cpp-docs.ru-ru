---
title: "Ошибка компилятора C3465 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3465
dev_langs:
- C++
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 07dfd738cdfdd8cca85df6f70139fc0bbf0b7a4e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3465"></a>Ошибка компилятора C3465
для использования типа "тип" необходима ссылка на сборку "сборка"  
  
 Перенаправление типов будет работать для клиентского приложения до перекомпиляции клиента. При перекомпиляции потребуется ссылка для каждой сборки, содержащей определение типа, используемого в клиентском приложении.  
  
 Дополнительные сведения см. в разделе [переадресации типов (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется построение сборки, содержащей новое расположение типа.  
  
```  
// C3465.cpp  
// compile with: /clr /LD  
public ref class R {  
public:  
   ref class N {};  
};  
```  
  
## <a name="example"></a>Пример  
 В следующем примере выполняет построение сборки, которая обычно содержит определение типа, но теперь содержит синтаксис перенаправления для типа.  
  
```  
// C3465_b.cpp  
// compile with: /clr /LD  
#using "C3465.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3465.  
  
```  
// C3465_c.cpp  
// compile with: /clr  
// C3465 expected  
#using "C3465_b.dll"  
// Uncomment the following line to resolve.  
// #using "C3465.dll"  
  
int main() {  
   R^ r = gcnew R();  
}  
```
