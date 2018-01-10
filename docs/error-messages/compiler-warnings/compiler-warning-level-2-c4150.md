---
title: "Предупреждение (уровень 2) C4150 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4150
dev_langs: C++
helpviewer_keywords: C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09267a909ea6e4b0bedd43e6f31a31e778ffb904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4150"></a>Предупреждение (уровень 2) C4150 компилятора
Удаление указателя на неполный тип «тип»; деструктор не вызван  
  
 **Удалить** оператор был вызван для удаления типа, который был объявлен, но не определен, чтобы компилятору не удается найти деструктор.  
  
 Следующий пример приводит к возникновению ошибки C4150:  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```