---
title: "Ошибка компилятора C3675 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3675
dev_langs: C++
helpviewer_keywords: C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d45236fc32fd0d10e9617b6946683d8ebd73ef0e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3675"></a>Ошибка компилятора C3675
«функция»: зарезервировано, поскольку определено «свойство»  
  
 При объявлении простого свойства компилятор создает методы get и методы доступа set и тех, имена которых включаются в область действия программы.  Имена созданных компилятором формируются путем добавления перед get_ и set_ к имени свойства.  Таким образом нельзя объявлять функции с тем же именем, как созданные компилятором методы доступа.  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3675.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```