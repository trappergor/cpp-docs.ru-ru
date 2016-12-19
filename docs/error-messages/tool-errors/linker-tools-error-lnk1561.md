---
title: "Ошибка средств компоновщика LNK1561 | Microsoft Docs"
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
  - "LNK1561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1561"
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

следует определить точку входа  
  
 Компоновщик не обнаружил точку входа.  Возможно, предполагалась компоновка библиотеки DLL; в этом случае компоновку следует производить с параметром [\/DLL](../../build/reference/dll-build-a-dll.md).  Возможно, не было задано имя входной точки; в этом случае компоновку следует производить с параметром [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
 В противном случае в коде должна присутствовать функция с именем main, wmain, WinMain, или wMain.  
  
 При использовании программы [LIB](../../build/reference/lib-reference.md) с расчетом на построение библиотеки DLL эта ошибка может возникать из\-за включения файла DEF.  В этом случае файл DEF следует удалить из построения.  
  
 Следующий пример приводит к возникновению ошибки LNK1561:  
  
```  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```