---
title: ЛОКАЛЬНЫЙ (MASM) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed9926d23f2e1e8636f31a6f586609ae22d38acd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053575"
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