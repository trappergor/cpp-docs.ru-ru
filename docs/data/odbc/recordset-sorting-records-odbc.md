---
title: 'Набор записей: Сортировка записей (ODBC) | Документы Microsoft'
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
ms.openlocfilehash: ddb92016b7b911fc86f2feab27a698ce7fa55c45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090277"
---
# <a name="recordset-sorting-records-odbc"></a>Набор записей. Сортировка записей (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 В этом разделе объясняется, как проводить сортировку набора записей. Можно указать один или несколько столбцов в качестве основания для сортировки и указании возрастающем или убывающем порядке (`ASC` или **DESC**; `ASC` значение по умолчанию) для каждого выбранного столбца. Например если выбрать два столбца записи отсортированы сначала первый столбец с именем, а затем второй столбец с именем. SQL **ORDER BY** предложение определяет порядок сортировки. Если платформа добавляет **ORDER BY** запросом предложение to SQL набора записей, выбор упорядочение элементов управления предложения.  
  
 Необходимо установить порядок сортировки набора записей после создания объекта, но перед вызовом его **откройте** функция-член (или перед вызовом метода **Requery** функции-члена для существующего объекта набора записей которого **откройте** функция-член вызван ранее).  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Чтобы указать порядок сортировки для объекта набора записей  
  
1.  Создайте новый объект набора записей (или вызовите **Requery** существующего объекта).  
  
2.  Значение объекта [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) члена данных.  
  
     Сортировка представляет собой строку, завершающуюся значением null. Он содержит содержимое **ORDER BY** предложения, но не ключевое слово **ORDER BY**. Например используйте:  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  Задайте параметры, необходимые, например фильтр, режим блокировки или параметры.  
  
4.  Вызовите **откройте** для нового объекта (или **Requery** для существующего объекта).  
  
 Выбранные записи сортируются в соответствии. Например для сортировки набора записей студентов в убывающем порядке по фамилии, а затем по имени, выполните следующее:  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 Набор записей, содержащий записи студентов, затем отсортированы в порядке убывания (от я до А) по фамилии, по имени.  
  
> [!NOTE]
>  Если требуется переопределить строку SQL набора записей по умолчанию, передав строку SQL для **откройте**, sort не задано, если Настраиваемая строка имеет **ORDER BY** предложения.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)