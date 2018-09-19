---
title: 'Набор записей: Определение сумм и других статистических результатов (ODBC) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d78b6375736c35b7a1d49436c870d7f807f6c78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032371"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Набор записей. Определение сумм и других статистических результатов (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.  
  
В этом разделе объясняется, как для получения статистических данных с использованием следующих [SQL](../../data/odbc/sql.md) ключевые слова:  
  
- **Сумма** вычисляет сумму значений в столбце с числовым типом данных.  
  
- **MIN** извлекает наименьшее значение в столбце с числовым типом данных.  
  
- **MAX** извлекает наибольшее значение в столбце с числовым типом данных.  
  
- **AVG** вычисляет среднее значение всех значений в столбце с числовым типом данных.  
  
- **ЧИСЛО** подсчитывает количество записей в столбце любого типа данных.  
  
Чтобы получить статистические сведения о записях в источнике данных, а не для извлечения записей из источника данных, используйте эти функции SQL. Набор записей, обычно состоит из одной записи (если все столбцы имеют агрегатов), содержащий значение. (Может существовать несколько записей при использовании **GROUP BY** предложение.) Это значение является результатом вычисления или извлечения, выполненного с помощью функции SQL.  
  
> [!TIP]
>  Чтобы добавить SQL **GROUP BY** предложение (и, возможно, **HAVING** предложение) в инструкцию SQL, добавьте его в конец `m_strFilter`. Пример:  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
Можно ограничить количество записей, используемых для получения статистических данных путем фильтрации и сортировки столбцов.  
  
> [!CAUTION]
>  Некоторые операторы статистической обработки возвращают различные типы данных из столбцов, по которым они статистической обработке.  
  
- **Сумма** и **AVG** может вернуть Следующий больший тип данных (например, вызов метода с `int` возвращает **LONG** или **двойные**).  
  
- **ЧИСЛО** обычно возвращает **LONG** независимо от целевой тип столбца.  
  
- **MAX** и **MIN** возвращают один и тот же тип данных столбцов, их вычисления.  
  
     Например **Добавление класса** мастер создает `long` `m_lSales` в соответствии с столбца Sales, но вам необходимо заменить с `double m_dblSumSales` элемент данных для размещения на совокупный результат. См. следующий пример.  
  
#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Для получения результата статистической обработки набора записей  
  
1. Создать набор записей, как описано в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) содержащий столбцы, из которых для получения статистических данных.  
  
1. Изменить [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) функции для набора записей. Замените строку, представляющую имя столбца (второй аргумент [RFX](../../data/odbc/record-field-exchange-using-rfx.md) вызовы функций) со строкой, представляющей агрегатную функцию для столбца. Например замените:  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     на:  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
1. Откройте набор записей. Результат операции статистической обработки, остаются в `m_dblSumSales`.  
  
> [!NOTE]
>  Фактически мастер назначает имена членов данных венгерская префиксы отсутствуют. Например, мастер выдаст `m_Sales` для столбца Sales, а не `m_lSales` имя, используемое ранее для иллюстрации.  
  
Если вы используете [CRecordView](../../mfc/reference/crecordview-class.md) класса для просмотра данных, необходимо заменить вызов функции DDX для отображения значений новых элементов данных; таким образом, изменив его с:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
В:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## <a name="see-also"></a>См. также  

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Порядок выборки записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)