---
title: "Ошибка компилятора C2410 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2410
dev_langs: C++
helpviewer_keywords: C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3cd5dfa7b33f5af5c57f6479170a7a56df39a0e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2410"></a>Ошибка компилятора C2410
«Идентификатор»: неоднозначное имя члена в «контекст»  
  
 Идентификатор является членом более чем одной структуры или объединения в этом контексте.  
  
 Используйте структуры или объединения спецификатор операнда, который вызвал ошибку. Спецификатор структуры или объединения является идентификатором типа `struct` или `union` ( `typedef` имени или переменной того же типа, что структуры или объединения на которые ссылаются). Описатель должен быть левым операндом первого оператора выбора члена (.) чтобы использовать операнд.