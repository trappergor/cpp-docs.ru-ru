---
title: "-Zc: триграфы (подстановка триграфов) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 739e772c87c937a552e07a32fa5bb80b1a1e2508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (подстановка триграфов)
Когда **/Zc: trigraphs** указан, компилятор заменяет последовательность символов триграфов, используя соответствующие знаки пунктуации. Чтобы отключить подстановку триграфов, укажите **/Zc:trigraphs-**. По умолчанию **/Zc: trigraphs** отключен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Триграф состоит из двух последовательных вопросительных знаков ("??"), за которыми следует третий уникальный знак. Например, компилятор заменяет «?? =» с помощью символа «#». Следует использовать триграфы в файлах исходного кода на С, которые используют набор символов, не содержащий подходящего графического представления для некоторых знаков пунктуации.  
  
 Список триграфов C/C++ и пример их использования см. в разделе [триграфов](../../c-language/trigraphs.md).  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)   
 [Триграфы](../../c-language/trigraphs.md)