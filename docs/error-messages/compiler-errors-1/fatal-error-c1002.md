---
title: "Неустранимая ошибка C1002 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1002
dev_langs: C++
helpviewer_keywords: C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d299c6793e106ce516a81a9a81312ef0a09c25bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1002"></a>Неустранимая ошибка C1002
не хватает размера кучи на 2-ом проходе компилятора  
  
 Компилятору недостаточно пространства динамической памяти во время второго прохода, возможно, из-за программа с слишком много символов или сложных выражений.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Разделите исходный файл на несколько файлов меньшего размера.  
  
2.  Разделите выражения на более мелкие части выражения.  
  
3.  Удалите другие программы или драйверы, которые занимают память.