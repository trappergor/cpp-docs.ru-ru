---
title: "Сопроцессор с плавающей запятой и соглашения о вызовах | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d16e5c99dc96618bc8657fbd7d3025f9dd410dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах
При создании сборки подпрограммы для вычислений с плавающей точки сопроцессора, необходимо сохранять значение с плавающей запятой и очистить стек сопроцессора, если только вы возвращаете **float** или **двойные** значение (которое функция должна возвращать в ST(0)).  
  
## <a name="see-also"></a>См. также  
 [Соглашения о вызовах](../cpp/calling-conventions.md)