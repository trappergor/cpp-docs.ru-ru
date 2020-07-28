---
title: Выборка данных
ms.date: 10/19/2018
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
ms.openlocfilehash: 919eb059f5d3f29d491bf7a6598b0c77163bd783
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184648"
---
# <a name="fetching-data"></a>Выборка данных

После открытия объектов источника данных, сеанса и набора строк можно получить данные. В зависимости от типа метода доступа, который вы используете, может потребоваться привязать столбцы.

## <a name="to-fetch-data"></a>Выборка данных

1. Откройте набор строк с помощью соответствующей команды **Open** .

1. Если вы используете `CManualAccessor` , привяжите выходные столбцы, если это еще не сделано. Следующий пример взят из примера [дбвиевер](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) . Чтобы привязать столбцы, вызовите `GetColumnInfo` , а затем создайте метод доступа с привязками, как показано в следующем примере:

    ```cpp
    // From the DBViewer Sample CDBTreeView::OnQueryEdit
    // Get the column information
    ULONG ulColumns       = 0;
    DBCOLUMNINFO* pColumnInfo  = NULL;
    LPOLESTR pStrings      = NULL;
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);
    struct MYBIND* pBind = new MYBIND[ulColumns];
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);
    for (ULONG l=0; l<ulColumns; l++)
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);
    rs.Bind();
    ```

1. Напишите **`while`** цикл для получения данных. В цикле вызовите, `MoveNext` чтобы переместить курсор и проверить возвращаемое значение на S_OK, как показано в следующем примере:

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. В **`while`** цикле можно получить данные в соответствии с типом метода доступа.

   - При использовании класса [какцессор](../../data/oledb/caccessor-class.md) у вас должна быть запись пользователя, содержащая элементы данных. Доступ к данным можно получить с помощью этих элементов данных, как показано в следующем примере:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - При использовании `CDynamicAccessor` `CDynamicParameterAccessor` класса или можно получить данные с помощью функций доступа `GetValue` и `GetColumn` , как показано в следующем примере. Если вы хотите определить тип используемых данных, используйте `GetType` .

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the dynamic accessor functions to retrieve your data.

            ULONG ulColumns = rs.GetColumnCount();
            for (ULONG i=0; i<ulColumns; i++)
            {
                rs.GetValue(i);
            }
        }
        ```

   - При использовании `CManualAccessor` необходимо указать собственные элементы данных, привязать их самостоятельно и обращаться к ним напрямую, как показано в следующем примере:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами потребителей OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)
