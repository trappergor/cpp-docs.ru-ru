---
title: "Ошибка компилятора C3612 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3612
dev_langs: C++
helpviewer_keywords: C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dd430c7dbdfae88d80e073fa9e624f123c41f366
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3612"></a>Ошибка компилятора C3612
«Тип»: запечатанный класс не может быть абстрактным  
  
Типы, определенные с помощью `value` являются запечатанными по умолчанию и класс является абстрактным, если он не реализует все методы базового. Запечатанный абстрактный класс не может быть базовым классом и не может создавать его экземпляр.  
  
Дополнительные сведения см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3612:  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```