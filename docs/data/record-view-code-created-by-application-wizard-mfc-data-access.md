---
title: Код представления записей, создаваемый мастером приложений (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: 69bebe978d03e5777f20765ac0bcf9a344f69320
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209161"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Код представления записей, создаваемый мастером приложений (доступ к данным MFC)

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) переопределяет `OnInitialUpdate` представления и `OnGetRecordset` функции элементов. После того как платформа создает фрейм окна, документ и представление, она вызывает `OnInitialUpdate` для инициализации представления. `OnInitialUpdate` получает указатель на набор записей из документа. Вызов базового класса, функция [CView:: онинитиалупдате](../mfc/reference/cview-class.md#oninitialupdate) открывает набор записей. Следующий код демонстрирует этот процесс для `CRecordView`:

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

При открытии набора записей происходит выбор записей. [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) делает первую запись текущей записью, а DDX перемещает данные из элементов данных полей набора записей в соответствующие элементы управления формы в представлении. Дополнительные сведения о RFX см. в статье [Обмен полями записей (RFX)](../data/odbc/record-field-exchange-rfx.md). Дополнительные сведения об DDX см [обмен данными окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Сведения о процессе создания документа/представления см. в разделе [Использование классов для написания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

> [!NOTE]
>  Следует предоставить конечным пользователям возможность обновления элементов управления представления записи из набора записей. Без этой возможности, если пользователь изменяет значение в элементе управления на недопустимое значение, пользователь может застрять на текущей записи. Чтобы обновить элементы управления, вызовите функцию-член `CWnd` [упдатедата](../mfc/reference/cwnd-class.md#updatedata) с параметром false.

## <a name="see-also"></a>См. также раздел

[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)
