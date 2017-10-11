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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d6955a610e3109c3b16edf96913be4503ee4c647
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2097"></a>Ошибка компилятора C2097
Недопустимая инициализация  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Инициализация переменной с помощью Непостоянное значение.  
  
2.  Инициализация короткого адреса с длинный адрес.  
  
3.  Инициализация локальной структуры, объединения или массива с использованием неконстантного выражения при компиляции с параметром **/Za**.  
  
4.  Инициализация с использованием выражения, содержащего оператор-запятую.  
  
5.  Инициализация с помощью выражения, не являющегося константным или символьной.
