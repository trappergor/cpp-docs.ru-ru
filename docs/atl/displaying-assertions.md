---
title: Отображение утверждения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9133d2fadfa4158eef9755fff7e0d2a62478966
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="displaying-assertions"></a>Отображение утверждения
Если перестать отвечать на запросы клиентов, подключенных к службе, служба может утвержденное и отображается окно сообщения, которые еще не видит. Это можно проверить с помощью отладчика Visual C++ для отладки кода (в разделе [с помощью диспетчера задач](../atl/using-task-manager.md) ранее в этом разделе).  
  
 Если выяснилось, что служба отображает окно сообщения, которое не отображается, может потребоваться установить **разрешить службе взаимодействовать с рабочим столом** параметр, прежде чем снова с помощью службы. Этот параметр указан параметр запуска, разрешающая все окна сообщений отображаются службой для отображается на рабочем столе. Этот параметр задан, откройте приложение службы на панели управления, выберите службу, нажмите кнопку **запуска**, а затем выберите **разрешить службе взаимодействовать с рабочим столом** параметр.  
  
## <a name="see-also"></a>См. также  
 [Советы по отладке](../atl/debugging-tips.md)

