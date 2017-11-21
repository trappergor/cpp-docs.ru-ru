---
title: "Ошибка компилятора C3412 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3412
dev_langs: C++
helpviewer_keywords: C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0e050e6d4aef2f9a51e6cc27e7b64b8f6cd8db3d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3412"></a>Ошибка компилятора C3412
«шаблон»: невозможно настроить шаблон в текущей области  
  
 Шаблон не может быть настроен только в глобальной области видимости класса или области видимости пространства имен.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3412.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано возможное решение.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```