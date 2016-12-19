---
title: "Выборка данных | Microsoft Docs"
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
  - "данные [C++], выборка"
  - "выборка"
  - "шаблоны потребителей OLE DB [C++], выборка данных"
  - "наборы строк [C++], выборка"
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Выборка данных
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

После открытия источника данных, сеанса и объектов набора строк можно производить выборку данных.  В зависимости от используемого типа метода доступа, возможно, понадобится провести привязку столбцов.  
  
### Чтобы произвести выборку данных, необходимо выполнить следующие действия  
  
1.  Откройте набор строк с помощью соответствующей команды **Открыть**.  
  
2.  Если используется метод доступа `CManualAccessor`, следует выполнить привязку выходных столбцов, если это еще не сделано.  Для привязки столбцов необходимо вызвать метод `GetColumnInfo` и создать метод доступа с привязками, как показано в следующем примере:  
  
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
  
3.  Добавьте цикл `while`, чтобы получить данные.  В цикле вызывайте метод `MoveNext`, чтобы передвигать курсор и проверять возвращаемое значение на равенство значению S\_OK, как показано в следующем примере:  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  В цикле `while` можно производить выборку данных в соответствии с используемым типом метода доступа.  
  
    -   Если используется класс [CAccessor](../Topic/CAccessor%20Class.md), необходимо наличие пользовательской записи, содержащей элементы данных.  Доступ к данным можно получить, используя эти элементы данных, как показано в следующем примере:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   Если используется класс `CDynamicAccessor` или `CDynamicParameterAccessor`, можно произвести выборку данных с помощью функций доступа `GetValue` и `GetColumn`, как показано в следующем примере.  Если требуется определить тип используемых данных, можно воспользоваться методом `GetType`.  
  
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
  
    -   Если используется класс `CManualAccessor`, необходимо указать собственные элементы данных, самостоятельно осуществить их привязку и обратиться к ним напрямую, как показано в следующем примере:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## См. также  
 [Работа с шаблонами объекта\-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)