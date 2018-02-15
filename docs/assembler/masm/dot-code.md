---
title: ". КОД | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de0a9b8930c04929b05b02931a1f796d28a78099
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="code"></a>.CODE
При использовании с [. МОДЕЛЬ](../../assembler/masm/dot-model.md), указывает на начало сегмента кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`name`|Необязательный параметр, который указывает имя сегмента кода. Имя по умолчанию — _TEXT compact очень мала, малый, и плоский [моделей](../../assembler/masm/dot-model.md). Имя по умолчанию — *modulename*_TEXT для других моделей.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)