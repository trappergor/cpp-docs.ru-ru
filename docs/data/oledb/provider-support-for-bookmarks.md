---
title: Поддержка закладок поставщиками | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b16605b8cd0b5855d7a6cc1f5ceac9f46ad495f4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337635"
---
# <a name="provider-support-for-bookmarks"></a>Поддержка закладок поставщиками
В примере в этом разделе добавляется `IRowsetLocate` интерфейс `CMyProviderRowset` класса. Практически во всех случаях начинается с добавления к существующему объекту COM интерфейс. Затем можно проверить его, добавив дополнительные вызовы с шаблонами объекта-получателя. В примере показано, как:  
  
-   Добавление интерфейса в поставщик.  
  
-   Динамически Определите столбцы, возвращаемые для потребителя.  
  
-   Добавление поддержки закладок.  
  
 Интерфейс `IRowsetLocate` наследует от интерфейса `IRowset`. Чтобы добавить `IRowsetLocate` интерфейсом, наследуют `CMyProviderRowset` из [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).  
  
 Добавление `IRowsetLocate` интерфейс немного отличается от большинства других интерфейсов. Чтобы сделать файл vtable на строку вверх, OLE DB шаблонов поставщика имеют параметр шаблона для обработки производного интерфейса. В следующем коде показано новый список наследования:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>>  
```  
  
 Четвертый, пятый и шестой параметры также добавляются. В этом примере используются значения по умолчанию для четвертый и пятый параметры указывают, но `IRowsetLocateImpl` как шестой параметр. `IRowsetLocateImpl` Это класс шаблона OLE DB, который принимает два параметра шаблона: эти подключения `IRowsetLocate` интерфейс `CMyProviderRowset` класса. Для большинства интерфейсов, можно пропустить этот шаг и перейти к следующей. Только `IRowsetLocate` и `IRowsetScroll` интерфейсы должны обрабатываться таким образом.  
  
 Затем необходимо указать `CMyProviderRowset` для вызова `QueryInterface` для `IRowsetLocate` интерфейс. Добавьте строку `COM_INTERFACE_ENTRY(IRowsetLocate)` на карту. Схему интерфейсов для `CMyProviderRowset` должен выглядеть, как показано в следующем коде:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>> _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Необходимо также связать в `CRowsetImpl` класса. Добавьте в макросе COM_INTERFACE_ENTRY_CHAIN может подключить `CRowsetImpl` карты. Кроме того, создайте typedef вызывается `RowsetBaseClass` , состоящий из со сведениями о наследовании. Это определение типа является произвольным и можно игнорировать.  
  
 Наконец, обрабатывать `IColumnsInfo::GetColumnsInfo` вызова. PROVIDER_COLUMN_ENTRY в используется обычно для этого. Тем не менее потребитель может потребоваться использовать закладки. Необходимо изменить столбцы, возвращаемые поставщиком, в зависимости от того, является ли потребитель запрашивает закладку.  
  
 Для обработки `IColumnsInfo::GetColumnsInfo` вызова, удалите `PROVIDER_COLUMN` сопоставления в `CTextData` класса. Макрос PROVIDER_COLUMN_MAP определяет функцию `GetColumnInfo`. Необходимо определить свои собственные `GetColumnInfo` функции. Объявление функции должно выглядеть следующим образом:  
  
```cpp
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
  
 Затем запустите `GetColumnInfo` функции в файле MyProviderRS.cpp следующим образом:  
  
```cpp
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
  
 `GetColumnInfo` сначала проверяет ли свойство, называемую `DBPROP_IRowsetLocate` имеет значение. OLE DB содержит свойства для каждого дополнительного интерфейса, не объекта набора строк. Если потребителю необходимо использовать один из этих дополнительных интерфейсов, он присваивает свойству значение true. Поставщик можно проверить это свойство и выполнить специальные действия, на его основе.  
  
 В реализации получения свойства с помощью указателя на объект команды. `pThis` Указатель представляет класс набора или команды. Так как здесь используются шаблоны, необходимо передать его в качестве `void` указатель или код не компилируется.  
  
 Укажите статический массив, содержащий сведения о столбце. Если потребитель не столбец закладки, теряется запись в массиве. Вы можете динамически выделить этот массив, но необходимо обязательно уничтожить его должным образом. В этом примере определяет и использует макросы ADD_COLUMN_ENTRY и ADD_COLUMN_ENTRY_EX используется для вставки данных в массив. Макросы можно добавить в файл MyProviderRS.H, как показано в следующем коде:  
  
```cpp
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
  
 Чтобы проверить код в объекте-получателе, вам потребуется внести некоторые изменения, чтобы `OnRun` обработчика. Первое изменение функции — добавить код, чтобы добавить свойство в наборе свойств. В коде устанавливается `DBPROP_IRowsetLocate` присваивается значение true, тем самым сообщая поставщику, что необходимо сделать столбец закладки. `OnRun` Код обработчика должен выглядеть следующим образом:  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider>> table;  
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
  
 While содержит код для вызова `Compare` метод в `IRowsetLocate` интерфейс. Код, который у вас есть всегда должно передавать, так как при сравнении точное же закладки. Кроме того, сохранить одну закладку во временной переменной, таким образом, вы можете использовать после while окончании для вызова цикла `MoveToBookmark` функция в шаблонах потребителей. `MoveToBookmark` Вызовы функций `GetRowsAt` метод в `IRowsetLocate`.  
  
 Необходимо также обновить запись пользователя в объекте-получателе. Добавьте запись в класс для обработки закладки и запись в `COLUMN_MAP`:  
  
```cpp
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
  
 Когда вы обновили код, можно создавать и выполнять поставщик с `IRowsetLocate` интерфейс.  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)