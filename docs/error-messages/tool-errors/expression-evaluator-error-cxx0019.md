---
title: Ошибка вычислителя выражений CXX0019 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52e1679374e105ab06ce245ba68cfe92706689e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302494"
---
# <a name="expression-evaluator-error-cxx0019"></a>Ошибка вычислителя выражений CXX0019
неправильное приведение типа  
  
 Вычислитель выражений C не удается выполнить приведение типа согласно записи.  
  
 Эта ошибка идентична ошибке CAN0019.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Указанный тип неизвестен.  
  
2.  Было слишком много уровней типов указателей. Например приведение типов  
  
    ```  
    (char **)h_message  
    ```  
  
     не удается вычислить с помощью вычислителя выражений.