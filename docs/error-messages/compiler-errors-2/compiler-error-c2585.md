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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25df5237d2536f6f74226121cbeceba61a454390
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2585"></a>Ошибка компилятора C2585
явное преобразование в «тип» является неоднозначным  
  
 Преобразование типов может иметь несколько результатов.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Преобразование из типа класса или структуры на основе множественного наследования. Если тип наследует более одного раза для одного базового класса, функция или оператор преобразования должны использовать разрешение области (`::`) чтобы указать, какие из этих классов для использования при преобразовании.  
  
2.  Оператор преобразования и конструктор определено сделать то же самое преобразование.