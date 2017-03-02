---
title: "Предупреждение (уровень 1) C4945 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4945
dev_langs:
- C++
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 04cd425a7e285fe3610604a76a2e61958051b101
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4945"></a>Предупреждение компилятора (уровень level 1) C4945
«символ»: не удается импортировать символ из «сборки&2;»: «символ» уже был импортирован из другой сборки «сборка1»  
  
 Символ был импортирован из указанной сборки, но этот символ уже был импортирован из другой сборки, на которую указывает ссылка. Не ссылаться на одну из сборок, или имя символа в одной из сборок.  
  
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
