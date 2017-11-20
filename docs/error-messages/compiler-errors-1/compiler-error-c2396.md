---
title: "Ошибка компилятора C2396 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2396
dev_langs: C++
helpviewer_keywords: C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20eca11d402265bbc81d61a8079ae9975cceef67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2396"></a>Ошибка компилятора C2396
":: operator'type '': среды CLR или WinRT допустимый functionnot определенного пользователем преобразования. Необходимо преобразовать из или в: «T^», «T^%», «T^&», где T = your_type  
  
 Функция преобразования в управляемом типе или типе среды выполнения Windows не содержала по крайней мере один параметр, тип которого совпадает с типом, содержащим эту функцию преобразования.  
  
 В следующем примере показано возникновение ошибки C2396 и приводятся сведения по ее устранению.  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```