---
title: "Ошибка компилятора C2097 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e50154d88a5019cdc181c4921c09cbd222d8b530
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2097"></a>Ошибка компилятора C2097
Недопустимая инициализация  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Инициализация переменной с помощью Непостоянное значение.  
  
2.  Инициализация короткого адреса с длинный адрес.  
  
3.  Инициализация локальной структуры, объединения или массива с использованием неконстантного выражения при компиляции с параметром **/Za**.  
  
4.  Инициализация с использованием выражения, содержащего оператор-запятую.  
  
5.  Инициализация с помощью выражения, не являющегося константным или символьной.