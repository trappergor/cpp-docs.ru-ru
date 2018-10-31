---
title: Динамично определяемые столбцы, возвращенные объекту-получателю | Документация Майкрософт
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2149c50f4dc8880e20bff2401adf0db46ad6588
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216504"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Динамично определяемые столбцы, возвращенные объекту-получателю

PROVIDER_COLUMN_ENTRY в обычном режиме обработки `IColumnsInfo::GetColumnsInfo` вызова. Тем не менее так как объект-получатель может предпочесть использование закладок, поставщик должен иметь возможность изменять столбцы, возвращаемые в зависимости от того, является ли потребитель запрашивает закладку.

Для обработки `IColumnsInfo::GetColumnsInfo` вызова, удалите PROVIDER_COLUMN_MAP, которая определяет функцию `GetColumnInfo`, из `CAgentMan` пользователя записи в CustomRS.h и замените его определение собственных `GetColumnInfo` функции:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
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

Далее, реализовать `GetColumnInfo` работать в *Custom*RS.cpp, как показано в следующем коде.

`GetColumnInfo` проверяет, чтобы проверить, если свойство OLE DB `DBPROP_BOOKMARKS` имеет значение. Чтобы получить значение свойства `GetColumnInfo` использует указатель (`pRowset`) объекта набора строк. `pThis` Указатель представляет класс, который создал набор строк, который является классом, где хранится в схеме сопоставления свойств. `GetColumnInfo` приводит `pThis` указатель на `RCustomRowset` указатель.

Для проверки `DBPROP_BOOKMARKS` свойство, `GetColumnInfo` использует `IRowsetInfo` интерфейс, который можно получить, вызвав `QueryInterface` на `pRowset` интерфейс. Кроме того, можно использовать ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) метод вместо этого.

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
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

В этом примере использует статического массива для хранения данных столбца. Если потребитель не столбец закладки, одна запись в массиве не используется. Обрабатывать эти данные, создайте два массива макроса: ADD_COLUMN_ENTRY и ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX дополнительным параметром, *флаги*, который требуется при указании столбца закладки.

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

Теперь можно скомпилировать и запустить усовершенствованный поставщик. Чтобы протестировать поставщика, измените тестовый объект-получатель, как описано в [реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md). Выполните тестовый объект-получатель для поставщика. Убедитесь, что тестовый объект-получатель получает соответствующие строки от поставщика, при нажатии кнопки **запуска** кнопку **тестовый объект-получатель** диалоговое окно.

## <a name="see-also"></a>См. также

[Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
