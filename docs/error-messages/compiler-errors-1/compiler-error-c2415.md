---
title: Ошибка компилятора C2415 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2415
dev_langs:
- C++
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ad06cdf891c9b958f6cf08e724f4003a8507c2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2415"></a>Ошибка компилятора C2415
Недопустимый тип операнда  
  
 Код операции не использует операнды данного типа.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Код операции не поддерживает количество используемых операндов. Проверьте сборку с руководством по языку определить правильное число операндов.  
  
2.  Новый процесс поддерживает инструкции с новыми типами. Настройка [/arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md) параметр, чтобы использовать более новый процессор.