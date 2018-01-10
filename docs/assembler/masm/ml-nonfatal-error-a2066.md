---
title: "Некритичная ошибка ML A2066 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2066
dev_langs: C++
helpviewer_keywords: A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b85402feccf4f85f2f1dd60902bb5759ed723911
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2066"></a>Некритичная ошибка ML A2066
**несовместимые размер режим и сегмент ЦП**  
  
 Была предпринята попытка открыть сегмент с **USE16**, **USE32**, или **плоский** атрибут, который несовместим с указанным ЦП или изменить на 16-разрядных ЦП в 32-разрядной Сегмент.  
  
 **USE32** и **плоский** атрибуты должен предшествовать.386 или больше директивы процессора.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)