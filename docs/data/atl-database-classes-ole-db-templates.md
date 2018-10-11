---
title: Классы баз данных ATL (шаблоны OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6defe70a018fe954a0daa2d1a4b49142a9a37884
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081948"
---
# <a name="atl-database-classes-ole-db-templates"></a>Классы баз данных библиотеки ATL (шаблоны OLE DB)

Корпорация Майкрософт предоставляет несколько реализаций OLE DB, набор COM-интерфейсов, обеспечивающих унифицированный доступ к данным в различных источниках и форматах.  OLE DB обычно не используется; Данный документ предназначен для разработчиков, которые Поддержка устаревшего кода. Новые приложения должны использовать ODBC для подключения к источникам данных SQL.
  
Шаблоны OLE DB являются шаблонами C++ ATL, которые упрощают технологии баз данных OLE DB для использования, предоставляя классов, реализующих многие часто используемые интерфейсы OLE DB.  
  
Библиотека шаблонов состоит из двух частей:  
  
- [Шаблоны потребителей OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) используется для реализации приложения клиент (потребитель) OLE DB.  
  
- [Шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) используется для реализации приложения сервера (поставщик) OLE DB.  
  
Кроме того [атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md) предоставляют удобный способ создания потребителей OLE DB. Эти атрибуты OLE DB внедряют код, основанный на шаблонах потребителей OLE DB для создания рабочих потребителей OLE DB.  
  
Обратите внимание, что библиотека MFC содержит один класс [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), которая отображает записи базы данных в элементах управления. Представление — представление формы, который напрямую подключен к `CRowset` и отображает поля `CRowset` в элементах управления шаблона диалогового окна.  
  
Дополнительные сведения см. в разделе [OLE DB программирования](../data/oledb/ole-db-programming.md) и [Руководство программиста OLE DB](/previous-versions/windows/desktop/ms713643).  
  
## <a name="see-also"></a>См. также  

[Создание объекта-получателя OLE DB](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[Создание поставщика OLE DB](../data/oledb/creating-an-ole-db-provider.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Ссылка на шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Примеры шаблонов OLE DB](https://github.com/Microsoft/VCSamples)