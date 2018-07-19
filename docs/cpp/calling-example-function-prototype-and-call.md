---
title: 'Пример вызова: Прототип и вызов функции | Документы Microsoft'
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
ms.openlocfilehash: 2fcfda308ed3a5723b32729e7986a7063e9928fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409375"
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