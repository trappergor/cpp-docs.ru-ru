---
title: "Ошибка компилятора C3116 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3116
dev_langs:
- C++
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78281083fd98806306ccdcf9fe889f679acd6bcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3116"></a>Ошибка компилятора C3116
«спецификатор»: недопустимый класс хранения для метода интерфейса  
  
 Вы использовали `typedef`, `register`, или `static` как класс хранения для метода интерфейса. Эти классы хранения не допускаются для членов интерфейса.  
  
 Следующий пример приводит к возникновению ошибки C3116:  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```