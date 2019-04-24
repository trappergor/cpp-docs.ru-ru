---
title: Заполнение списка из второго набора записей (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
ms.openlocfilehash: 9428f8a59dca021a1bd0e00a7970f4d19bab46be
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030507"
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>Заполнение списка из второго набора записей (доступ к данным MFC)

По умолчанию представление записей связано с одним объектом набора записей, поля которого сопоставляются элементам управления представления записей. Иногда может возникнуть необходимость поместить элемента управления списком или полем со списком в представление записей и заполнить его значениями из второго объекта набора записей. Можно использовать поле со списком для выбора новой категории сведений для отображения в представлении записей пользователя. В этом разделе объясняется, как и когда это можно сделать.

> [!TIP]
>  Имейте в виду, что заполнение поля со списком или списка из источника данных может быть медленным. Учитывайте этот факт при заполнении элемента управления данными из набора с большим числом записей.

Модель для этого раздела состоит из основного набора записей для заполнения элементов управления формы, и вторичного набора для заполнения списка или поля со списком. При выборе строки в списке вызывает повторный запрос первого набора записей на основании выбранной программе. Следующая процедура использует поле со списком, но применяется одинаково и к списку.

#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>Чтобы заполнить поле со списком или список из второго набора записей

1. Создание объекта набора записей ([CRecordset](../mfc/reference/crecordset-class.md).

1. Получить указатель на [CComboBox](../mfc/reference/ccombobox-class.md) объект для элемента управления полем со списком.

1. Очистите поле со списком от любого предыдущего содержимого.

1. Перемещение по всем записям в наборе записей, вызов [CComboBox::AddString](../mfc/reference/ccombobox-class.md#addstring) для каждой строки из текущей записи, вы хотите добавить в поле со списком.

1. Инициализируйте выбор элементов в поле со списком.

```cpp
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

[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)