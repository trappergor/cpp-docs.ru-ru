---
title: Если нужно вызвать AtlAxWinTerm? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinTerm
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61830023d3fb67d331784769f32cda4eee8355b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>Если нужно вызвать AtlAxWinTerm?
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) отменяет регистрацию **«AtlAxWin80»** класс окна. Эту функцию следует вызывать (если больше не требуется для создания узла windows) после уничтожения всех существующих окон узла. Если не вызвать эту функцию, класс окна будет отменена автоматически при завершении процесса.  
  
## <a name="see-also"></a>См. также  
 Если нужно вызвать AtlAxWinInit  
[Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

