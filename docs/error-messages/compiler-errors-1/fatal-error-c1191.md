---
title: "Неустранимая ошибка C1191 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1191
dev_langs: C++
helpviewer_keywords: C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 95795ddfcc27a7cd150dec565f0e52a4f7eca00e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1191"></a>Неустранимая ошибка C1191
«dll» могут быть импортированы только в глобальной области видимости  
  
 Инструкция для импорта библиотеки mscorlib.dll в программу, с использованием параметра/CLR не может находиться в пространстве имен или функции, но должны находиться в глобальной области.  
  
 Следующий пример приводит к возникновению ошибки C1191:  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 Возможное решение:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```