---
title: "Если нужно вызвать AtlAxWinInit? | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69dfcfbe0c8c05d275a5f3a8f86c30b0e59bd3a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>Если нужно вызвать AtlAxWinInit?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) регистрирует **«AtlAxWin80»** класса окна (а также пару пользовательских сообщений окна), поэтому эту функцию необходимо вызывать перед попыткой создания главного окна. Тем не менее, не всегда требуется эта функция вызывается явно, так как размещение API-интерфейсы (и классы, которые их используют) часто эта функция вызывается для вас. Нет никакого вреда вызов этой функции более одного раза. .  
  
## <a name="see-also"></a>См. также  
 Если нужно вызвать AtlAxWinTerm     
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)
