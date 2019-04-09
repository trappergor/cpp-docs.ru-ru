---
title: Динамическое связывание столбцов в поставщике
ms.date: 11/04/2016
helpviewer_keywords:
- columns [C++], dynamic column binding
- dynamic column binding
- providers [C++], dynamic column binding
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
ms.openlocfilehash: 3c66cf58ce1f8b83b2b3308c8dabba6cf8cdf0ef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033856"
---
# <a name="dynamically-binding-columns-in-your-provider"></a>Динамическое связывание столбцов в поставщике

Убедитесь, что вам действительно необходим динамическая привязка столбцов. Так как он может понадобиться:

- Во время компиляции не определены столбцы набора строк.

- Чтобы помочь элемент, такой как закладка, которая добавляет столбцы.

## <a name="to-implement-dynamic-column-binding"></a>Для реализации динамическая привязка столбцов

1. Удалите все `PROVIDER_COLUMN_MAP`s из кода.

1. В записи пользователя (структуру) добавьте следующее объявление:

    ```cpp
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
    ```

1. Реализуйте `GetColumnInfo` функции. Эта функция определяет схему хранения информации. Может потребоваться получить свойства или другие сведения для этой функции. Может потребоваться создать макрос, аналогичную [COLUMN_ENTRY](../../data/oledb/column-entry.md) макрос для добавления своих собственных сведений.

   В следующем примере показан `GetColumnInfo` функции.

    ```cpp
    // Check the property flag for bookmarks, if it is set, set the zero
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
          ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), DBTYPE_BYTES,
             0, 0, GUID_NULL, CAgentMan, dwBookmark, DBCOLUMNFLAGS_ISBOOKMARK)
          ulCols++;
       }
    }

    // Next, set up the other columns.
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

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)