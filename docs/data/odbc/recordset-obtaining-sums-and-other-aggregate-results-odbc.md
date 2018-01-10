---
title: "Набор записей: Определение сумм и других статистических результатов (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4753193789c95b726a8770cef9a153b041fa762c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Набор записей. Определение сумм и других статистических результатов (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 В этом разделе описывается процесс получения статистических данных с использованием следующих [SQL](../../data/odbc/sql.md) ключевые слова:  
  
-   **Сумма** вычисляет сумму значений в столбце с числовым типом данных.  
  
-   **MIN** извлекает наименьшее значение в столбце с числовым типом данных.  
  
-   **MAX** извлекает наибольшее значение в столбце с числовым типом данных.  
  
-   **AVG** вычисляет среднее значение всех значений в столбце с числовым типом данных.  
  
-   **ЧИСЛО** подсчитывается количество записей в любой тип данных столбца.  
  
 Чтобы получить статистические сведения о записях в источнике данных, а не для получения записей из источника данных используются эти функции SQL. Набор записей обычно состоит из одной записи (если все столбцы являются статистическими выражениями), содержащий значение. (Может существовать несколько записей при использовании **GROUP BY** предложение.) Это значение является результатом вычисления или извлечения, выполненного с помощью функции SQL.  
  
> [!TIP]
>  Чтобы добавить SQL **GROUP BY** предложение (и, возможно, **HAVING** предложение) для инструкции SQL, добавьте его в конец **m_strFilter**. Пример:  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 Можно ограничить количество записей, используемых для получения статистических данных путем фильтрации и сортировки столбцов.  
  
> [!CAUTION]
>  Некоторые операторы статистической обработки возвращают различные типы данных из столбцов, по которым они статистической обработке.  
  
-   **Сумма** и **AVG** может вернуть Следующий больший тип данных (например, вызов с `int` возвращает **ДЛИННЫЕ** или **двойные**).  
  
-   **ЧИСЛО** обычно возвращает **ДЛИННЫЕ** независимо от целевой тип столбца.  
  
-   **MAX** и **MIN** возвращают один и тот же тип данных столбцов, их вычисления.  
  
     Например **добавить класс** мастер создает `long` `m_lSales` для размещения столбца Sales, но необходимо заменить с `double m_dblSumSales` элемент данных, чтобы вместить итоговый результат. См. следующий пример.  
  
#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Для получения результата статистической обработки набора записей  
  
1.  Создать набор записей, как описано в [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) содержит столбцы, из которых требуется получения статистических данных.  
  
2.  Изменить [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) функции для набора записей. Замените строку, представляющую имя столбца (второй аргумент [RFX](../../data/odbc/record-field-exchange-using-rfx.md) вызовов функций) со строкой, представляющей агрегатную функцию для столбца. Например замените:  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     с:  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  Откройте набор записей. Результат операции статистической обработки, остаются в `m_dblSumSales`.  
  
> [!NOTE]
>  Фактически мастер назначает имена членов данных без венгерская префиксов. Например, мастер выдаст `m_Sales` для столбца Sales, а не `m_lSales` имя, использованное ранее для иллюстрации.  
  
 Если вы используете [CRecordView](../../mfc/reference/crecordview-class.md) класса для просмотра данных, необходимо изменить вызов функции DDX для отображения значений новых элементов данных; таким образом, изменив ее из:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 В:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей. Порядок выборки записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)