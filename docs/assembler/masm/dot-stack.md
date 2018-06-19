---
title: . СТЕК | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .STACK
dev_langs:
- C++
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab47677da8db2afca73a078b110300a017e7c8d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052304"
---
# <a name="stack"></a>.STACK
При использовании с [. МОДЕЛЬ](../../assembler/masm/dot-model.md), определяет сегмент стека (с именем сегмента СТЕК). Необязательный `size` указывает число байтов для стека (по умолчанию 1024). `.STACK` Директива автоматически закрывает инструкцию стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STACK [[size]]  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)