---
title: Запишите просмотреть код, создаваемый мастером приложений (доступ к данным MFC) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15355d156b3c85c8f99ba638b30f831da96686af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Код представления записей, создаваемый мастером приложений (доступ к данным MFC)
[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) представление переопределений `OnInitialUpdate` и `OnGetRecordset` функции-члены. После того как платформа создает фрейм окна, документ и представление, она вызывает `OnInitialUpdate` для инициализации представления. `OnInitialUpdate` Получает указатель на набор записей из документа. Вызов базового класса [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функция открывает набор записей. В следующем коде показан этот процесс для `CRecordView`:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 При открытии набора записей происходит выбор записей. [CRecordset::Open](../mfc/reference/crecordset-class.md#open) делает первую запись текущей записью и DDX перемещает данные из элементов данных полей набора записей в соответствующий элементы управления формы в представлении. Дополнительные сведения об RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md). Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Сведения о процессе создания документов и представлений см. в разделе [использование классов для написания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
> [!NOTE]
>  Следует предоставить конечным пользователям возможность обновления элементов управления представления записи из набора записей. Без этой возможности, если пользователь изменяет значение в элементе управления на недопустимое значение, пользователь может застрять на текущей записи. Чтобы обновить элементы управления, следует вызвать `CWnd` функции-члена [UpdateData](../mfc/reference/cwnd-class.md#updatedata) с параметром **FALSE**.  
  
## <a name="see-also"></a>См. также  
 [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)