---
title: Код представления записей, создаваемый мастером приложений (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: e25ca9cad1390dd11ab7328ffefed31badf6fc0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152687"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Код представления записей, создаваемый мастером приложений (доступ к данным MFC)

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) переопределяет представления `OnInitialUpdate` и `OnGetRecordset` функций-членов. После того как платформа создает фрейм окна, документ и представление, она вызывает `OnInitialUpdate` для инициализации представления. `OnInitialUpdate` Получает указатель на набор записей из документа. Вызов базового класса [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функция открывает набор записей. Ниже показан этот процесс для `CRecordView`:

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

При открытии набора записей происходит выбор записей. [CRecordset::Open](../mfc/reference/crecordset-class.md#open) делает первую запись текущей записью и DDX перемещает данные из поля элементов данных набора записей в соответствующие элементы управления формы в представлении. Дополнительные сведения о RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md). Дополнительные сведения об DDX см [обмен данными окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Сведения о процессе создания документов и представлений см. в разделе [использование классов для записи приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

> [!NOTE]
>  Следует предоставить конечным пользователям возможность обновления элементов управления представления записи из набора записей. Без этой возможности, если пользователь изменяет значение в элементе управления на недопустимое значение, пользователь может застрять на текущей записи. Чтобы обновить элементы управления, следует вызвать `CWnd` функция-член [UpdateData](../mfc/reference/cwnd-class.md#updatedata) со значением параметра равным FALSE.

## <a name="see-also"></a>См. также

[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)