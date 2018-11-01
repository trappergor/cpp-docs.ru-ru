---
title: Выборка данных
ms.date: 10/19/2018
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
ms.openlocfilehash: 441f036d1677806e81bc419ec6a45e810e63a34f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651923"
---
# <a name="fetching-data"></a>Выборка данных

После открытия источника данных, сеанс и объекты набора строк, можно извлечь данные. В зависимости от типа метода доступа, которую вы используете может потребоваться привязать столбцы.

## <a name="to-fetch-data"></a>Для выборки данных

1. Открыть набор строк, с помощью соответствующего **откройте** команды.

1. Если вы используете `CManualAccessor`, выполнить привязку выходных столбцов, если вы еще этого не сделали. Следующий пример взят из [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) образца. Чтобы привязать столбцы, вызовите `GetColumnInfo`, а затем создайте метод доступа с привязками, как показано в следующем примере:

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

1. Запись **хотя** цикла для извлечения данных. В этом же цикле вызовите `MoveNext` Чтобы переместить курсор и протестировать возвращают значение S_OK, как показано в следующем примере:

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. В рамках **хотя** цикла, можно извлекать данные в соответствии с используемым типом метода доступа.

   - Если вы используете [CAccessor](../../data/oledb/caccessor-class.md) класс, должен иметь запись пользователя, который содержит данные-члены. Для доступа к данным, используя эти элементы данных, как показано в следующем примере:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - Если вы используете `CDynamicAccessor` или `CDynamicParameterAccessor` класса, можно извлечь данные с помощью функций доступа `GetValue` и `GetColumn`, как показано в следующем примере. Если вы хотите определить тип данных, вы используете, используйте `GetType`.

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

   - Если вы используете `CManualAccessor`, необходимо указать собственные элементы данных, привязать их и доступ к ним напрямую, как показано в следующем примере:

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>См. также

[Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)
