---
title: "Если нужно вызвать AtlAxWinTerm? | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AtlAxWinTerm
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c52c5295108ef01dc23ea9f945850e91a9806d6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>Если нужно вызвать AtlAxWinTerm?
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) отменяет регистрацию **«AtlAxWin80»** класс окна. Эту функцию следует вызывать (если больше не требуется для создания узла windows) после уничтожения всех существующих окон узла. Если не вызвать эту функцию, класс окна будет отменена автоматически при завершении процесса.  
  
## <a name="see-also"></a>См. также  
 Если нужно вызвать AtlAxWinInit  
[Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

