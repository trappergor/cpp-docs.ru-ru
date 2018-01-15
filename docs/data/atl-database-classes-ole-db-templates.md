---
title: "Классы баз данных ATL (шаблоны OLE DB) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ca7607c037cdb1f6a42a2267d64ef274d1041cb2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="atl-database-classes-ole-db-templates"></a>Классы баз данных библиотеки ATL (шаблоны OLE DB)
Корпорация Майкрософт предоставляет несколько реализаций OLE DB, набор COM-интерфейсов, обеспечивающих унифицированный доступ к данным в различных источниках и форматах.  OLE DB обычно не используется; Данная документация является для разработчиков, которые обслуживание кода прежних версий. Новые приложения должны использовать ODBC для подключения к источникам данных SQL.
  
 Шаблоны OLE DB являются шаблонами C++ библиотеки ATL, которые упрощают использование классов, реализующих многие часто используемые интерфейсы OLE DB технологии баз данных OLE DB.  
  
 Библиотека шаблонов состоит из двух частей:  
  
-   [Шаблоны потребителя OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) используется для реализации приложений OLE DB клиента (покупатели).  
  
-   [Шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) используется для реализации приложения OLE DB для сервера (поставщик).  
  
 Кроме того [атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md) предоставляют удобный способ создания потребителей OLE DB. Атрибуты OLE DB вводят код, основанный на шаблонах потребителей OLE DB для создания рабочих потребителей OLE DB.  
  
 Обратите внимание, что библиотека MFC содержит класс, [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), которое отображает записи базы данных в элементах управления. Представление — это представление формы, непосредственно подключенные к `CRowset` объекта и отображает поля `CRowset` в элементах управления шаблона диалогового окна.  
  
 Дополнительные сведения см. в разделе [OLE DB программирования](../data/oledb/ole-db-programming.md) и [Руководство программиста OLE DB](http://go.microsoft.com/fwlink/p/?linkid=121548).  
  
## <a name="see-also"></a>См. также  
 [Создание потребителя OLE DB](../data/oledb/creating-an-ole-db-consumer.md)   
 [Создание поставщика OLE DB](../data/oledb/creating-an-ole-db-provider.md)   
 [Ссылка на шаблоны потребителя OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)   
 [Ссылка на шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-reference.md)   
 [Примеры шаблонов OLE DB](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c)