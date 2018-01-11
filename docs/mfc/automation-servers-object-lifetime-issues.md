---
title: "Серверы автоматизации: Вопросы времени жизни объектов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6c9fab7af74dee482c5e8dffb327da9c037796fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="automation-servers-object-lifetime-issues"></a>Серверы автоматизации. Вопросы времени жизни объектов
Когда клиент автоматизации создает или активирует объект OLE, сервер передает клиент указатель на этот объект. Клиент устанавливает ссылку на объект через вызов функции OLE [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Эта ссылка действует до клиент вызывает метод [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317). (Клиентские приложения, написанные с использованием классов библиотеки классов Microsoft Foundation OLE не требуется выполнять эти вызовы платформа делает это.) Система OLE и сам сервер может установить ссылки на объект. Сервер не следует удалить объект, при условии, что внешние ссылки на объект остаются в силе.  
  
 Платформа поддерживает внутренний счетчик числа ссылок для любого серверного объекта, производного от [CCmdTarget](../mfc/reference/ccmdtarget-class.md). Этот счетчик обновляется в том случае, когда клиент автоматизации или другой сущности, добавляет или удаляет ссылку на объект.  
  
 Когда счетчик ссылок становится равным 0, платформа вызывает виртуальную функцию [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease). Реализация по умолчанию эта функция вызывает **удалить** оператор, чтобы удалить этот объект.  
  
 Библиотеки классов Microsoft Foundation предоставляет дополнительные средства для управления поведением приложения, когда внешние клиенты имеют ссылки на объекты приложения. Помимо подсчитывается количество ссылок для каждого объекта, серверы поддерживают глобальные число активных объектов. Глобальные функции [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) и [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) обновить приложения число активных объектов. Если это число является ненулевым, приложение не прекращен, когда пользователь выбирает закрыть из меню системы или выход из меню «файл». Вместо этого главное окно приложения скрыты (но не удаляются) до всех ожидающих клиентских запросов будут завершены. Как правило `AfxOleLockApp` и `AfxOleUnlockApp` будут вызываться в конструкторы и деструкторы, соответственно, классов, поддерживающих автоматизацию.  
  
 Иногда обстоятельствах заставить сервер завершать, пока клиент все еще содержит ссылку на объект. Например ресурс, от которого зависит сервер может стать недоступным, приведшая к возникает ошибка. Пользователь также может закрыть серверный документ, содержащий объекты, с которыми связаны другие приложения.  
  
 В Windows SDK, в разделе `IUnknown::AddRef` и `IUnknown::Release`.  
  
## <a name="see-also"></a>См. также  
 [Серверы автоматизации](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

