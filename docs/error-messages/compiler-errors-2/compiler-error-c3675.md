---
title: "Ошибка компилятора C3675 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3675"
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": зарезервировано, поскольку определено "свойство"  
  
 При объявлении простого свойства компилятором автоматически создаются методы доступа get и set, имена которых включаются в область действия программы.  Имена этих методов создаются посредством добавления префиксов get\_ и set\_ к имени свойства.  В связи с этим нельзя объявлять функции, имена которых совпадают с автоматически создаваемыми компилятором именами методов доступа.  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере возникает ошибка C3675.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```