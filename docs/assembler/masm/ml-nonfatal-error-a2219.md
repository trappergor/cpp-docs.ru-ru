---
title: Некритичная ошибка ML A2219 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2219
dev_langs:
- C++
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d1ae9eb4b8535ac3f1363bb1059468cddf5636
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2219"></a>Некритичная ошибка ML A2219
**Неправильное выравнивание для смещения в код очистки**  
  
 Операнд для [. ALLOCSTACK](../../assembler/masm/dot-allocstack.md) и [. SAVEREG](../../assembler/masm/dot-savereg.md) должно быть кратным 8.  Операнд для [. SAVEXMM128](../../assembler/masm/dot-savexmm128.md) и [. SETFRAME](../../assembler/masm/dot-setframe.md) должна быть кратной 16.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)