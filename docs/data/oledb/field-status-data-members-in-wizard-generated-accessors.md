---
title: "Поля членов данных состояния в мастере создания методов доступа | Документы Microsoft"
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
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 663b26d77138af60d13c3caf24960730a324131e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Статус поля элементов данных в мастере создания методов доступа
При использовании мастера потребителя ATL OLE DB для создания потребителя мастер создает член данных в классе записи пользователя для каждого поля, заданные в сопоставлении столбцов. Каждый элемент данных имеет тип `DWORD` и содержит значение состояния, отвечающее соответствующему полю.  
  
 Например, для элемента данных *m_OwnerID*, мастер создает дополнительный член данных для поля состояния (*dwOwnerIDStatus*) и еще один для длины полей (*dwOwnerIDLength*). Он также генерирует сопоставление столбцов с `COLUMN_ENTRY_LENGTH_STATUS` записей.  
  
 Это показано в следующем коде:  
  
```  
[db_source("insert connection string")]  
[db_command(" \  
   SELECT \  
      Au_ID, \  
      Author, \  
      `Year Born`, \  
      FROM Authors")]  
  
class CAuthors  
{  
public:  
  
   // The following wizard-generated data members contain status   
   // values for the corresponding fields in the column map. You   
   // can use these values to hold NULL values that the database   
   // returns or to hold error information when the compiler returns   
   // errors. See "Field Status Data Members in Wizard-Generated   
   // Accessors" in the Visual C++ documentation for more information   
   // on using these fields.  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
  
   // The following wizard-generated data members contain length  
   // values for the corresponding fields in the column map.  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
  
BEGIN_COLUMN_MAP(CAuthorsAccessor)  
   COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)  
END_COLUMN_MAP()  
  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
      pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
   }  
};  
```  
  
> [!NOTE]
>  Если вы изменяете класс записей пользователя или создаете собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.  
  
 Значения состояния можно использовать для целей отладки. Если код, созданный мастером потребителя ATL OLE DB создает ошибки компиляции, такие как **DB_S_ERRORSOCCURRED** или **DB_E_ERRORSOCCURRED**, необходимо просмотреть текущие значения поля состояния члены данных. Те, которые имеют ненулевое значение соответствуют столбцам, вызывающим ошибки.  
  
 Значения состояния может использоваться для задания значения NULL для определенного поля. Это помогает в случаях, когда необходимо отличать друг значение поля как NULL, а не с нуля. Это вы можете решить, является ли NULL допустимым значением или специальное значение и решить, как он должен обрабатывать приложение. OLE DB определяет **DBSTATUS_S_ISNULL** как правильным указания универсального значения NULL. Если потребитель считывает данные и имеет значение null, в поле состояния имеет значение **DBSTATUS_S_ISNULL**. Если необходимо установить значение NULL, потребитель задает значение состояния **DBSTATUS_S_ISNULL** перед вызовом поставщика.  
  
 Затем откройте Oledb.h и поиск **DBSTATUSENUM**. Можно противопоставить числовое значение ненулевое значение состояния для **DBSTATUSENUM** значений перечисления. Если имя перечисления не достаточно выяснить, почему, см. в разделе «Status» в разделе «Значения привязки данных» [Руководство программиста OLE DB](http://go.microsoft.com/fwlink/p/?linkid=121548). Этот раздел содержит таблицы значений состояния, используемые при получении или установке данных. Дополнительные сведения о значениях длины см. в разделе «Длина» в одном разделе.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>Определение длины или состояния столбца  
 Можно получить длину столбца переменной длины или состояния столбца (для проверки **DBSTATUS_S_ISNULL**, например):  
  
-   Чтобы получить длину, используйте `COLUMN_ENTRY_LENGTH` макрос.  
  
-   Чтобы получить состояние, используйте `COLUMN_ENTRY_STATUS` макрос.  
  
-   Чтобы это сделать, используйте `COLUMN_ENTRY_LENGTH_STATUS`, как показано ниже.  
  
```  
class CProducts  
{  
public:  
   char      szName[40];  
   long      nNameLength;  
   DBSTATUS   nNameStatus;  
  
BEGIN_COLUMN_MAP(CProducts)  
// Bind the column to CProducts.m_ProductName.  
// nOrdinal is zero-based, so the column number of m_ProductName is 1.  
   COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CProducts >> product;  
  
product.Open(session, "Product");  

while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
 При использовании `CDynamicAccessor`, длина и состояние привязываются автоматически. Чтобы получить значения длины и состояния, используйте `GetLength` и **GetStatus** функции-члены.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)