---
title: Каковы издержки при наследовании классов от CObject? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffff35cdef6cf2f730687334bbb56bc078371a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381681"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Каковы издержки при наследовании классов от CObject?
Затраты на производные от класса [CObject](../mfc/reference/cobject-class.md) сводится к минимуму. Производный класс наследует только четыре виртуальных функций и одним [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
