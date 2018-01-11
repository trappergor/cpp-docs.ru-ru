---
title: "Оптимизация | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 35b5147b3561df409906af9134ae4ec921a7d16b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="optimize"></a>optimize
Задает оптимизации, которые требуется выполнять для каждой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## <a name="remarks"></a>Примечания  
 **Оптимизировать** директива pragma должна находиться за пределами функции и вступает в силу в первой функции, определенной после этой директивы. **На** и **off** аргументы выключают параметры, указанные в *списке оптимизации* или отключить.  
  
 *Списке оптимизации* может содержать ноль или несколько параметров, приведенных в следующей таблице.  
  
### <a name="parameters-of-the-optimize-pragma"></a>Параметры директивы #pragma optimize  
  
|Параметры|Тип оптимизации|  
|--------------------|--------------------------|  
|**g**|Включить глобальную оптимизацию.|  
|**s** или **t**|Указывать короткую или быструю последовательность машинного кода.|  
|**y**|Создавать указатели фреймов в стеке программы.|  
  
 Это же буквы используются с [/o](../build/reference/o-options-optimize-code.md) параметры компилятора. Например, следующая директива pragma эквивалентно **/Os** параметр компилятора:  
  
```  
#pragma optimize( "ts", on )  
```  
  
 С помощью **оптимизировать** pragma с пустой строкой (**» «**) представляет собой специальную форму директивы:  
  
 При использовании **off** она отключает оптимизации, перечисленные в таблице ранее в этом разделе.  
  
 При использовании **на** параметра, она снова устанавливает оптимизации, указанные с [/o](../build/reference/o-options-optimize-code.md) параметр компилятора.  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)