---
title: "Ошибка компилятора C2628 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2628
dev_langs: C++
helpviewer_keywords: C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60fd4e45b19423e32b7a5973b8bdfad34b75bcc6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2628"></a>Ошибка компилятора C2628
«тип1» и «тип2» не допускается (возможно, вы забыли «;»?)  
  
 Возможно, отсутствует точка с запятой.  
  
 Следующий пример приводит к возникновению ошибки C2628:  
  
```  
// C2628.cpp  
class CMyClass {}  
int main(){}   // C2628 error  
```  
  
 Возможное решение:  
  
```  
// C2628b.cpp  
class CMyClass {};  
int main(){}  
```