---
title: Службы ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule
dev_langs:
- C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4875c4844b97e3715c3804f83f4fa3e863eb53bc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761034"
---
# <a name="atl-services"></a>Службы ATL

Для создания объекта ATL COM, таким образом, чтобы он работает в службе, просто выберите из списка параметров для сервера в мастере проектов ATL службы (EXE). Мастер создаст класс, производный от `CAtlServiceModuleT` для реализации службы.

При построении объекта ATL COM как услуга, оно будет зарегистрировано только как локальный сервер и она не будет отображаться в списке служб на панели управления. Это, так как это упрощает отладку службы, как локальный сервер чем как услуга. Чтобы установить его в качестве службы, выполните следующее в командной строке:

`YourEXE` `.exe /Service`

Чтобы удалить его, используйте следующую команду:

`YourEXE` `.exe /UnregServer`

Первые четыре в этом разделе рассматриваются действия, которые происходят при выполнении `CAtlServiceModuleT` функций-членов. Эти разделы отображаются в той же последовательности, как функции обычно вызываются. Чтобы лучше понять эти разделы, рекомендуется использовать исходный код, созданный мастером проектов ATL как ссылка. Эти первые четыре относятся следующие.

- [Функция CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

- [Функция CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

- [Функция CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

- [Функция CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

Последние три рассматриваются основные понятия, связанные с разработкой службы:

- [Записи реестра](../atl/registry-entries.md) для службы ATL

- [DCOMCNFG](../atl/dcomcnfg.md)

- [Советы по отладке](../atl/debugging-tips.md) для службы ATL

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)

