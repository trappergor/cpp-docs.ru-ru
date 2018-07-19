---
title: Отношения между объектами MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef6a9e605948fac4f31338f87b4d00bbaa8712f4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931656"
---
# <a name="relationships-among-mfc-objects"></a>Отношения между объектами MFC
Для облегчения восприятия процесс создания документов и представлений в перспективе, рассмотрите возможность выполняющейся программе: документ, фрейм окна, содержащий представление и представление, связанное с документом.  
  
-   Документа хранит список представлений этого документа и указатель в шаблоне документа, в котором был создан документ.  
  
-   Представление сохраняет указатель на документ и является дочерним элементом родительского окна фрейма.  
  
-   Окно фрейма документа сохраняет указатель на его текущее активное представление.  
  
-   Шаблон документа хранит список его открытых документов.  
  
-   Приложение хранит список ее шаблонов документов.  
  
-   Windows сохраняет сведения о всех открытых окон, он может отправлять сообщения на них.  
  
 Эти связи задаются во время создания документов и представлений. В следующей таблице показаны объекты в работающей программе уровень доступа других объектов. Любой объект можно получить указатель на объект приложения путем вызова глобальной функции [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).  
  
### <a name="gaining-access-to-other-objects-in-your-application"></a>Получение доступа к другим объектам в приложении  
  
|Из объекта|Как получить доступ к другим объектам|  
|-----------------|---------------------------------|  
|Document|Используйте [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) и [GetNextView](../mfc/reference/cdocument-class.md#getnextview) для доступа к списку представление документа.<br /><br /> Вызовите [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) для получения шаблона документа.|  
|Просмотр|Вызовите [GetDocument](../mfc/reference/cview-class.md#getdocument) получить документ.<br /><br /> Вызовите [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) для получения фрейм окна.|  
|Окно фрейма документа|Вызовите [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) для получения текущего представления.<br /><br /> Вызовите [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) получить документ, присоединенный к текущему представлению.|  
|Окно области MDI|Вызовите [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) для получения текущего активного [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).|  
  
 Как правило окно фрейма имеет одно представление, но в некоторых случаях окно фрейма как окна разделителей содержит несколько представлений. Окна фрейма сохраняет указатель на текущий активный представления; указатель обновляется каждый раз, когда активируется другое представление.  
  
> [!NOTE]
>  Указатель на главное окно хранится в [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) переменной-члена объекта приложения. Вызов `OnFileNew` в переопределении `InitInstance` функцию-член `CWinApp` задает *m_pMainWnd* для вас. Если вы не вызываете `OnFileNew`, необходимо задать значение переменной в `InitInstance` самостоятельно. (SDI COM-компонент (сервера) приложения не могут устанавливать переменной Если в командной строке параметры/Embedding.) Обратите внимание, что *m_pMainWnd* является членом класса `CWinThread` вместо `CWinApp`.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Создание шаблонов документов](../mfc/document-template-creation.md)   
 [Создание документа или представления](../mfc/document-view-creation.md)   
 [Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

