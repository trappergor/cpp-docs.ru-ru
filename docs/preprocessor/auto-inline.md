---
title: auto_inline | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs:
- C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de012a31fe68c68d4e64df2d3fa10b44d9112735
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="autoinline"></a>auto_inline
Исключает все функции, определенные в пределах диапазона где **off** указан из числа кандидатов на автоматическое расширение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## <a name="remarks"></a>Примечания  
 Для использования **auto_inline** pragma, поместите ее перед или сразу после (не в) определение функции. Эта директива #pragma начинает действовать с первого определения функции после вхождения данной директивы.  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)