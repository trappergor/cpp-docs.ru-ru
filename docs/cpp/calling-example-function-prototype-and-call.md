---
title: 'Пример вызова: Прототип и вызов функции | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9ee05b55a0945d18e78dc67df5653c06c8a1bc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404386"
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