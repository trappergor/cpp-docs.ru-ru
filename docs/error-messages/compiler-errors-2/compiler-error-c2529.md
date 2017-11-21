---
title: "Ошибка компилятора C2529 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2529
dev_langs: C++
helpviewer_keywords: C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7c0a693af458818b8c5ac44e160272d8b15fa5f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2529"></a>Ошибка компилятора C2529
«Имя»: ссылка на ссылку недопустима  
  
 Чтобы устранить эту ошибку с помощью синтаксиса указателя, объявления ссылки на указатель.  
  
 Следующий пример приводит к возникновению ошибки C2529:  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```