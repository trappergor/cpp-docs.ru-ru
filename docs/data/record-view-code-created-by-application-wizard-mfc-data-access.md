---
title: Код представления записей, создаваемый мастером приложений (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: 69481299980329b98e378f02e090670fa3d7ece2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376022"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Код представления записей, создаваемый мастером приложений (доступ к данным MFC)

Мастер `OnInitialUpdate` [приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) переопределяет функции представления и `OnGetRecordset` членов. После того как платформа создает фрейм окна, документ и представление, она вызывает `OnInitialUpdate` для инициализации представления. `OnInitialUpdate`получает указатель на рекорд, установленный из документа. Вызов в базовый класс [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функция открывает запись. Следующий код показывает этот `CRecordView`процесс для:

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

При открытии набора записей происходит выбор записей. [CRecordset::Open](../mfc/reference/crecordset-class.md#open) делает первую запись текущей записи, и DDX перемещает данные от полевых членов данных записи к соответствующим элементам управления формой в представлении. Для получения дополнительной информации о RFX, см [Record Field Exchange (RFX)](../data/odbc/record-field-exchange-rfx.md). Дополнительные сведения об DDX см [обмен данными окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Для получения информации о процессе создания документа/просмотра [см.](../mfc/using-the-classes-to-write-applications-for-windows.md)

> [!NOTE]
> Следует предоставить конечным пользователям возможность обновления элементов управления представления записи из набора записей. Без этой возможности, если пользователь изменяет значение в элементе управления на недопустимое значение, пользователь может застрять на текущей записи. Чтобы обновить элементы управления, вы называете функцию `CWnd` участника [UpdateData](../mfc/reference/cwnd-class.md#updatedata) с параметром FALSE.

## <a name="see-also"></a>См. также раздел

[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)
