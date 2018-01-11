---
title: "Ошибка компилятора C2092 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2092
dev_langs: C++
helpviewer_keywords: C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b844429b0264eea109c1757b192f596a6366d1ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2092"></a>Ошибка компилятора C2092
Тип элемента массива «имя массива» не может быть функцией  
  
 Массивы функций не разрешены. Используйте массив указателей на функции.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2092:  
  
```  
// C2092.cpp  
typedef void (F) ();  
typedef F AT[10];   // C2092  
```  
  
## <a name="example"></a>Пример  
 Возможное решение  
  
```  
// C2092b.cpp  
// compile with: /c  
typedef void (F) ();  
typedef F * AT[10];  
```