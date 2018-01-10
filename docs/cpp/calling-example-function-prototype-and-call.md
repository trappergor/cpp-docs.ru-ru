---
title: "Пример вызова: Прототип и вызов функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: afdc7d91e11936ebfd1775477f8c684ae4ff6d62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="calling-example-function-prototype-and-call"></a>Пример вызова. Прототип и вызов функции
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 В следующем примере показаны результаты вызова функции с использованием различных соглашений о вызовах.  
  
 Этот пример основан на следующей схеме функции. Замените `calltype` соответствующим соглашением о вызове.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 Дополнительные сведения см. в разделе [пример результатов вызова](../cpp/results-of-calling-example.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Соглашения о вызовах](../cpp/calling-conventions.md)