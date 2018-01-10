---
title: "Шаблоны OLE DB, атрибуты и другие реализации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a859e455bb0c1569c401a865e9cfffbf6bdf2c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>Шаблоны, атрибуты и другие реализации OLE DB
## <a name="atl-ole-db-templates"></a>Шаблоны OLE DB ATL  
 Шаблоны OLE DB, которые являются частью библиотеки ATL (библиотеки ATL), упростить технологии высокой производительности баз данных OLE DB путем предоставления классов, реализующих многие часто используемые интерфейсы OLE DB. Вместе с этого шаблона библиотека включает поддержку мастера для создания начальных приложений OLE DB.  
  
 Библиотека шаблонов состоит из двух частей:  
  
-   **Шаблоны потребителей OLE DB** используется для реализации приложений OLE DB клиента (покупатели).  
  
-   **Шаблоны поставщика OLE DB** используется для реализации приложения OLE DB для сервера (поставщик).  
  
 Чтобы использовать шаблоны OLE DB, необходимо иметь навыки работы с шаблонами C++, COM и интерфейсами OLE DB. Если вы не знакомы с OLE DB, см. раздел [Справочник программиста OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx).  
  
 Дополнительные сведения можно сделать следующее.  
  
-   Ознакомьтесь с разделами о [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) или [шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
-   Создание [потребителя OLE DB](../../data/oledb/creating-an-ole-db-consumer.md) или [поставщик OLE DB](../../data/oledb/creating-an-ole-db-provider.md).  
  
-   Просмотреть список [классы потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) или [классы поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md).  
  
-   Просмотреть список [примеры шаблонов OLE DB](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c).  
  
-   В разделе [справочника программиста OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx) (в Windows SDK).  
  
## <a name="ole-db-attributes"></a>Атрибуты OLE DB  
 [Атрибуты потребителя OLE DB](../../windows/ole-db-consumer-attributes.md) предоставляют удобный способ создания потребителей OLE DB. Атрибуты OLE DB вводят кода на основе [шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) для создания рабочих потребителей OLE DB и поставщики. Если необходимо указать функциональные возможности, не поддерживаемые атрибуты, можно использовать шаблоны OLE DB в сочетании с атрибутами в коде.  
  
## <a name="mfc-ole-db-classes"></a>Классы MFC OLE DB  
 В библиотеке MFC представлен один класс [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), которое отображает записи базы данных в элементах управления. Представление — это представление формы, непосредственно подключенные к `CRowset` и отображает свойства поля `CRowset` в элементах управления шаблона диалогового окна. Он также предоставляет реализацию по умолчанию для перемещения к первому следующего, предыдущего или последней записи и интерфейс для обновления записи в настоящее время для представления. Дополнительные сведения см. в разделе `COleDBRecordView`.  
  
## <a name="ole-db-sdk-interfaces"></a>Пакет SDK для интерфейсов OLE DB  
 В случаях, где шаблоны OLE DB не поддерживают функциональные возможности OLE DB необходимо использовать сами интерфейсы OLE DB. Дополнительные сведения см. в разделе [Справочник программиста OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Программирование объектов OLE DB](../../data/oledb/ole-db-programming.md)   
 [Общие сведения о программировании OLE DB](../../data/oledb/ole-db-programming-overview.md)