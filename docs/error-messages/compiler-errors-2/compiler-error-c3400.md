---
title: "Ошибка компилятора C3400 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3400
dev_langs: C++
helpviewer_keywords: C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77c68c81aef564e6dc15ec782d631ca90feb24f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3400"></a>Ошибка компилятора C3400
циклическая зависимость ограничения, включающая "ограничение_1" и "ограничение_2"  
  
 Компилятор обнаружил циклическую зависимость ограничений.  
  
 Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3400:  
  
```  
// C3400.cpp  
// compile with: /clr /c  
generic<class T, class U>  
where T : U  
where U : T   // C3400  
public ref struct R {};  
```