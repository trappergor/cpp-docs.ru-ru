---
title: "Классы, создаваемые мастером объекта-получателя | Microsoft Docs"
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
  - "введенные атрибутом классы и методы"
  - "классы и методы, создаваемые мастером"
  - "потребители OLE DB, создаваемые мастером классы и методы"
  - "командные классы (потребитель OLE DB)"
  - "классы [C++], создаваемые мастером потребители OLE DB"
  - "классы и методы, создаваемые мастером потребителя"
  - "классы записей пользователя (потребитель OLE DB)"
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы, создаваемые мастером объекта-получателя
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При создании потребителя с помощью мастера потребителя ATL OLE DB вы можете выбрать использование шаблонов OLE DB или атрибутов OLE DB. В обоих случаях мастер создает класс команд и класс записей пользователя. В классе команд содержится код для открытия источника данных и набора строк, указанных в мастере. Класс записей пользователя содержит сопоставление столбцов для выбранной таблицы базы данных. Однако созданный код в каждом случае отличается.  
  
-   Если вы выбираете потребителя на основе шаблонов, мастер создает класс команд и класс записей пользователя. Класс команд будет иметь имя, указанное вами в поле "Класс" мастера \(например, `CProducts`\), а класс записей пользователя получит имя в форме "*ИмяКласса*Accessor" \(например, `CProductsAccessor`\). Оба класса находятся в файле заголовка потребителя.  
  
-   При выборе потребителя на основе атрибутов класс записей пользователя будет иметь имя в форме "\_*ИмяКласса*Accessor" и будет внедренным. То есть в текстовом редакторе вы сможете просматривать только класс команд; класс записей пользователя вы сможете просматривать только как внедренный код. Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
 В следующих примерах с помощью класса команд, созданного в таблице Products базы данных Northwind, демонстрируется код создаваемого мастером потребителя для класса команд и класса записей пользователя.  
  
## Классы записей пользователя на основе шаблонов  
 При создании потребителя OLE DB с помощью шаблонов OLE DB \(а не атрибутов OLE DB\) мастер создает код, как описано в этом разделе.  
  
### Элементы данных столбцов  
 Первая часть класса записей пользователя включает объявления элементов данных и элементы данных состояния и длины для каждого столбца с привязкой к данным. Сведения об этих элементах данных см. в разделе [Элементы данных состояния поля в создаваемых мастером методах доступа](../Topic/Field%20Status%20Data%20Members%20in%20Wizard-Generated%20Accessors.md).  
  
> [!NOTE]
>  Если вы изменяете класс записей пользователя или создаете собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.  
  
> [!NOTE]
>  Мастер потребителя ATL OLE DB использует тип **DB\_NUMERIC** для привязки числовых типов данных. Ранее он использовал **DBTYPE\_VARNUMERIC** \(формат которого описывался типом **DB\_VARNUMERIC**; см. Oledb.h\). Если потребители создаются без помощи мастера, рекомендуется использовать **DB\_NUMERIC**.  
  
```  
// Products.H : Declaration of the CProducts class class CProductsAccessor { public: // Column data members: LONG m_ProductID; TCHAR m_ProductName[41]; LONG m_SupplierID; LONG m_CategoryID; TCHAR m_QuantityPerUnit[21]; CURRENCY m_UnitPrice; SHORT m_UnitsInStock; SHORT m_UnitsOnOrder; SHORT m_ReorderLevel; VARIANT_BOOL m_Discontinued; // Column status data members: DBSTATUS m_dwProductIDStatus; DBSTATUS m_dwProductNameStatus; DBSTATUS m_dwSupplierIDStatus; DBSTATUS m_dwCategoryIDStatus; DBSTATUS m_dwQuantityPerUnitStatus; DBSTATUS m_dwUnitPriceStatus; DBSTATUS m_dwUnitsInStockStatus; DBSTATUS m_dwUnitsOnOrderStatus; DBSTATUS m_dwReorderLevelStatus; DBSTATUS m_dwDiscontinuedStatus; // Column length data members: DBLENGTH m_dwProductIDLength; DBLENGTH m_dwProductNameLength; DBLENGTH m_dwSupplierIDLength; DBLENGTH m_dwCategoryIDLength; DBLENGTH m_dwQuantityPerUnitLength; DBLENGTH m_dwUnitPriceLength; DBLENGTH m_dwUnitsInStockLength; DBLENGTH m_dwUnitsOnOrderLength; DBLENGTH m_dwReorderLevelLength; DBLENGTH m_dwDiscontinuedLength;  
```  
  
### Свойства набора строк  
 Далее мастер задает свойства набора строк. Если в мастере потребителя ATL OLE DB вы выбрали **Изменить**, **Вставить** или **Удалить**, здесь задаются соответствующие свойства \(свойство DBPROP\_IRowsetChange всегда задается, а затем одно или несколько свойств DBPROPVAL\_UP\_CHANGE, DBPROPVAL\_UP\_INSERT или DBPROPVAL\_UP\_DELETE соответственно\).  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet) { pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE); }  
```  
  
### Класс команд или таблиц  
 Если вы указали класс команд, мастер объявляет класс команд; для кода на основе шаблонов команда выглядит следующим образом:  
  
```  
DEFINE_COMMAND_EX(CProductsAccessor, L" \ SELECT \ ProductID, \ ProductName, \ SupplierID, \ CategoryID, \ QuantityPerUnit, \ UnitPrice, \ UnitsInStock, \ UnitsOnOrder, \ ReorderLevel, \ Discontinued \ FROM dbo.Products")  
```  
  
### Сопоставление столбцов  
 Затем мастер создает привязки столбцов или сопоставление столбцов. Для устранения некоторых проблем с поставщиками следующий код может привязывать столбцы в порядке, отличном от сообщаемого поставщиком.  
  
```  
BEGIN_COLUMN_MAP(CProductsAccessor) COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus) COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus) COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus) COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus) COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus) _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus)) COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus) COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus) COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus) _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus)) END_COLUMN_MAP() };  
```  
  
### Объявление класса  
 Наконец, мастер создает объявление класса команд, например следующим образом:  
  
```  
class CProducts : public CCommand<CAccessor<CProductsAccessor> >  
```  
  
## Классы записей пользователя, внедряемые атрибутами  
 Если вы создаете потребителя OLE DB с помощью атрибутов базы данных \([db\_command](../../windows/db-command.md) или [db\_table](../../windows/db-table.md)\), эти атрибуты внедряют класс записей пользователя с именем в форме "\_*ИмяКласса*Accessor". Например, если класс команд назван `COrders`, класс записей пользователя получит имя `_COrdersAccessor`. Хотя класс записей пользователя отображается в представлении классов, дважды щелкнув его кнопкой мыши, вы перейдете вместо него в класс команд или таблиц в файле заголовка. В таких случаях вы можете просмотреть фактическое объявление класса записей пользователя только путем просмотра кода, внедренного атрибутами.  
  
 При добавлении или переопределении методов в потребителях на основе атрибутов могут возникать определенные сложности. Например, если вы добавите конструктор `_COrdersAccessor` в объявление `COrders`, то заметите, что в действительности конструктор добавляется во внедренный класс `COrdersAccessor`. Такой конструктор может инициализировать столбцы или параметры, но вы не сможете создать таким образом конструктор копий, поскольку он не может напрямую создавать экземпляр объекта `COrdersAccessor`. Если нужен конструктор \(или другой метод\) непосредственно в классе `COrders`, рекомендуется определить новый класс, производный от `COrders`, и добавить в него необходимые методы.  
  
 В следующем примере мастер создает объявление класса `COrders`, но класс записей пользователя `COrdersAccessor` не появляется, поскольку его вводит атрибут.  
  
```  
#define _ATL_ATTRIBUTES #include <atlbase.h> #include <atldbcli.h> [ db_source(L"your connection string"), db_command(L"Select ShipName from Orders;") ] class COrders { public: // COrders()            // incorrect constructor name _COrdersAccessor()      // correct constructor name { } [db_column(1) ] TCHAR m_ShipName[41]; };  
```  
  
 Объявление внедренного класса команд выглядит следующим образом:  
  
```  
class CProducts : public CCommand<CAccessor<_CProductsAccessor> >  
```  
  
 Большая часть внедренного кода аналогична версии на основе шаблона. Основные различия — во внедренных методах, которые описаны в разделе [Методы, создаваемые мастером потребителя](../Topic/Consumer%20Wizard-Generated%20Methods.md).  
  
 Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
## См. также  
 [Создание объекта\-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)