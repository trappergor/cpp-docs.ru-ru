---
title: "Динамично определяемые столбцы, возвращенные объекту-получателю | Microsoft Docs"
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
  - "закладки [C++], динамически определяемые столбцы"
  - "динамически определяемые столбцы [C++]"
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Динамично определяемые столбцы, возвращенные объекту-получателю
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Макрос PROVIDER\_COLUMN\_ENTRY обычно обрабатывает вызов **IColumnsInfo::GetColumnsInfo**.  Однако, поскольку объект\-получатель может выбрать использование закладок, поставщик обязан вносить изменения в возвращенные столбы в зависимости от запроса объекта\-получателя.  
  
 Для обработки вызова **IColumnsInfo::GetColumnsInfo** удалите макрос PROVIDER\_COLUMN\_MAP, который определяет функцию `GetColumnInfo`, и в пользовательской записи MyProviderRS.h `CAgentMan` замените его на определение собственной функции `GetColumnInfo`.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 Далее установите функцию `GetColumnInfo` в MyProviderRS.cpp в соответствии с ниже приведенным кодом.  
  
 `GetColumnInfo` проверяет наличие установки свойства OLE DB **DBPROP\_BOOKMARKS**.  Для получения этого свойства `pRowset` используется указатель в объекте набора строк `GetColumnInfo`.  Указатель `pThis` представляет класс, создающий набор строк, которые формируют класс, где сохраняется сопоставление свойств.  `GetColumnInfo` приводит указатель `pThis` к указателю `RMyProviderRowset`.  
  
 Чтобы проверить свойство **DBPROP\_BOOKMARKS**, `GetColumnInfo` используйте интерфейс `IRowsetInfo`, делая вызов `QueryInterface` интерфейса `pRowset`.  В качестве дополнительно варианта можно использовать метод ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md).  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spRowsetProps)  
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
 В этом примере показан статический массив, который содержит данные столбцов.  Если потребитель не использует столбец закладки, запись в массиве остается незаполненной.  Для того чтобы управлять данными, создайте два массива с макросами: ADD\_COLUMN\_ENTRY и ADD\_COLUMN\_ENTRY\_EX.  ADD\_COLUMN\_ENTRY\_EX является дополнительным параметром, `flags`, который необходим для назначения столбца закладки.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision,   
scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type,   
precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
 В функции `GetColumnInfo` макрос закладки используется следующим образом:  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 Теперь можно скомпилировать и запустить расширенный интерфейс поставщика.  Для того чтобы протестировать поставщика, измените тестовый объект\-получатель в соответствии с разделом [Внедрение простого объекта\-получателя](../../data/oledb/implementing-a-simple-consumer.md).  Запустите тестовый объект\-получатель вместе с поставщиком.  При нажатии кнопки **Запустить** в диалоговом окне **Тестовый объект\-получатель**, убедитесь в том, чтобы строки, направляемые поставщиком объекту\-получателю, были правильными.  
  
## См. также  
 [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)