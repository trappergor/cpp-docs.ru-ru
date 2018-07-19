---
title: . КОД | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59e376fc9c10ab8891b02e4da334341ae0534b73
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051242"
---
# <a name="code"></a>.CODE
При использовании с [. МОДЕЛЬ](../../assembler/masm/dot-model.md), указывает на начало сегмента кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`name`|Необязательный параметр, который указывает имя сегмента кода. Имя по умолчанию — _TEXT compact очень мала, малый, и плоский [моделей](../../assembler/masm/dot-model.md). Имя по умолчанию — *modulename*_TEXT для других моделей.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)