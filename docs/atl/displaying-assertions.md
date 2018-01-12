---
title: "Отображение утверждения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bff1ab29841ff2dd9973d538bb763d1fc1126a8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="displaying-assertions"></a>Отображение утверждения
Если перестать отвечать на запросы клиентов, подключенных к службе, служба может утвержденное и отображается окно сообщения, которые еще не видит. Это можно проверить с помощью отладчика Visual C++ для отладки кода (в разделе [с помощью диспетчера задач](../atl/using-task-manager.md) ранее в этом разделе).  
  
 Если выяснилось, что служба отображает окно сообщения, которое не отображается, может потребоваться установить **разрешить службе взаимодействовать с рабочим столом** параметр, прежде чем снова с помощью службы. Этот параметр указан параметр запуска, разрешающая все окна сообщений отображаются службой для отображается на рабочем столе. Этот параметр задан, откройте приложение службы на панели управления, выберите службу, нажмите кнопку **запуска**, а затем выберите **разрешить службе взаимодействовать с рабочим столом** параметр.  
  
## <a name="see-also"></a>См. также  
 [Советы по отладке](../atl/debugging-tips.md)

