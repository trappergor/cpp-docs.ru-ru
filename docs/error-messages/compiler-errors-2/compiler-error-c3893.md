---
title: "Ошибка компилятора C3893 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3893
dev_langs: C++
helpviewer_keywords: C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fee017305c90d9da69f5432815c0005eb84352c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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