---
title: "COleDocument Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocument class"
  - "документы, OLE"
  - "OLE containers, client items"
  - "OLE documents"
  - "OLE documents, базовый класс"
  - "visual editing, OLE document base class"
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для документов OLE, которые поддерживают визуальное редактирование.  
  
## Синтаксис  
  
```  
class COleDocument : public CDocument  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDocument::COleDocument](../Topic/COleDocument::COleDocument.md)|Создает объект `COleDocument`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDocument::AddItem](../Topic/COleDocument::AddItem.md)|Добавляет элемент в список элементов, обслуживаемые этим документом.|  
|[COleDocument::ApplyPrintDevice](../Topic/COleDocument::ApplyPrintDevice.md)|Задает модуль печат\- целевого объекта для всех клиентских элементов в документе.|  
|[COleDocument::EnableCompoundFile](../Topic/COleDocument::EnableCompoundFile.md)|Приводит к тому, что документы храниться с помощью структурированный OLE формат файла хранилища.|  
|[COleDocument::GetInPlaceActiveItem](../Topic/COleDocument::GetInPlaceActiveItem.md)|Возвращает элемент OLE, который в настоящий момент активны в\- размещения.|  
|[COleDocument::GetNextClientItem](../Topic/COleDocument::GetNextClientItem.md)|Возвращает следующий элемент клиента для итерации.|  
|[COleDocument::GetNextItem](../Topic/COleDocument::GetNextItem.md)|Возвращает следующий элемент документа для итерации.|  
|[COleDocument::GetNextServerItem](../Topic/COleDocument::GetNextServerItem.md)|Возвращает следующий элемент сервера для итерации.|  
|[COleDocument::GetPrimarySelectedItem](../Topic/COleDocument::GetPrimarySelectedItem.md)|Возвращает основной выделенный элемент OLE в документе.|  
|[COleDocument::GetStartPosition](../Topic/COleDocument::GetStartPosition.md)|Получает положение на первоначальную начать итерацию.|  
|[COleDocument::HasBlankItems](../Topic/COleDocument::HasBlankItems.md)|Проверяет наличие пустых элементов в документе.|  
|[COleDocument::OnShowViews](../Topic/COleDocument::OnShowViews.md)|Вызываемый, когда документ становится видимым или невидимым.|  
|[COleDocument::RemoveItem](../Topic/COleDocument::RemoveItem.md)|Удаляет элемент из списка элементов, обслуживаемые этим документом.|  
|[COleDocument::UpdateModifiedFlag](../Topic/COleDocument::UpdateModifiedFlag.md)|Помечает документ как измененное, если изменились какие\-либо элементы, содержащиеся в формате ole.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleDocument::OnEditChangeIcon](../Topic/COleDocument::OnEditChangeIcon.md)|Обрабатывает события в команде меню значка изменения.|  
|[COleDocument::OnEditConvert](../Topic/COleDocument::OnEditConvert.md)|Обрабатывает преобразование внедренный или связанного объекта одного типа к другому.|  
|[COleDocument::OnEditLinks](../Topic/COleDocument::OnEditLinks.md)|Обрабатывает события в ссылках управляют в меню Правка.|  
|[COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)|Отправляет сообщение электронной почты с вложенный документ.|  
|[COleDocument::OnUpdateEditChangeIcon](../Topic/COleDocument::OnUpdateEditChangeIcon.md)|Вызываемый платформой для обновления пользовательский интерфейс команды значок правки для пункта меню\/изменения.|  
|[COleDocument::OnUpdateEditLinksMenu](../Topic/COleDocument::OnUpdateEditLinksMenu.md)|Вызываемый платформой для обновления пользовательский интерфейс команды для параметра меню правка или ссылок.|  
|[COleDocument::OnUpdateObjectVerbMenu](../Topic/COleDocument::OnUpdateObjectVerbMenu.md)|Вызываемый платформой для обновления пользовательский интерфейс команды для параметра меню правка или *ObjectName*, а подменю команды правка и обращения к файлу в *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](../Topic/COleDocument::OnUpdatePasteLinkMenu.md)|Вызываемый платформой для обновления пользовательский интерфейс команды для параметра меню Специальная вставка ".|  
|[COleDocument::OnUpdatePasteMenu](../Topic/COleDocument::OnUpdatePasteMenu.md)|Вызываемый платформой для обновления пользовательский интерфейс команды для параметра меню вставки.|  
  
## Заметки  
 `COleDocument` является производным от **CDocument**, который обеспечивает работу приложения OLE использовать архитектуру " документ\-представление ", обеспечиваемую библиотеки Microsoft Foundation Class.  
  
 `COleDocument` обрабатывается документ как коллекции объектов [CDocItem](../../mfc/reference/cdocitem-class.md) для обработки OLE элементы.  Является и контейнером, и серверные приложения требуют этой архитектуры, так как их документы должны иметь возможность содержать элементы OLE.  Классы [COleServerItem](../../mfc/reference/coleserveritem-class.md) и [COleClientItem](../../mfc/reference/coleclientitem-class.md) оба, производные от `CDocItem`, управляющие взаимодействия между приложениями и элементами OLE.  
  
 При создании простой приложение\-контейнер, наследуйте класс от `COleDocument` документа.  При написании приложение\-контейнер, поддерживающем привязку к внедренным элементам, содержащимся свои документы, наследуйте класс от [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) документа.  При написании контейнер серверного приложения или сочетания\/сервер, наследуйте класс от [COleServerDoc](../Topic/COleServerDoc%20Class.md) документа.  `COleLinkingDoc` и `COleServerDoc` производными от `COleDocument`, поэтому эти классы наследуют все службы, доступные в `COleDocument` и **CDocument**.  
  
 Для использования `COleDocument`, унаследуйте класс от него и добавьте функциональные возможности для управления сведениями о OLE, отличного от приложения и встроенные или связанные элементы.  При указании `CDocItem`\- производные классы для хранения данных приложения собственных можно использовать реализацию по умолчанию, указанную `COleDocument` для хранения и сведения о и OLE, не относящихся к OLE.  Можно также создавать собственные структуры данных для хранения данных, не относящихся к OLE отдельно от OLE элементов.  Дополнительные сведения см. в статье [контейнеры: составные файлы](../../mfc/containers-compound-files.md).  
  
 **CDocument** поддерживает отправить документ по почте если поддержка почты \(MAPI\).  `COleDocument` обновлении [OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md) обрабатывать составные документы правильно.  Дополнительные сведения см. в разделе статьи [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 `COleDocument`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [КОНТЕЙНЕР примеры MFC](../../top/visual-cpp-samples.md)   
 [Образец MFCBIND MFC](../../top/visual-cpp-samples.md)   
 [CDocument Class](../Topic/CDocument%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)