---
title: Функция CAtlServiceModuleT::Handler
ms.date: 11/04/2016
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: e344fd36ad6c70a80486eef6a10eacd8a88a2baf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273378"
---
# <a name="catlservicemodulethandler-function"></a>Функция CAtlServiceModuleT::Handler

`CAtlServiceModuleT::Handler` — Это процедуры, что диспетчер управления службами (SCM) вызывает получение сведений о состоянии службы и присвоить ему различные инструкции (например, остановка или приостановка). Диспетчер управления Службами передает код операции для `Handler` для указания, что должен делать. Услуга созданный ATL по умолчанию обрабатывает только инструкция stop. Если диспетчер управления Службами передает инструкция stop, службы показывает диспетчера управления Службами, что программа является остановка. Затем вызывается службой `PostThreadMessage` Чтобы отправить сообщение на самого себя. Это завершает цикл обработки сообщений и службы в конечном счете будет закрыт.

Чтобы обрабатывать дополнительные инструкции, необходимо изменить `m_status` член данных инициализирован в `CAtlServiceModuleT` конструктор. Этот элемент данных сообщает SCM кнопки, которые следует включить при выборе службы в приложении службы на панели управления.

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)
