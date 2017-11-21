---
title: "Установка свойств в поставщике | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 80b82e1fb69200f45716b2ad62a44160862f7d08
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setting-properties-in-your-provider"></a>Установка свойств в поставщике
Для свойства, которое требуется найти группы свойств и идентификатор свойства. Дополнительные сведения см. в разделе [свойства OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) в *Справочник программиста OLE DB*.  
  
 В код поставщика, сформированной мастером найдите сопоставление свойства, соответствующее группе свойств. Имя группы свойств обычно соответствует имени объекта. Свойства команд и наборов строк можно найти в команду или строк; источник и инициализации свойства данных можно найти в объекте источника данных.  
  
 В сопоставлении свойств, добавление [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) макрос. PROPERTY_INFO_ENTRY_EX принимает четыре параметра:  
  
-   Идентификатор свойства, соответствующий свойству. Первые семь символов («DBPROP_») необходимо удалить из начала имени свойства. Например, если вы хотите добавить **DBPROP_MAXROWS**, передайте `MAXROWS` как первый элемент. Если это пользовательское свойство, передать имя полный идентификатор GUID (например, `DBMYPROP_MYPROPERTY`).  
  
-   Тип variant свойства (в [свойства OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) в *Справочник программиста OLE DB*). Введите **VT_** типа (например, `VT_BOOL` или `VT_I2`), соответствующий типу данных.  
  
-   Флаги, указывающие, является ли свойство для чтения и записи и группы, к которой он принадлежит. Например следующий код определяет свойство чтения/записи, относящиеся к группе строк:  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   Базовое значение свойства. Это может быть **VARIANT_FALSE** логическое значение типа или нулевое значение для целочисленного типа, например. Свойство имеет это значение, если оно изменяется.  
  
    > [!NOTE]
    >  Некоторые свойства соединены (сцеплены) с другими свойствами, например закладки или обновление. Когда потребитель устанавливает одно свойство в значение true, может также устанавливаться другого свойства. Шаблоны поставщика OLE DB поддерживают такую через метод [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Свойства игнорируются поставщиками Microsoft OLE DB  
 Поставщики данных Microsoft OLE DB не учитывать следующие свойства OLE DB:  
  
-   **Свойство DBPROP_MAXROWS** работает только для поставщиков, доступных только для чтения (т.е., где DBPROP_IRowsetChange и DBPROP_IRowsetUpdate — false); в противном случае это свойство не поддерживается.  
  
-   **DBPROP_MAXPENDINGROWS** игнорируется; Поставщик устанавливает собственное ограничение.  
  
-   **DBPROP_MAXOPENROWS** игнорируется; Поставщик устанавливает собственное ограничение.  
  
-   **DBPROP_CANHOLDROWS** игнорируется; Поставщик устанавливает собственное ограничение.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)