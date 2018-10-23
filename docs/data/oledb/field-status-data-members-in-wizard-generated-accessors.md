---
title: Поле членов данных состояния в мастере создания методов доступа | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ce3ad819b6e22bfb5c760849e5f3fdf85bd4f7bc
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49809100"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Статус поля элементов данных в мастере создания методов доступа

При использовании Мастер потребителя ATL OLE DB для создания получателя, мастер формирует данные-член в класс записей пользователя для каждого поля, указанного в сопоставлении столбцов. Каждый элемент данных имеет тип `DWORD` и содержит значение состояния, соответствующее соответствующему полю.  
  
Например, для элемента данных *m_OwnerID*, мастер создает дополнительный член данных для поля состояния (*dwOwnerIDStatus*) и еще один — для длины полей (*dwOwnerIDLength*). Она также создает схему столбца со COLUMN_ENTRY_LENGTH_STATUS элементами.  
  
Это показано в следующем коде:  
  
```cpp  
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
> Если вы изменяете класс записей пользователя или создаете собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.  
  
Значения состояния можно использовать для отладки. Если код, сгенерированный Мастер потребителя ATL OLE DB создает ошибки компиляции, например DB_S_ERRORSOCCURRED или DB_E_ERRORSOCCURRED, вы сначала просмотрите текущие значения членов данных состояния поля. Те, которые имеют ненулевые значения соответствуют столбцам, вызывающим ошибки.  
  
Значения состояния также можно присвоить значение NULL для определенного поля. Это помогает в случаях, когда необходимо отличать друг значение поля как значение NULL, а не с нуля. Это можно решить, является ли NULL допустимым значением или специальное значение, а также решить, каким образом приложение необходимо обработать его. OLE DB определяет DBSTATUS_S_ISNULL как правильные средства, указав универсальный значение NULL. Если потребитель считывает данные и имеет значение null, в поле состояния устанавливается в значение DBSTATUS_S_ISNULL. Если необходимо установить значение NULL, потребитель задает значение состояния DBSTATUS_S_ISNULL перед вызовом поставщика.  
  
Затем откройте Oledb.h и выполните поиск DBSTATUSENUM. Затем можно сопоставить численного значения перечисления DBSTATUSENUM ненулевое значение состояния. Если имя перечисления не достаточно сказать, что не так, см. в разделе «Состояние» в разделе «Значения привязки данных» [Руководство программиста OLE DB](/previous-versions/windows/desktop/ms713643). Этот раздел содержит таблицы значений состояния, используемый при получении или задании данных. Сведения о значениях длины см. в разделе «Длина» в одном разделе.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>Получение длины или состояния столбца  

Можно получить длину столбца переменной длины или изменении состояния столбца (например проверки DBSTATUS_S_ISNULL):  
  
- Чтобы получить длину, используйте column_entry_length-макрос.  
  
- Чтобы получить состояние, используйте column_entry_status-макрос.  
  
- Чтобы получить оба, используйте COLUMN_ENTRY_LENGTH_STATUS, как показано ниже.  
  
```cpp  
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
  
При использовании `CDynamicAccessor`, длина и состояние привязываются автоматически. Чтобы получить значения длины и состояния, используйте `GetLength` и `GetStatus` функций-членов.  
  
## <a name="see-also"></a>См. также  

[Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)