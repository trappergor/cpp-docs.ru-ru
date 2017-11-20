---
title: "Ошибка компилятора C2428 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2428
dev_langs: C++
helpviewer_keywords: C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: acc73e232e6e513df394875ec93cfa34911e2760
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2428"></a>Ошибка компилятора C2428
«Операция»: не разрешается с операндом типа «bool»  
  
 Оператор декремента нельзя применить к объектам типа `bool`.  
  
 Следующий пример приводит к возникновению ошибки C2428:  
  
```  
// C2428.cpp  
void g(bool fFlag) {  
   --fFlag;   // C2428  
   fFlag--;   // C2428  
}  
```