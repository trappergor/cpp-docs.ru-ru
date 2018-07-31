---
title: Установка свойств в поставщике | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7fedb77b6ede8d9fa843e7e7cdd344e03efecede
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337902"
---
# <a name="setting-properties-in-your-provider"></a>Установка свойств в поставщике
Для свойства, которое требуется найти группы свойств и идентификатор свойства. Дополнительные сведения см. в разделе [свойства OLE DB](https://msdn.microsoft.com/library/ms722734.aspx) в *Справочник программиста OLE DB по*.  
  
 В код поставщика, созданного мастером содержатся в схеме сопоставления свойств, соответствующей той группе свойство. Имя группы свойств обычно соответствует имени объекта. Свойства команд и наборов строк можно найти в команду или набор строк; Свойства данных источника и инициализации можно найти в объекте источника данных.  
  
 В сопоставлении свойств, добавьте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) макрос. PROPERTY_INFO_ENTRY_EX принимает четыре параметра:  
  
-   Идентификатор свойства, соответствующий свойству. Необходимо удалить первые семь символов («DBPROP_») в начале имени свойства. Например, если вы хотите добавить `DBPROP_MAXROWS`, передайте `MAXROWS` как первый элемент. Если это пользовательское свойство, передать имя полный идентификатор GUID (например, `DBMYPROP_MYPROPERTY`).  
  
-   Тип variant свойства (в [свойства OLE DB](https://msdn.microsoft.com/library/ms722734.aspx) в *Справочник программиста OLE DB по*). Введите тип (например, VT_BOOL или VT_I2) VT_, соответствующий типу данных.  
  
-   Флаги, указывающие, является ли свойство для чтения и записи и группы, к которой он принадлежит. Например следующий код указывает свойство чтения/записи, входящей в группу строк:  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   Базовое значение свойства. Это может быть `VARIANT_FALSE` логическое значение типа, или нуль для целого типа, например. Свойство имеет это значение, если он изменяется.  
  
    > [!NOTE]
    >  Некоторые свойства подключением и связанных с другими свойствами, например закладки или обновление. Когда потребитель устанавливает одно свойство в значение true, можно также задавать другое свойство. Шаблоны поставщика OLE DB поддерживает это через метод [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Свойства, обрабатывается поставщиками Microsoft OLE DB  
 Поставщики данных Microsoft OLE DB не учитывать следующие свойства OLE DB:  
  
-   `DBPROP_MAXROWS` работает только для поставщиков только для чтения (то есть свойство DBPROP_IRowsetChange DBPROP_IRowsetUpdate которых и false); в противном случае это свойство не поддерживается.  
  
-   `DBPROP_MAXPENDINGROWS` учитывается; Поставщик устанавливает собственное ограничение.  
  
-   `DBPROP_MAXOPENROWS` учитывается; Поставщик устанавливает собственное ограничение.  
  
-   `DBPROP_CANHOLDROWS` учитывается; Поставщик устанавливает собственное ограничение.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)