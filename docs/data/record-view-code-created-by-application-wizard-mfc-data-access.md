---
title: "Код представления записей, создаваемый мастером приложений (доступ к данным MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "мастера приложений [C++], код представления записей"
  - "представления записей, кода мастера приложений"
  - "представления записей, обновление элементов управления"
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Код представления записей, создаваемый мастером приложений (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) переопределяет представления функций\-членов `OnInitialUpdate` и `OnGetRecordset` .  После того как платформа создает фрейм окна, документ и представление, она вызывает `OnInitialUpdate` для инициализации представления.  `OnInitialUpdate` Получает указатель на набор записей из документа.  Вызов функции базового класса [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) открывает набор записей.  В следующем коде показан этот процесс для `CRecordView` — код для `CDaoRecordView` похож:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 При открытии набора записей происходит выбор записей.  [CRecordset::Open](../Topic/CRecordset::Open.md) или [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) делает первую запись текущей записью и DDX перемещает данные из данных полей элементов набора записей в соответствующий элементы управления формы в представлении.  Дополнительные сведения об RFX см [обмен полей записей \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  Дополнительные сведения об DDX см [обмен данными окон и проверка](../mfc/dialog-data-exchange-and-validation.md).  Дополнительные сведения о процессе создания документов и представлений см [использование классов для написания приложений для Windows](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md).  
  
> [!NOTE]
>  Следует предоставить конечным пользователям возможность обновления элементов управления представления записи из набора записей.  Без этой возможности, если пользователь изменяет значение в элементе управления на недопустимое значение, пользователь может застрять на текущей записи.  Чтобы обновить элементы управления, следует вызвать `CWnd` функцию\-члена [UpdateData](../Topic/CWnd::UpdateData.md) с параметром **FALSE**.  
  
## См. также  
 [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)