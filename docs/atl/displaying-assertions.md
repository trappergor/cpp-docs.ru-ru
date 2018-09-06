---
title: Отображение утверждений | Документация Майкрософт
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
ms.openlocfilehash: 8ff7b9b29808e310be2d5568add64a0294bc67e7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762386"
---
# <a name="displaying-assertions"></a>Отображение утверждений

Если перестать отвечать на запросы клиента, подключенного к вашей службе, служба может сигнал и отображается окно сообщения, которое вы не сможете см. в разделе. Это можно проверить с помощью отладчика Visual C++ для отладки кода (см. в разделе [с помощью диспетчера задач](../atl/using-task-manager.md) ранее в этом разделе).

Если вы определили, что служба отображает окно сообщения, которое не отображается, может потребоваться задать **разрешить службе взаимодействие с рабочим столом** параметр перед использованием службы снова. Этот параметр указан параметр запуска, который разрешает все окна сообщений отображаются в службе отображение на рабочем столе. Чтобы задать этот параметр, откройте панель управления службами приложений, выберите службу, нажмите кнопку **запуска**, а затем выберите **разрешить службе взаимодействие с рабочим столом** параметр.

## <a name="see-also"></a>См. также

[Советы по отладке](../atl/debugging-tips.md)

