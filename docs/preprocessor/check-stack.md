---
title: "check_stack | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
dev_langs:
- C++
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70f88d1eabb58f384d754803674b35f0bd9dbeda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="checkstack"></a>check_stack
Указывает компилятору на необходимость выключения стековых зондов, если **off** (или  **-** ) указан, или если включить стековые зонды **на** (или  **+** ) указан.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | -}  
```  
  
## <a name="remarks"></a>Примечания  
 Если аргумент не указан, стековые зонды обрабатываются в соответствии с настройкой по умолчанию. Эта директива #pragma начинает действовать с первой функции, определенной после вхождения данной директивы. Стековые зонды не являются частью макросов или функций, создаваемых как встроенные.  
  
 Если не задан аргумент для **check_stack** pragma, проверка стека возвращается к поведению, указанный в командной строке. Дополнительные сведения см. в разделе [справочнике по компилятору](../build/reference/compiler-options.md). Взаимодействие **#pragma check_stack** и [/GS](../build/reference/gs-control-stack-checking-calls.md) приведена в следующей таблице.  
  
### <a name="using-the-checkstack-pragma"></a>Использование директивы #pragma check_stack  
  
|Синтаксис|Скомпилировано с использованием<br /><br /> параметра /Gs?|Действие|  
|------------|------------------------------------|------------|  
|**#pragma check_stack ()** или<br /><br /> **#pragma check_stack**|Да|Отключает проверку стека для последующих функций|  
|**#pragma check_stack ()** или<br /><br /> **#pragma check_stack**|Нет|Включает проверку стека для последующих функций|  
|**#pragma check_stack(on)**<br /><br /> или **#pragma check_stack +**|"Да" или "Нет"|Включает проверку стека для последующих функций|  
|**#pragma check_stack(off)**<br /><br /> или **#pragma check_stack -**|"Да" или "Нет"|Отключает проверку стека для последующих функций|  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)