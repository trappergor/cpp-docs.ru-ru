---
title: Ошибка компилятора C2097 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b867c7f043d796f208fdc7100509893147daf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2097"></a>Ошибка компилятора C2097
Недопустимая инициализация  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Инициализация переменной с помощью Непостоянное значение.  
  
2.  Инициализация короткого адреса с длинный адрес.  
  
3.  Инициализация локальной структуры, объединения или массива с использованием неконстантного выражения при компиляции с параметром **/Za**.  
  
4.  Инициализация с использованием выражения, содержащего оператор-запятую.  
  
5.  Инициализация с помощью выражения, не являющегося константным или символьной.