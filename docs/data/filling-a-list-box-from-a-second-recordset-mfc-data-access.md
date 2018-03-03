---
title: "Заполнение списка из второго набора записей (доступ к данным MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6e411ebcf40099a2236048dd8f151b438fe5b947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>Заполнение списка из второго набора записей (доступ к данным MFC)
По умолчанию представление записей связано с одним объектом набора записей, поля которого сопоставляются элементам управления представления записей. Иногда может возникнуть необходимость поместить элемента управления списком или полем со списком в представление записей и заполнить его значениями из второго объекта набора записей. Можно использовать поле со списком для выбора новой категории сведений для отображения в представлении записей пользователя. В этом разделе объясняется, как и когда это можно сделать.  
  
> [!TIP]
>  Имейте в виду, что заполнение поля со списком или списка из источника данных может быть медленным. Учитывайте этот факт при заполнении элемента управления данными из набора с большим числом записей.  
  
 Модель для этого раздела состоит из основного набора записей для заполнения элементов управления формы, и вторичного набора для заполнения списка или поля со списком. При выборе строки в списке вызывает повторный запрос первого набора записей на основании выбранной программе. Следующая процедура использует поле со списком, но применяется одинаково и к списку.  
  
#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>Чтобы заполнить поле со списком или список из второго набора записей  
  
1.  Создание объекта набора записей ([CRecordset](../mfc/reference/crecordset-class.md).  
  
2.  Получение указателя на [CComboBox](../mfc/reference/ccombobox-class.md) объекта для элемента управления полем со списком.  
  
3.  Очистите поле со списком от любого предыдущего содержимого.  
  
4.  Перемещение по всем записям в наборе записей, вызов [CComboBox::AddString](../mfc/reference/ccombobox-class.md#addstring) для каждой строки из текущей записи, необходимо добавить в поле со списком.  
  
5.  Инициализируйте выбор элементов в поле со списком.  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
    // ...  
  
    // Fill the combo box with all of the courses  
    CENROLLDoc* pDoc = GetDocument();  
    if (!pDoc->m_courseSet.Open())  
        return;  
  
    // ...  
  
    m_ctlCourseList.ResetContent();  
    if (pDoc->m_courseSet.IsOpen())  
    {   
        while (!pDoc->m_courseSet.IsEOF() )  
        {  
            m_ctlCourseList.AddString(  
                pDoc->m_courseSet.m_CourseID);  
            pDoc->m_courseSet.MoveNext();  
        }  
    }  
    m_ctlCourseList.SetCurSel(0);  
}  
```  
  
 В этой функции используется второй набор записей, `m_courseSet`, который содержит записи по всем предлагаемым курсам и элемент управления `CComboBox` , `m_ctlCourseList`, который хранится в классе представления записей.  
  
 Функция получает `m_courseSet` из документа и открывает его. Затем она очищает `m_ctlCourseList` и совершается прокрутку по `m_courseSet`. Для каждой записи,  функция вызывает для поля со списком функцию-член `AddString`, чтобы добавить идентификатор курса из записи. И, наконец, код задает для поля со списком выбранный элемент.  
  
## <a name="see-also"></a>См. также  
 [Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)