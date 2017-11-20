---
title: "ЛОКАЛЬНЫЙ (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Local
dev_langs: C++
helpviewer_keywords: LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60dac02a5bf08f7ced2fbb8adb46cc558cbfe44b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="local-masm"></a>LOCAL (MASM)
В директиве первого макроса **ЛОКАЛЬНОГО** определяет метки, которые являются уникальными для каждого экземпляра макроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>Примечания  
 В директиве второй в определении процедуры (**PROC**), **ЛОКАЛЬНОГО** создает стековую переменные, которые существуют во время процедуры. *Метка* может быть простой переменной или массив, содержащий *число* элементов.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)