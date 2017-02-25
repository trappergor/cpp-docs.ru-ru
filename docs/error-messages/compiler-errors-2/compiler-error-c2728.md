---
title: "Ошибка компилятора C2728 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2728"
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Ошибка компилятора C2728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type: собственный массив не может содержать этот тип  
  
 Синтаксис для создания массива использовался для создания массива или управляемых объектов или объектов WinRT.  Невозможно создать массив управляемых объектов или объектов WinRT, используя синтаксис управляемого массива.  
  
 Подробнее: [Класс array](../../windows/arrays-cpp-component-extensions.md).  
  
 В следующем примере показано возникновение ошибки C2728 и приводятся сведения по ее устранению.  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
  
 Объект [\_\_nogc](../../misc/nogc.md) массива не может быть типа [\_\_gc](../Topic/__gc.md).  
  
 В следующем примере показано возникновение ошибки C2728 и приводятся сведения по ее устранению.  
  
```  
// C2728_b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
int main() {  
   int __gc* arr __nogc[5];   // C2728  
  
   // try the following line instead  
   int arr2 __gc[];  
}  
```