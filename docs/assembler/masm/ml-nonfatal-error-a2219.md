---
title: "Некритичная ошибка ML A2219 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2219
dev_langs: C++
helpviewer_keywords: A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f918e79b47a6a1ea88ac8f01dd43f20fb793f99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2219"></a>Некритичная ошибка ML A2219
**Неправильное выравнивание для смещения в код очистки**  
  
 Операнд для [. ALLOCSTACK](../../assembler/masm/dot-allocstack.md) и [. SAVEREG](../../assembler/masm/dot-savereg.md) должно быть кратным 8.  Операнд для [. SAVEXMM128](../../assembler/masm/dot-savexmm128.md) и [. SETFRAME](../../assembler/masm/dot-setframe.md) должна быть кратной 16.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)