---
title: Некритичная ошибка ML A2066 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2066
dev_langs:
- C++
helpviewer_keywords:
- A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92cc0daf183f617767ff5ff119c5e95b8f34cd51
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2066"></a>Некритичная ошибка ML A2066
**несовместимые размер режим и сегмент ЦП**  
  
 Была предпринята попытка открыть сегмент с **USE16**, **USE32**, или **плоский** атрибут, который несовместим с указанным ЦП или изменить на 16-разрядных ЦП в 32-разрядной Сегмент.  
  
 **USE32** и **плоский** атрибуты должен предшествовать.386 или больше директивы процессора.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)