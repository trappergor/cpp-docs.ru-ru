---
title: "Ошибка компилятора C3611 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3611
dev_langs: C++
helpviewer_keywords: C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfd4d0cb336f540387ad8f135c02c512a5282e26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3611"></a>Ошибка компилятора C3611
«функция»: запечатанная функция не может иметь чистый спецификатор  
  
 Запечатанная функция был объявлен неправильно.  Дополнительные сведения см. в разделе [запечатанный](../../windows/sealed-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3611.  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```