---
title: "Пример вызова: Прототип и вызов функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 897771dbe2d769744bd5dc119083c9db243d56c0
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="calling-example-function-prototype-and-call"></a>Пример вызова. Прототип и вызов функции
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 В следующем примере показаны результаты вызова функции с использованием различных соглашений о вызове.  
  
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
