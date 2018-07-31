---
title: 'Набор записей: Сортировка записей (ODBC) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c78603e12aec7653e7c5c62d9a0282241ccda99e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337834"
---
# <a name="recordset-sorting-records-odbc"></a>Набор записей. Сортировка записей (ODBC)
Этот раздел относится к классам ODBC библиотеки MFC.  
  
 В этом разделе объясняется, как проводить сортировку набора записей. Можно указать один или несколько столбцов, на котором основывается сортировки, и можно указать по возрастанию или убыванию (**ASC** или **DESC**; **ASC** используется по умолчанию) для каждого выбранного столбца. Например если указать два столбца, записи сортируются сначала в первом столбце с именем, а затем на второй столбец с именем. SQL **ORDER BY** предложение определяют порядок сортировки. Когда платформа добавляет **ORDER BY** запросить предложение to SQL набора записей, выделение упорядочение элементов управления предложение.  
  
 Необходимо установить порядок сортировки для набора записей, после создания объекта, но перед вызовом его `Open` функция-член (или перед вызовом метода `Requery` функция-член для существующего набора записей объекта, `Open` была функция-член вызван ранее).  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Чтобы задать порядок сортировки для объекта набора записей  
  
1.  Создайте новый объект набора записей (или вызовите `Requery` для существующего).  
  
2.  Установите для параметра объекта [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) элемент данных.  
  
     Сортировка — это строка, завершающаяся нулем. Он содержит содержимое **ORDER BY** предложение, но не ключевое слово **ORDER BY**. Например используйте:  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  Задайте другие параметры, необходимые, например фильтр, режим блокировки или параметры.  
  
4.  Вызовите `Open` для нового объекта (или `Requery` для существующего объекта).  
  
 Выбранные записи сортируются в соответствии. Например для сортировки набора записей учащихся в убывающем порядке по фамилии, а затем имя, сделайте следующее:  
  
```cpp  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 Набор записей содержит все записи учащихся, затем сортируются в нисходящем порядке (от Z до A) по фамилии, по имени.  
  
> [!NOTE]
>  Если вы решили переопределить строку SQL набора записей по умолчанию, передав строку SQL для `Open`, не устанавливайте сортировки, если Настраиваемая строка имеет **ORDER BY** предложение.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)