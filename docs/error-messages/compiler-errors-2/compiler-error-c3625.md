---
title: "Ошибка компилятора C3625 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3625
dev_langs: C++
helpviewer_keywords: C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c49600c823965dc92e0decab3048f076169d43fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3625"></a>Ошибка компилятора C3625
native_type: неуправляемый тип не может быть производным от типа WinRT type  
  
Неуправляемый класс не может наследовать от управляемого класса или класса WinRT. Дополнительные сведения см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3625:  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
