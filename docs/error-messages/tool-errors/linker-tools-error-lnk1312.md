---
title: "Ошибка средств компоновщика LNK1312 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1312"
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка средств компоновщика LNK1312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недействующий или поврежденный файл; невозможно импортировать сборку  
  
 При построении сборки файл, отличный от модуля или сборки, компилируется с помощью параметра **\/clr**, переданного в параметр компоновщика **\/ASSEMBLYMODULE**.  Если объектный файл передан в **\/ASSEMBLYMODULE**, просто передайте объект напрямую в компоновщик, а не в **\/ASSEMBLYMODULE**.  
  
## Пример  
 В следующем примере показано создание OBJ\-файла.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## Пример  
 В следующем примере показано возникновение ошибки LNK1312.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```