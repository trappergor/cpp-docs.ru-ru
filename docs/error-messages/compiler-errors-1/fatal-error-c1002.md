---
title: Неустранимая ошибка C1002 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c63a8d399b3e8c781694d89825e7898fd1db4639
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225055"
---
# <a name="fatal-error-c1002"></a>Неустранимая ошибка C1002
не хватает размера кучи на 2-ом проходе компилятора  
  
 Компилятору недостаточно пространства динамической памяти во время второго прохода, возможно, из-за программа с слишком много символов или сложных выражений.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Разделите исходный файл на несколько файлов меньшего размера.  
  
2.  Разделите выражения на более мелкие части выражения.  
  
3.  Удалите другие программы или драйверы, которые занимают память.