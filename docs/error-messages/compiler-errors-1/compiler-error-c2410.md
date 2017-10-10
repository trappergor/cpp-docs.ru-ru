---
title: "Ошибка компилятора C2410 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3d2f8f9b21d44c2fce92c526de0f6d53b99930b8
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2410"></a>Ошибка компилятора C2410
«Идентификатор»: неоднозначное имя члена в «контекст»  
  
 Идентификатор является членом более чем одной структуры или объединения в этом контексте.  
  
 Используйте структуры или объединения спецификатор операнда, который вызвал ошибку. Спецификатор структуры или объединения является идентификатором типа `struct` или `union` ( `typedef` имени или переменной того же типа, что структуры или объединения на которые ссылаются). Описатель должен быть левым операндом первого оператора выбора члена (.) чтобы использовать операнд.
