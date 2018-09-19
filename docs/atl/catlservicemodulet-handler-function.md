---
title: Функция CAtlServiceModuleT::Handler | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs:
- C++
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c8dc0b0d41a18c775258e1eacddd8e4dbebdb3d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039222"
---
# <a name="catlservicemodulethandler-function"></a>Функция CAtlServiceModuleT::Handler

`CAtlServiceModuleT::Handler` — Это процедуры, что диспетчер управления службами (SCM) вызывает получение сведений о состоянии службы и присвоить ему различные инструкции (например, остановка или приостановка). Диспетчер управления Службами передает код операции для `Handler` для указания, что должен делать. Услуга созданный ATL по умолчанию обрабатывает только инструкция stop. Если диспетчер управления Службами передает инструкция stop, службы показывает диспетчера управления Службами, что программа является остановка. Затем вызывается службой `PostThreadMessage` Чтобы отправить сообщение на самого себя. Это завершает цикл обработки сообщений и службы в конечном счете будет закрыт.

Чтобы обрабатывать дополнительные инструкции, необходимо изменить `m_status` член данных инициализирован в `CAtlServiceModuleT` конструктор. Этот элемент данных сообщает SCM кнопки, которые следует включить при выборе службы в приложении службы на панели управления.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

