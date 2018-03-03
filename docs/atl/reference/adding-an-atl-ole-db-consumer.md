---
title: "Добавление потребителя ATL OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: defc933014bd287eb48f53635efba12a40960711
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-ole-db-consumer"></a>Добавление потребителя ATL OLE DB
Этот мастер используется для добавления в проект потребителя ATL OLE DB. Потребителя ATL OLE DB состоит из OLE DB доступа класса и привязки данных для доступа к источнику данных. Проект необходимо создать как COM-приложение ATL или как приложение MFC или Win32, содержащее поддержку ATL (которую мастер потребителя ATL OLE DB добавляется автоматически).  
  
 **Примечание** потребителя OLE DB можно добавить в проект MFC. В противном случае мастер потребителя ATL OLE DB добавляет необходимую поддержку COM в проект. Предполагается, что при создании проекта MFC был установлен **элементы управления ActiveX** флажок (в **дополнительные функции** мастера приложений MFC проекта), который включен по умолчанию. При выборе этого параметра гарантирует, что приложение вызывает **CoInitialize** и **CoUninitialize**. Если вы не выбрали **элементы управления ActiveX** при создании проекта MFC, необходимо вызвать **CoInitialize** и **CoUninitialize** в основном коде.  
  
### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Добавление потребителя ATL OLE DB в проект  
  
1.  В представлении классов щелкните правой кнопкой мыши проект. В контекстном меню щелкните **добавить** и нажмите кнопку **Добавление класса**.  
  
2.  В папке Visual C++ дважды щелкните **потребителя ATL OLE DB** значок или выберите его и нажмите кнопку **откройте**.  
  
     Откроется Мастер потребителя ATL OLE DB.  
  
3.  Задайте параметры, как описано в [Мастер потребителя ATL OLE DB](../../atl/reference/atl-ole-db-consumer-wizard.md).  
  
4.  Нажмите кнопку **Готово** для завершения работы мастера. Вновь созданный код потребителя OLE DB будет вставлен в своем проекте.  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)

