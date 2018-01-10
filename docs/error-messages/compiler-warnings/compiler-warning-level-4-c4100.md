---
title: "Предупреждение (уровень 4) C4100 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4100
dev_langs: C++
helpviewer_keywords: C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72236ee0c100388906689121a0936daf23c58e89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4100"></a>Предупреждение компилятора (уровень 4) C4100
«Идентификатор»: неиспользованный формальный параметр  
  
 Формальный параметр не используется в теле функции. Неиспользуемые параметр учитывается.  
  
 C4100 также могут быть выданы, когда код вызывает деструктор, в противном случае неиспользуемых параметр типа-примитива.  Это является ограничением компилятора Visual C++.  
  
 Следующий пример приводит к возникновению ошибки C4100:  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```