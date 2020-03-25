---
title: Поддержка закладок поставщиками
ms.date: 11/04/2016
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
ms.openlocfilehash: e8ea949653c7e62f39ab9d1b181c419cf51fe3cb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209837"
---
# <a name="provider-support-for-bookmarks"></a>Поддержка закладок поставщиками

Пример в этом разделе добавляет интерфейс `IRowsetLocate` в класс `CCustomRowset`. Почти во всех случаях начинается Добавление интерфейса в существующий COM-объект. Затем можно протестировать его, добавив дополнительные вызовы из шаблонов потребителей. В примере показано, как:

- Добавление интерфейса к поставщику.

- Динамически определяются столбцы, возвращаемые потребителю.

- Добавление поддержки закладок.

Интерфейс `IRowsetLocate` наследует от интерфейса `IRowset` . Чтобы добавить интерфейс `IRowsetLocate`, наследуйте `CCustomRowset` из [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).

Добавление интерфейса `IRowsetLocate` немного отличается от большинства интерфейсов. Чтобы сделать таблицы VTABLE выставляемыми, шаблоны поставщика OLE DB имеют параметр шаблона для работы с производным интерфейсом. В следующем коде показан новый список наследования:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

// CCustomRowset
class CCustomRowset : public CRowsetImpl< CCustomRowset,
      CTextData, CCustomCommand, CAtlArray<CTextData>,
      CSimpleRow,
          IRowsetLocateImpl<CCustomRowset, IRowsetLocate>>
```

Будут добавлены четвертый, пятый и шестой параметры. В этом примере используются значения по умолчанию для четвертого и пятого параметров, но в качестве шестого параметра указывается `IRowsetLocateImpl`. `IRowsetLocateImpl` — это OLE DB класс шаблона, принимающий два параметра шаблона: они применяют интерфейс `IRowsetLocate` к классу `CCustomRowset`. Чтобы добавить большинство интерфейсов, можно пропустить этот шаг и перейти к следующему. Таким образом должны обрабатываться только интерфейсы `IRowsetLocate` и `IRowsetScroll`.

Затем необходимо указать `CCustomRowset` вызывать `QueryInterface` для интерфейса `IRowsetLocate`. Добавьте строку `COM_INTERFACE_ENTRY(IRowsetLocate)` на карту. Карта интерфейса для `CCustomRowset` должна выглядеть, как показано в следующем коде:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

typedef CRowsetImpl< CCustomRowset, CTextData, CCustomCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CCustomRowset, IRowsetLocate>> _RowsetBaseClass;

BEGIN_COM_MAP(CCustomRowset)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Также необходимо подключить карту к классу `CRowsetImpl`. Добавьте в COM_INTERFACE_ENTRY_CHAIN макрос для подключения к `CRowsetImpl` карте. Кроме того, создайте typedef с именем `RowsetBaseClass`, состоящий из сведений о наследовании. Это определение типа является произвольным и может быть пропущено.

Наконец, обработайте вызов `IColumnsInfo::GetColumnsInfo`. Для этого обычно используются макросы PROVIDER_COLUMN_ENTRY. Однако потребителю может потребоваться использовать закладки. Необходимо иметь возможность изменить столбцы, возвращаемые поставщиком, в зависимости от того, запрашивает ли потребитель закладку.

Чтобы обрабатывался вызов `IColumnsInfo::GetColumnsInfo`, удалите карту PROVIDER_COLUMN в классе `CTextData`. Макрос PROVIDER_COLUMN_MAP определяет функцию `GetColumnInfo`. Определите собственную функцию `GetColumnInfo`. Объявление функции должно выглядеть следующим образом:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H

class CTextData
{
   ...
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!
   static ATLCOLUMNINFO* GetColumnInfo(CCustomRowset* pThis,
        ULONG* pcCols);
   static ATLCOLUMNINFO* GetColumnInfo(CCustomCommand* pThis,
        ULONG* pcCols);
...
};
```

Затем реализуйте функцию `GetColumnInfo` в *пользовательском*файле RS. cpp следующим образом:

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp

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

ATLCOLUMNINFO* CTextData::GetColumnInfo(CCustomCommand* pThis,
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

`GetColumnInfo` сначала проверяет, задано ли свойство с именем `DBPROP_IRowsetLocate`. OLE DB имеет свойства для каждого из дополнительных интерфейсов из объекта набора строк. Если потребитель хочет использовать один из этих необязательных интерфейсов, он устанавливает для свойства значение true. Затем поставщик может проверить это свойство и предпринять на нем специальные действия.

В реализации вы получаете свойство, используя указатель на объект Command. Указатель `pThis` представляет набор строк или класс команд. Так как вы используете здесь шаблоны, необходимо передать это значение в виде указателя **void** , иначе код не будет компилироваться.

Укажите статический массив для хранения сведений о столбце. Если потребителю не нужен столбец Bookmark, то запись в массиве теряется. Этот массив можно динамически выделить, но его необходимо уничтожить должным образом. В этом примере определяются и используются макросы ADD_COLUMN_ENTRY и ADD_COLUMN_ENTRY_EX для вставки данных в массив. Макросы можно добавить в *пользовательскую*RS. H файл, как показано в следующем коде:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

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

Чтобы протестировать код в потребителе, необходимо внести несколько изменений в обработчик `OnRun`. Первое изменение функции заключается в том, что вы добавляете код для добавления свойства в набор свойств. Код задает для свойства `DBPROP_IRowsetLocate` значение true, тем самым указывая поставщику, что вам нужен столбец закладки. Код обработчика `OnRun` должен выглядеть следующим образом:

```cpp
//////////////////////////////////////////////////////////////////////
// TestProv Consumer Application in TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession   session;

   if (source.Open("Custom.Custom.1", NULL, NULL, NULL,
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

Цикл **while** содержит код для вызова метода `Compare` в интерфейсе `IRowsetLocate`. Код должен всегда проходить, так как сравниваются одни и те же закладки. Кроме того, сохраните одну закладку во временной переменной, чтобы ее можно было использовать после завершения цикла **while** , чтобы вызвать функцию `MoveToBookmark` в шаблонах потребителей. Функция `MoveToBookmark` вызывает метод `GetRowsAt` в `IRowsetLocate`.

Также необходимо обновить запись пользователя в потребителе. Добавьте запись в класс для управления закладкой и записью в COLUMN_MAP:

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

После обновления кода вы сможете создать и выполнить поставщик с интерфейсом `IRowsetLocate`.

## <a name="see-also"></a>См. также раздел

[Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)
