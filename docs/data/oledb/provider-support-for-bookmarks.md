---
title: "Поддержка закладок поставщиками | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "закладки, OLE DB"
  - "IRowsetLocate - класс"
  - "IRowsetLocate - класс, поддержка закладок поставщиками"
  - "шаблоны поставщика OLE DB, закладки"
  - "поставщики OLE DB, поддержка закладок"
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Поддержка закладок поставщиками
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В примере данного раздела интерфейс `IRowsetLocate` добавляется к классу `CMyProviderRowset`.  Практически во всех случаях работа начинается с добавления интерфейса в существующий COM\-объект.  Затем можно его протестировать, добавив дополнительные вызовы из шаблонов потребителя.  В следующем примере показано выполнение следующих действий.  
  
-   Добавление интерфейса к поставщику.  
  
-   Динамическое определение столбцов, возвращаемых потребителю.  
  
-   Добавление поддержки закладок.  
  
 Интерфейс `IRowsetLocate` наследует от интерфейса `IRowset`.  Чтобы добавить интерфейс `IRowsetLocate`, необходимо выполнить наследование `CMyProviderRowset` от [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).  
  
 Добавление интерфейса `IRowsetLocate` отличается от большинства других интерфейсов.  Для выравнивания виртуальных таблиц VTABLE шаблоны поставщика OLE DB содержат параметр шаблона для обработки производного интерфейса.  В следующем коде показан новый список наследования.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> >  
```  
  
 Четвертый, пятый и шестой параметры также добавляются.  В этом примере для четвертого и пятого параметров используются значения по умолчанию, однако в качестве шестого параметра указывается `IRowsetLocateImpl`.  `IRowsetLocateImpl` является классом шаблонов OLE DB, который принимает два параметра шаблонов: это привязывает интерфейс `IRowsetLocate` к классу `CMyProviderRowset`.  Для большинства интерфейсов этот шаг можно пропустить и перейти к следующему.  Только интерфейсы `IRowsetLocate` и `IRowsetScroll` должны обрабатываться таким образом.  
  
 Затем необходимо указать классу `CMyProviderRowset` вызвать метод `QueryInterface` для интерфейса `IRowsetLocate`.  Добавьте строку `COM_INTERFACE_ENTRY(IRowsetLocate)` в схему.  Схема интерфейса для `CMyProviderRowset` должна выглядеть, как показано в следующем коде.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> > _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Также необходимо связать эту схему с классом `CRowsetImpl`.  Добавьте в схему `CRowsetImpl` макрос COM\_INTERFACE\_ENTRY\_CHAIN для связывания.  Также следует создать определение типа \(typedef\) `RowsetBaseClass`, состоящее из сведений о наследовании.  Это определение типа является необязательным и может быть пропущено.  
  
 Затем следует обработать вызов **IColumnsInfo::GetColumnsInfo**.  Для этого, как правило, используется макрос PROVIDER\_COLUMN\_ENTRY.  Однако потребителю может потребоваться использовать закладки.  Необходимо иметь возможность изменить столбцы, возвращаемые поставщиком, в зависимости от того, запрашивает ли потребитель закладку.  
  
 Чтобы обработать вызов **IColumnsInfo::GetColumnsInfo**, удалите схему **PROVIDER\_COLUMN** в классе `CTextData`.  Макрос PROVIDER\_COLUMN\_MAP определяет функцию `GetColumnInfo`.  Следует определить собственную функцию `GetColumnInfo`.  Объявление функции должно выглядеть следующим образом:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 Затем реализуйте функцию `GetColumnInfo` в файле MyProviderRS.cpp, как показано ниже.  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
template <class TInterface>  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   CComQIPtr<TInterface> spProps = pPropsUnk;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spProps)  
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   // Check the property flag for bookmarks, if it is set, set the   
// zero ordinal entry in the column map with the bookmark   
// information.  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,   
                     sizeof(DWORD), DBTYPE_BYTES,  
            0, 0, GUID_NULL, CAgentMan, dwBookmark,         
                        DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
  
   }  
  
   // Next set the other columns up.  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,   
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)  
   ulCols++;  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,  
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
     ULONG* pcCols)  
{  
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),  
        pcCols);  
}  
  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)  
{  
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);  
}  
```  
  
 Сначала `GetColumnInfo` проверяет, задано ли свойство **DBPROP\_IRowsetLocate**.  OLE DB содержит свойства для каждого дополнительного интерфейса, не принадлежащего объекту набора строк.  Если потребителю необходимо использовать один из этих дополнительных интерфейсов, он устанавливает для этого свойства значение "true".  После этого поставщик может проверить это свойство и в зависимости от полученного результата выполнить определенное действие.  
  
 В своей реализации это свойство можно получить с помощью указателя на объект команды.  Указатель `pThis` представляет набор строк или класс команды.  Поскольку применяются шаблоны, необходимо передать указатель как `void`. В противном случае не удастся скомпилировать код.  
  
 Укажите статический массив, который должен содержать сведения о столбцах.  Если потребитель не создает закладку для столбца, запись в массиве тратится впустую.  Можно динамически подстраивать структуру массива, однако может потребоваться, чтобы он был уничтожен надлежащим образом.  В этом примере макросы ADD\_COLUMN\_ENTRY и ADD\_COLUMN\_ENTRY\_EX определяются и используются для вставки сведений в массив.  Можно добавить макросы в файл MyProviderRS.H, как показано в следующем коде.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
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
  
 Чтобы проверить код в потребителе, необходимо внести некоторые изменения в обработчик `OnRun`.  Первое изменение функции — это написание кода для добавления свойства в набор свойств.  Код устанавливает для свойства **DBPROP\_IRowsetLocate** значение "true", тем самым сообщая поставщику, что следует создать закладку для столбца.  Код обработчика `OnRun` должен выглядеть следующим образом:  
  
```  
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
          NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   propset.AddProperty(DBPROP_IRowsetLocate, true);  
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),   
          &propset) != S_OK)  
      return;  
  
   CBookmark<4> tempBookmark;  
   ULONG ulCount=0;  
   while (table.MoveNext() == S_OK)  
   {  
  
      DBCOMPARE compare;  
      if (ulCount == 2)  
         tempBookmark = table.bookmark;  
      HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,  
                 &compare);  
      if (FAILED(hr))  
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);  
      else  
         _ASSERTE(compare == DBCOMPARE_EQ);  
  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
      ulCount++;  
   }  
  
   table.MoveToBookmark(tempBookmark);  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 Цикл while содержит код для вызова метода `Compare` в интерфейсе `IRowsetLocate`.  Код должен постоянно передаваться, поскольку выполняется сравнение одних и тех же закладок.  Также следует сохранить одну закладку во временной переменной, чтобы ее можно было использовать по окончании цикла while для вызова функции `MoveToBookmark` в шаблонах потребителя.  Функция `MoveToBookmark` вызывает метод `GetRowsAt` в интерфейсе `IRowsetLocate`.  
  
 Также необходимо обновить запись пользователя в потребителе.  Добавьте запись в класс для обработки закладки и запись в **COLUMN\_MAP**:  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
class CProvider  
{  
// Attributes  
public:  
   CBookmark<4>    bookmark;  // Add this line  
   char   szCommand[16];  
   char   szText[256];  
  
   // Binding Maps  
BEGIN_ACCESSOR_MAP(CProvider, 1)  
   BEGIN_ACCESSOR(0, true)   // auto accessor  
      BOOKMARK_ENTRY(bookmark)  // Add this line  
      COLUMN_ENTRY(1, szField1)  
      COLUMN_ENTRY(2, szField2)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 После обновления кода можно построить и выполнить поставщик с интерфейсом `IRowsetLocate`.  
  
## См. также  
 [Дополнительные способы использования поставщика](../Topic/Advanced%20Provider%20Techniques.md)