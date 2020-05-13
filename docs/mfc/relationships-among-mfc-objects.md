---
title: Отношения между объектами MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: d7e40e25b405d3f8ec50a518889cc2b89bc8c725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372813"
---
# <a name="relationships-among-mfc-objects"></a>Отношения между объектами MFC

Чтобы помочь уложить процесс создания документа/представления в перспективе, рассмотрим программу выполнения: документ, окно кадра, используемое для содержания представления, и представление, связанное с документом.

- В документе содержится список представлений этого документа и указатель на шаблон документа, создаваемый документ.

- Представление сохраняет указатель на свой документ и является ребенком родительского окна кадра.

- Окно кадра документа сохраняет указатель на текущее активное представление.

- Шаблон документа содержит список открытых документов.

- Приложение хранит список шаблонов документов.

- Windows отслеживает все открытые окна, чтобы отправлять им сообщения.

Эти отношения устанавливаются при создании документа/просмотра. В следующей таблице показано, как объекты в запущенной программе могут получить доступ к другим объектам. Любой объект может получить указатель на объект приложения, позвонив в глобальную функцию [AfxGetApp.](../mfc/reference/application-information-and-management.md#afxgetapp)

### <a name="gaining-access-to-other-objects-in-your-application"></a>Получение доступа к другим объектам в приложении

|Из объекта|Как получить доступ к другим объектам|
|-----------------|---------------------------------|
|Документ|Для доступа к списку просмотров документа используйте [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) и [GetNextView.](../mfc/reference/cdocument-class.md#getnextview)<br /><br /> Позвоните [GetDocTemplate,](../mfc/reference/cdocument-class.md#getdoctemplate) чтобы получить шаблон документа.|
|Представление|Позвоните [GetDocument,](../mfc/reference/cview-class.md#getdocument) чтобы получить документ.<br /><br /> Позвоните [GetParentFrame,](../mfc/reference/cwnd-class.md#getparentframe) чтобы получить окно рамы.|
|Окно кадра документа|Позвоните [GetActiveView,](../mfc/reference/cframewnd-class.md#getactiveview) чтобы получить текущее представление.<br /><br /> Позвоните [GetActiveDocument,](../mfc/reference/cframewnd-class.md#getactivedocument) чтобы получить документ, приложенный к текущему представлению.|
|Окно рамы MDI|Позвоните [MDIGetActive,](../mfc/reference/cmdiframewnd-class.md#mdigetactive) чтобы получить в настоящее время активный [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).|

Как правило, окно кадра имеет одно представление, но иногда, как в окнах сплиттера, одно и то же окно кадра содержит несколько представлений. Окно кадра удерживает указатель на активное представление; указатель обновляется в любое время активации другого представления.

> [!NOTE]
> Указатель на окно основной рамы хранится в переменной [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) члена объекта приложения. Вызов `OnFileNew` в переопределение функции `InitInstance` участника `CWinApp` наборов *m_pMainWnd* для вас. Если вы не `OnFileNew`звоните, вы должны установить значение переменной в `InitInstance` себе. (Компонент SDI COM (сервер) приложения не могут установить переменную, если /Встраивание находится на командной строке.) Обратите внимание, что *m_pMainWnd* `CWinThread` в `CWinApp`настоящее время является членом класса, а не .

## <a name="see-also"></a>См. также раздел

[Шаблоны документов и процесс создания документов/просмотра](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](../mfc/document-template-creation.md)<br/>
[Создание документов/просмотра](../mfc/document-view-creation.md)<br/>
[Создание новых документов, Windows и представлений](../mfc/creating-new-documents-windows-and-views.md)
