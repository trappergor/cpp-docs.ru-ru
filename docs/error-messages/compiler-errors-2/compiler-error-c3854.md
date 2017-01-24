---
title: "Ошибка компилятора C3854 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3854"
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

выражение слева от знака "\=" сводится к функции.Присваивание значения функции не допускается \(функция не может стоять слева от знака присваивания\)  
  
 Ссылки нельзя инициализировать повторно.  Разыменовывание ссылки на функцию дает функцию, которая может стоять справа от оператора присваивания, но которой нельзя присваивать значение.  Поэтому присваивание через ссылку на функцию не допускается.  
  
 Следующий пример приводит к возникновению ошибки C3854:  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```