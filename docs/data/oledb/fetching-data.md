---
title: "Выборка данных | Документы Microsoft"
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
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1741f761db47154e6b1e151c6a4a3fa9788e7ad2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="fetching-data"></a>Выборка данных
После открытия источника данных, сеанса и объектов набора строк можно производить выборку данных. В зависимости от типа доступа, которую вы используете может потребоваться для привязки столбцов.  
  
### <a name="to-fetch-data"></a>Для выборки данных  
  
1.  Откройте набор строк с помощью соответствующей **откройте** команды.  
  
2.  Если вы используете `CManualAccessor`, привязку выходных столбцов, если вы еще не выполнена. Для привязки столбцов необходимо вызвать `GetColumnInfo`и создать метод доступа с привязками, как показано в следующем примере:  
  
    ```  
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
  
3.  Запись `while` цикла для извлечения данных. В цикле, вызовите `MoveNext` переместить курсор и протестировать возвращают значение S_OK, как показано в следующем примере:  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  В пределах `while` цикла, можно извлекать данные в соответствии с используемым типом метода доступа.  
  
    -   Если вы используете [CAccessor](../../data/oledb/caccessor-class.md) класс, должен иметь запись пользователя, содержащей элементы данных. Для доступа к данным, используя эти элементы данных, как показано в следующем примере:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   Если вы используете `CDynamicAccessor` или `CDynamicParameterAccessor` класса, можно получать данные с помощью функций доступа `GetValue` и `GetColumn`, как показано в следующем примере. Если вы хотите определить тип данных используется, используйте `GetType`.  
  
        ```  
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
  
    -   Если вы используете `CManualAccessor`, необходимо указать собственные элементы данных, привязать их и доступа к ним напрямую, как показано в следующем примере:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)