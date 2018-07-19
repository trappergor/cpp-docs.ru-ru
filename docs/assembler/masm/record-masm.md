---
title: ЗАПИСЬ (MASM) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- RECORD
dev_langs:
- C++
helpviewer_keywords:
- RECORD directive
ms.assetid: c83db394-0fe3-468f-813f-13302cdc862d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e726053a9146cf88ed4e84045118d19b7094ed37
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057268"
---
# <a name="record-masm"></a>RECORD (MASM)
Объявляет тип записи, состоящий из указанного поля. *FieldName* имена полей, *ширина* указывает количество битов, и *выражение* предоставляет его начального значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
   recordname RECORD fieldname:width [[= expression]]   
[[, fieldname:width [[= expression]]]]...  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)