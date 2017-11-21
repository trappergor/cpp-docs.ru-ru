---
title: "Запишите просмотреть код, создаваемый мастером приложений (доступ к данным MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9475dd6192eb6bc1abd00e3614c18482be415c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>Код представления записей, создаваемый мастером приложений (доступ к данным MFC)
[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) представление переопределений `OnInitialUpdate` и `OnGetRecordset` функции-члены. После того как платформа создает фрейм окна, документ и представление, она вызывает `OnInitialUpdate` для инициализации представления. `OnInitialUpdate`Получает указатель на набор записей из документа. Вызов базового класса [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функция открывает набор записей. В следующем коде показан этот процесс для `CRecordView`:  
  
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