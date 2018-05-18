---
title: Предупреждение (уровень 1) C4945 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4945
dev_langs:
- C++
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8218c0ce387f70cb13a4074a3b3d008a72b1fe3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4945"></a>Предупреждение компилятора (уровень level 1) C4945
«символ»: не удается импортировать символ из «сборки 2»: «символ» уже был импортирован из другой сборки «сборка1»  
  
 Символ был импортирован из указанной сборки, но этот символ уже был импортирован из другой сборки, на которую указывает ссылка. Не ссылаются на одну из сборок, или имя символа, изменения в одной из сборок.  
  
 Приведенные ниже примеры создания C4945.  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 И потом  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 И потом  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```