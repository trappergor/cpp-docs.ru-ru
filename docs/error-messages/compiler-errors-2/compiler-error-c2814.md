---
title: "Ошибка компилятора C2814 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2814
dev_langs: C++
helpviewer_keywords: C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1572d547ee8b6eb8b534e6d99027e63dae39c54d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2814"></a>Ошибка компилятора C2814
member: неуправляемый тип не может быть вложенным в управляемом типе или типе WinRT "type"  
  
## <a name="example"></a>Пример  
 Неуправляемый тип не может быть вложенным в типе CLR или WinRT. В следующем примере показано возникновение ошибки C2814 и приводятся сведения по ее устранению.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
