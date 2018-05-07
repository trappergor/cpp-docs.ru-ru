---
title: Ошибка компилятора C2439 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33bfe8ebf00850a54020b2a3f21159daf28b7224
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2439"></a>Ошибка компилятора C2439
«Идентификатор»: не удается инициализировать член  
  
 Не удается инициализировать класса, структуры или члена объединения.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Попробуйте инициализировать косвенный базовый класс или структуру.  
  
2.  Попытка инициализировать наследуемый член класса или структуры. Если сделать унаследованный член необходимо инициализировать конструктору класса или структуры.