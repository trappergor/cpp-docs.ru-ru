---
title: "Неустранимая ошибка C1002 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cab0e1db2d84fb5ba84d773f28e70341faf10ac6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1002"></a>Неустранимая ошибка C1002
не хватает размера кучи на 2-ом проходе компилятора  
  
 Компилятору недостаточно пространства динамической памяти во время второго прохода, возможно, из-за программа с слишком много символов или сложных выражений.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Разделите исходный файл на несколько файлов меньшего размера.  
  
2.  Разделите выражения на более мелкие части выражения.  
  
3.  Удалите другие программы или драйверы, которые занимают память.
