---
title: 'Серверы автоматизации: Вопросы времени жизни объектов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a53d1a9d3849798fa1e583c0758b156d282a401c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397121"
---
# <a name="automation-servers-object-lifetime-issues"></a>Серверы автоматизации. Вопросы времени жизни объектов

Когда клиент автоматизации создает или активирует объект OLE, сервер передает клиент указатель на этот объект. Клиент устанавливает ссылку на объект посредством вызова функции OLE [IUnknown::AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref). Эта ссылка действует до клиент вызывает [IUnknown::Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). (Клиентские приложения, написанные с помощью библиотеки Microsoft Foundation Class классы OLE не потребуется выполнять эти вызовы framework делает это.) Система OLE и сам сервер, могут устанавливать ссылки на объект. Сервер не должен уничтожить объект, до тех пор, пока внешние ссылки на объект остаются в силе.

Платформа поддерживает внутренний счетчик числа ссылок для любого серверного объекта, производного от [CCmdTarget](../mfc/reference/ccmdtarget-class.md). Этот счетчик обновляется в том случае, когда клиент автоматизации или другая сущность, добавляет или удаляет ссылку на объект.

Когда счетчик ссылок становится равным 0, платформа вызывает виртуальную функцию [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease). Реализация по умолчанию эта функция вызывает **удалить** оператор удаление данного объекта.

Библиотеки Microsoft Foundation Class предоставляет дополнительные средства для управления поведением приложения в том случае, когда внешние клиенты имеют ссылки на объекты приложения. Помимо подсчитывается количество ссылок для каждого объекта, серверы поддерживают общего счетчика активных объектов. Глобальные функции [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) и [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) обновить приложения число активных объектов. Если это число не равно нулю, приложение не прекращен, когда пользователь выбирает закрыть из меню системы или выхода из меню "файл". Вместо этого главное окно приложения является скрытым (но не уничтожается) пока все ожидающие клиентские запросы будут завершены. Как правило `AfxOleLockApp` и `AfxOleUnlockApp` , называются в конструкторы и деструкторы, соответственно, классами, которые поддерживают службы автоматизации.

Иногда обстоятельствах принудительно завершить, а клиент по-прежнему имеет ссылку на объект. Например ресурс, от которого зависит сервера могут стать недоступными, приведшая к сообщение об ошибке. Пользователь также может закрыть документ сервера, который содержит объекты, к которым другие приложения имеют ссылки.

В пакете SDK для Windows, см. в разделе `IUnknown::AddRef` и `IUnknown::Release`.

## <a name="see-also"></a>См. также

[Серверы автоматизации](../mfc/automation-servers.md)<br/>
[AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

