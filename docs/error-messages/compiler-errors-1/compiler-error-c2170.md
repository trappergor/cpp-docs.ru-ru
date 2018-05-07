---
title: Ошибка компилятора C2170 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2170
dev_langs:
- C++
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad0d19dff10d04d155d8071ffb349664f6b3104e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2170"></a>Ошибка компилятора C2170
«Идентификатор»: не объявлена как функция, не может быть встроенной  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Директива pragma `intrinsic` используется для элемента, не являющихся функциями.  
  
2.  Директива pragma `intrinsic` используется для функции, не имеющей форму.