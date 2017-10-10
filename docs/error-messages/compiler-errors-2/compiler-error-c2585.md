---
title: "Ошибка компилятора C2585 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cb0720c7fa9cde9a735c4353bb6bf1d8714ff0fd
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2585"></a>Ошибка компилятора C2585
явное преобразование в «тип» является неоднозначным  
  
 Преобразование типов может иметь несколько результатов.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Преобразование из типа класса или структуры на основе множественного наследования. Если тип наследует более одного раза для одного базового класса, функция или оператор преобразования должны использовать разрешение области (`::`) чтобы указать, какие из этих классов для использования при преобразовании.  
  
2.  Оператор преобразования и конструктор определено сделать то же самое преобразование.
