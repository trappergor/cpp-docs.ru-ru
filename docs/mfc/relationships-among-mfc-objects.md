---
title: Отношения между объектами MFC | Документация Майкрософт
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
ms.openlocfilehash: d2f42f754157a4fc2e3f3e1aa40f38477b982e16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372487"
---
# <a name="relationships-among-mfc-objects"></a>Отношения между объектами MFC

Для эффективного использования компьютерных процесс создания документов и представлений в перспективе, рассмотрите возможность выполняющейся программе: документ, фрейм окна, содержащий представление и представление, связанное с документом.

- Документа хранит список представления документа и указатель на шаблон документов, создавшей документ.

- Представление сохраняет указатель на документ и является дочерним элементом родительского фрейма окна.

- Окном фрейма документа сохраняет указатель на его текущее активное представление.

- Шаблон документа хранит список его открытых документов.

- Приложение хранит список его шаблонов документов.

- Windows сохраняет сведения о всех открытых окон, что он может отправлять сообщения на их.

Эти связи задаются во время создания документов и представлений. В следующей таблице показаны как доступ к другим объектам для объектов в выполняющейся программе. Любой объект можно получить указатель на объект приложения, вызвав функцию глобального [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).

### <a name="gaining-access-to-other-objects-in-your-application"></a>Доступ к другим объектам в приложении

|Из объекта|Как получить доступ к другим объектам|
|-----------------|---------------------------------|
|Document|Используйте [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) и [GetNextView](../mfc/reference/cdocument-class.md#getnextview) для доступа к списку представление документа.<br /><br /> Вызовите [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) для получения шаблона документа.|
|Просмотр|Вызовите [GetDocument](../mfc/reference/cview-class.md#getdocument) для получения документа.<br /><br /> Вызовите [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) для получения фрейма окна.|
|Окно фрейма документа|Вызовите [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) для получения текущего представления.<br /><br /> Вызовите [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) получить документ, присоединенный к текущему представлению.|
|Окно области MDI|Вызовите [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) получить активный в данный момент [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).|

Как правило окно имеет одно представление, но иногда, как и в окна разделителей, окно фрейма содержит несколько представлений. Окна фрейма сохраняет указатель к текущему активному представлению; указатель обновляется каждый раз, когда активируется другое представление.

> [!NOTE]
>  Указатель на главное окно хранится в [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) переменной-члена объекта приложения. Вызов `OnFileNew` в переопределении `InitInstance` функцию-член `CWinApp` задает *m_pMainWnd* для вас. Если вы не вызываете `OnFileNew`, необходимо задать значение переменной в `InitInstance` самостоятельно. (SDI COM-компонента (сервер) приложения могут не установите переменные при/Embedding в командной строке.) Обратите внимание, что *m_pMainWnd* теперь является членом класса `CWinThread` вместо `CWinApp`.

## <a name="see-also"></a>См. также

[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](../mfc/document-template-creation.md)<br/>
[Создание документа или представления](../mfc/document-view-creation.md)<br/>
[Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

