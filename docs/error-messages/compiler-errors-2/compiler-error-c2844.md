---
title: "Ошибка компилятора C2844 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 45e0a7eb7a8846d90cc8e0743f5484ba1b58208a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2844"></a>Ошибка компилятора C2844
«член»: не может быть членом интерфейса «интерфейс»  
  
 [Класс интерфейса](../../windows/interface-class-cpp-component-extensions.md) не может содержать элемент данных, если это свойство.  
  
 Ничего, кроме свойства или функции-члена не допускается в интерфейсе. Кроме того конструкторы, деструкторы и операторы не разрешены.  
  
 Следующий пример приводит к возникновению ошибки C2844:  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  

