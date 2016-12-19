---
title: "Ошибка компилятора C3200 | Microsoft Docs"
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
  - "C3200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3200"
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"шаблон": недопустимый аргумент шаблона для параметра шаблона "параметр", ожидался шаблон класса  
  
 Передан недопустимый аргумент шаблону класса.  Шаблон класса ожидает шаблон в качестве параметра.  В следующем примере вызов `Y<int, int> aY` создает ошибку C3200.  Первый параметр должен быть шаблоном, таким как `Y<X, int> aY`.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```