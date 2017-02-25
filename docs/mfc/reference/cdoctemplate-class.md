---
title: "CDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate class"
  - "шаблоны документов"
  - "шаблоны, документ"
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Абстрактный базовый класс, который определяет базовые функциональные возможности шаблонов документов.  
  
## Синтаксис  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocTemplate::CDocTemplate](../Topic/CDocTemplate::CDocTemplate.md)|Создает объект `CDocTemplate`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDocTemplate::AddDocument](../Topic/CDocTemplate::AddDocument.md)|Добавляет документ с шаблоном.|  
|[CDocTemplate::CloseAllDocuments](../Topic/CDocTemplate::CloseAllDocuments.md)|Закрывает все документы, связанные с этим шаблоном.|  
|[CDocTemplate::CreateNewDocument](../Topic/CDocTemplate::CreateNewDocument.md)|Создает новый документ.|  
|[CDocTemplate::CreateNewFrame](../Topic/CDocTemplate::CreateNewFrame.md)|Создает новое фреймовое окно, в котором содержится документ и представление.|  
|[CDocTemplate::CreateOleFrame](../Topic/CDocTemplate::CreateOleFrame.md)|Создает OLE\- разрешенный фреймовое окно.|  
|[CDocTemplate::CreatePreviewFrame](../Topic/CDocTemplate::CreatePreviewFrame.md)|Создает кадр дочернего элемента, используемый для богатого предварительного просмотра.|  
|[CDocTemplate::GetDocString](../Topic/CDocTemplate::GetDocString.md)|Извлекает строку, связанную с типом документа.|  
|[CDocTemplate::GetFirstDocPosition](../Topic/CDocTemplate::GetFirstDocPosition.md)|Получает положение первого документа, связанного с этим шаблоном.|  
|[CDocTemplate::GetNextDoc](../Topic/CDocTemplate::GetNextDoc.md)|Извлекает документ и позиция следующего.|  
|[CDocTemplate::InitialUpdateFrame](../Topic/CDocTemplate::InitialUpdateFrame.md)|Инициализирует фреймовое окно, а также делает его видимым.|  
|[CDocTemplate::LoadTemplate](../Topic/CDocTemplate::LoadTemplate.md)|Загружает ресурсы для заданного `CDocTemplate` или производного класса.|  
|[CDocTemplate::MatchDocType](../Topic/CDocTemplate::MatchDocType.md)|Определяет степень уверенности в найденном соответствии между типами документов и этим шаблоном.|  
|[CDocTemplate::OpenDocumentFile](../Topic/CDocTemplate::OpenDocumentFile.md)|Открывает файл, указанный по имени пути.|  
|[CDocTemplate::RemoveDocument](../Topic/CDocTemplate::RemoveDocument.md)|Удаляет документ из шаблона.|  
|[CDocTemplate::SaveAllModified](../Topic/CDocTemplate::SaveAllModified.md)|Сохранение всех документов, связанные с этим шаблоном, которые были изменены.|  
|[CDocTemplate::SetContainerInfo](../Topic/CDocTemplate::SetContainerInfo.md)|Определяет ресурсы для редактирования OLE\-контейнер элемент OLE в\- размещения.|  
|[CDocTemplate::SetDefaultTitle](../Topic/CDocTemplate::SetDefaultTitle.md)|Отображается по умолчанию заголовок в строке заголовка окна документа.|  
|[CDocTemplate::SetPreviewInfo](../Topic/CDocTemplate::SetPreviewInfo.md)|Установки из процесса обработки предварительного просмотра.|  
|[CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md)|Определяет ресурсы и классы, когда внедрить документ сервера или изменянное в\- размещение.|  
  
## Заметки  
 Обычно создать один или несколько шаблонов в реализации функции `InitInstance` приложения.  Шаблон документа определяет связи между 3 типов классов:  
  
-   Класс документа, который наследуется от **CDocument**.  
  
-   Класс представления, отображающий данные из класса документа, перечисленные выше.  Можно наследовать этот класс `CView`, `CScrollView`, `CFormView` или `CEditView`.  \(Можно также использовать `CEditView` напрямую\).  
  
-   Класс фреймового окна, который содержит представление.  Для приложения одинарного интерфейса \(SDI\), необходимо создать производный класс от этого `CFrameWnd`.  Для приложения интерфейса MDI, необходимо создать производный класс от этого `CMDIChildWnd`.  Если не нужно настраивать функциональности фреймового окна, можно использовать `CFrameWnd` или `CMDIChildWnd` непосредственно без наследования в класс.  
  
 Приложение имеет один шаблон документа для каждого типа документа, он поддерживает.  Например, если приложение поддерживает и электронные таблицы и текстовые документы, то приложение имеет 2 объекта шаблона документа.  Каждый шаблон документа отвечает за создание и управление все документы этого типа.  
  
 Шаблон документа содержит указатели на объекты `CRuntimeClass` для документа, представления и классов фреймового окна.  Задание этих объектов `CRuntimeClass` при построении шаблон документа.  
  
 Шаблон документа содержит идентификатор ресурсов, используемых с типом документа \(например, меню, значок или ресурсы в таблице сочетаний клавиш\).  Шаблон документа также содержит строки, содержащие дополнительные сведения о своем типе документа.  Они включают имя типа документа \(например, "лист"\) и расширения файлов \(например, ".xls"\).  Дополнительно он может содержать другие строки, используемые пользовательским интерфейсом приложения, файловым менеджером Windows и объектом \(выделение содержит поддержка OLE\).  
  
 Если приложение или сервер OLE\-контейнер, то шаблон документа также определяет идентификатор меню, используемого во время встроенной активации.  Если приложение OLE\-сервер, то шаблон документа определяет идентификатор панели инструментов и меню, используемых во время встроенной активации.  Можно указать эти дополнительные ресурсы путем вызова метода `SetContainerInfo` и OLE `SetServerInfo`.  
  
 Поскольку `CDocTemplate` абстрактный класс, нельзя использовать класс напрямую.  Типичное приложение использует один из 2 `CDocTemplate`\- производные классы, предоставляемые библиотеки Microsoft Foundation Class. `CSingleDocTemplate`, который реализует интерфейс SDI и `CMultiDocTemplate`, который реализует интерфейс MDI.  См. раздел эти классы дополнительные сведения об использовании шаблонов документов.  
  
 Если приложение требует парадигмы, то интерфейса пользователя, принципиально иной из SDI или MDI можно создать собственный класс, производный от `CDocTemplate`.  
  
 Дополнительные сведения о `CDocTemplate` см. в разделе [Шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDocTemplate`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument Class](../Topic/CDocument%20Class.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CEditView Class](../Topic/CEditView%20Class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)