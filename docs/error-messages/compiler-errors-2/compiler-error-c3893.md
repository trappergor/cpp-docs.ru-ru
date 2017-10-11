---
title: "Ошибка компилятора C3893 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 49097d988175e7571c5825b4d54e1dd496fb2ba7
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3893"></a>Ошибка компилятора C3893
«переменная»: l значения можно использовать элементы данных initonly допускается только в конструкторе экземпляра класса «имя_типа»  
  
 Статические [initonly](../../dotnet/initonly-cpp-cli.md) элементы данных могут иметь только свои адреса в статическом конструкторе.  
  
 Элементы данных initonly (не статического) экземпляр может иметь только свои адреса в конструкторах экземпляров (не статического).  
  
 Следующий пример приводит к возникновению ошибки C3893:  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```
