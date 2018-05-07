---
title: Если нужно вызвать AtlAxWinInit? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9aa1dd14ccae555d4ab9acbbac15e9b66cafe6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>Если нужно вызвать AtlAxWinInit?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) регистрирует **«AtlAxWin80»** класса окна (а также пару пользовательских сообщений окна), поэтому эту функцию необходимо вызывать перед попыткой создания главного окна. Тем не менее, не всегда требуется эта функция вызывается явно, так как размещение API-интерфейсы (и классы, которые их используют) часто эта функция вызывается для вас. Нет никакого вреда вызов этой функции более одного раза. .  
  
## <a name="see-also"></a>См. также  
 Если нужно вызвать AtlAxWinTerm     
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)
