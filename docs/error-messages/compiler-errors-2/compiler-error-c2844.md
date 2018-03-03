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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3353a6dbacaca2779bb4feffe55958baf0c944e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
