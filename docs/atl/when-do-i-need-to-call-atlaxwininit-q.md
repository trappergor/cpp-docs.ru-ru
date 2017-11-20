---
title: "Если нужно вызвать AtlAxWinInit? | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinInit
dev_langs: C++
helpviewer_keywords: AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2ec7d8d15b8219071b593368ed539d92ff3c9032
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>Если нужно вызвать AtlAxWinInit?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) регистрирует **«AtlAxWin80»** класса окна (а также пару пользовательских сообщений окна), поэтому эту функцию необходимо вызывать перед попыткой создания главного окна. Тем не менее, не всегда требуется эта функция вызывается явно, так как размещение API-интерфейсы (и классы, которые их используют) часто эта функция вызывается для вас. Нет никакого вреда вызов этой функции более одного раза. .  
  
## <a name="see-also"></a>См. также  
 Если нужно вызвать AtlAxWinTerm     
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)
