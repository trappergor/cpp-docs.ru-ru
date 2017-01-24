---
title: "Шаблоны, атрибуты и другие реализации OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "шаблоны OLE DB"
  - "шаблоны OLE DB, сведения о шаблонах OLE DB"
  - "OLE DB, реализации"
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Шаблоны, атрибуты и другие реализации OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Шаблоны OLE DB в библиотеке  
 Шаблоны OLE DB, входящие в состав библиотеки активных шаблонов ATL, обеспечивают простоту использования высокопроизводительной технологии работы с базами данных OLE DB с помощью классов, в которых реализуется большинство часто используемых интерфейсов OLE DB.  Вместе с библиотекой шаблонов поставляется мастер, предназначенный для создания приложений OLE DB начального уровня.  
  
 Библиотека шаблонов состоит из двух частей:  
  
-   **Шаблоны объектов\-получателей OLE DB**. Предназначены для реализации клиентских приложений OLE DB \(получателей\).  
  
-   **Шаблоны поставщиков OLE DB**. Предназначены для реализации серверных приложений OLE DB \(поставщиков\).  
  
 Для работы с шаблонами OLE DB требуются навыки работы с шаблонами C\+\+, моделью COM и интерфейсами OLE DB.  Дополнительные сведения об OLE DB см. в [справочнике программиста OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx).  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Шаблоны объектов\-получателей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) или [Шаблоны поставщиков OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
-   Создание [объекта\-получателя OLE DB](../../data/oledb/creating-an-ole-db-consumer.md) или [поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md).  
  
-   Список [классов объектов\-получателей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) или [классов поставщиков OLE DB](../../data/oledb/ole-db-provider-templates-reference.md).  
  
-   Список [примеров шаблонов OLE DB](http://msdn.microsoft.com/ru-ru/08958863-0b5f-41ad-ae99-fca7440c553c).  
  
-   [Справочник программиста OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx) \(в пакете [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]\).  
  
## Атрибуты OLE DB  
 [Атрибуты объекта\-получателя OLE DB](../../windows/ole-db-consumer-attributes.md) используются для создания объектов получателей OLE DB.  С помощью атрибутов OLE DB в программу добавляется основанный на [шаблонах объектов\-получателей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) код, который используется для создания рабочих объектов\-получателей и поставщиков OLE DB.  Чтобы реализовать функции, не поддерживаемые этими атрибутами, используйте совместно с ними шаблоны OLE DB.  
  
## Классы OLE DB в библиотеке MFC  
 В библиотеке MFC представлен один класс [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), который предназначен для отображения записей базы данных на элементах управления.  Отображение реализуется с помощью представления формы, которое непосредственно связано с объектом `CRowset` и отображает поля объекта `CRowset` на элементах управления шаблона диалогового окна.  Кроме того, в библиотеке предусмотрены используемые по умолчанию реализации перехода к первой, последней, следующей или предыдущей записи, а также интерфейс для обновления отображаемой в представлении записи.  Для получения дополнительной информации см. `COleDBRecordView`.  
  
## Интерфейсы OLE DB в пакете SDK  
 Если шаблоны OLE DB не поддерживают функции OLE DB, следует использовать сами интерфейсы OLE DB.  Дополнительные сведения см. в [справочнике программиста OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx) в пакете [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
## См. также  
 [Программирование объектов OLE DB](../../data/oledb/ole-db-programming.md)   
 [Общие сведения о программировании OLE DB](../../data/oledb/ole-db-programming-overview.md)