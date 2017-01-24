---
title: "Ошибка компилятора C3813 | Microsoft Docs"
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
  - "C3813"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3813"
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

объявление свойства должно находиться только в пределах определения управляемого типа или типа WinRT  
  
 Значение [свойства](../../misc/property.md) можно объявлять только в пределах управляемого типа или типа среды выполнения Windows.  Собственные типы не поддерживают ключевое слово `property`.  
  
 В следующем примере показано возникновение ошибки C3813 и приводятся сведения по ее устранению.  
  
```  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```