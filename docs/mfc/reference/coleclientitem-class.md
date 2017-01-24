---
title: "COleClientItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleClientItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "client items and OLE containers"
  - "COleClientItem class"
  - "container interface class"
  - "OLE client item class"
  - "OLE containers, client items"
  - "OLE containers, interface class"
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleClientItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет интерфейс контейнера к элементам OLE.  
  
## Синтаксис  
  
```  
class COleClientItem : public CDocItem  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleClientItem::COleClientItem](../Topic/COleClientItem::COleClientItem.md)|Создает объект `COleClientItem`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleClientItem::Activate](../Topic/COleClientItem::Activate.md)|Открывает элемент OLE для операции, а затем выполняет указанную команду.|  
|[COleClientItem::ActivateAs](../Topic/COleClientItem::ActivateAs.md)|Активировать элемент как другой тип.|  
|[COleClientItem::AttachDataObject](../Topic/COleClientItem::AttachDataObject.md)|Получает данные в объект OLE.|  
|[COleClientItem::CanCreateFromData](../Topic/COleClientItem::CanCreateFromData.md)|Указывает, является ли приложение контейнера может создать внедренный объект.|  
|[COleClientItem::CanCreateLinkFromData](../Topic/COleClientItem::CanCreateLinkFromData.md)|Указывает, является ли приложение контейнера может создать связанный объект.|  
|[COleClientItem::CanPaste](../Topic/COleClientItem::CanPaste.md)|Указывает, содержит ли буфер обмена embeddable или статический элемент OLE.|  
|[COleClientItem::CanPasteLink](../Topic/COleClientItem::CanPasteLink.md)|Указывает, содержит ли буфер обмена linkable элемент OLE.|  
|[COleClientItem::Close](../Topic/COleClientItem::Close.md)|Закрывает соединение с сервером, но не удаляет элемент OLE.|  
|[COleClientItem::ConvertTo](../Topic/COleClientItem::ConvertTo.md)|Преобразовывает элемент в другой тип.|  
|[COleClientItem::CopyToClipboard](../Topic/COleClientItem::CopyToClipboard.md)|Копирует элемент OLE в буфер обмена.|  
|[COleClientItem::CreateCloneFrom](../Topic/COleClientItem::CreateCloneFrom.md)|Создает дубликат существующего элемента.|  
|[COleClientItem::CreateFromClipboard](../Topic/COleClientItem::CreateFromClipboard.md)|Создает встроенный элемент из буфера обмена.|  
|[COleClientItem::CreateFromData](../Topic/COleClientItem::CreateFromData.md)|Создает встроенный элемент из объекта данных.|  
|[COleClientItem::CreateFromFile](../Topic/COleClientItem::CreateFromFile.md)|Создает встроенный элемент из файла.|  
|[COleClientItem::CreateLinkFromClipboard](../Topic/COleClientItem::CreateLinkFromClipboard.md)|Создает связанный элемент из буфера обмена.|  
|[COleClientItem::CreateLinkFromData](../Topic/COleClientItem::CreateLinkFromData.md)|Создает связанный элемент из объекта данных.|  
|[COleClientItem::CreateLinkFromFile](../Topic/COleClientItem::CreateLinkFromFile.md)|Создает связанный элемент из файла.|  
|[COleClientItem::CreateNewItem](../Topic/COleClientItem::CreateNewItem.md)|Создает новый внедренный элемент, запустив серверное приложение.|  
|[COleClientItem::CreateStaticFromClipboard](../Topic/COleClientItem::CreateStaticFromClipboard.md)|Создает статический элемент из буфера обмена.|  
|[COleClientItem::CreateStaticFromData](../Topic/COleClientItem::CreateStaticFromData.md)|Создает статический элемент из объекта данных.|  
|[COleClientItem::Deactivate](../Topic/COleClientItem::Deactivate.md)|Отключает элемент.|  
|[COleClientItem::DeactivateUI](../Topic/COleClientItem::DeactivateUI.md)|Извлекает пользовательский интерфейс контейнерного приложения в исходное состояние.|  
|[COleClientItem::Delete](../Topic/COleClientItem::Delete.md)|Удаляет или закрывает элемент OLE, если было связанным элементом.|  
|[COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)|Выполняет операцию перетаскивания.|  
|[COleClientItem::DoVerb](../Topic/COleClientItem::DoVerb.md)|Выполняет указанную команду.|  
|[COleClientItem::Draw](../Topic/COleClientItem::Draw.md)|Рисует элемент OLE.|  
|[COleClientItem::GetActiveView](../Topic/COleClientItem::GetActiveView.md)|Возвращает представление, в котором элемент активировать на месте.|  
|[COleClientItem::GetCachedExtent](../Topic/COleClientItem::GetCachedExtent.md)|Возвращает границы прямоугольника OLE элемента.|  
|[COleClientItem::GetClassID](../Topic/COleClientItem::GetClassID.md)|Получает идентификатор класса присутствующего элемента|  
|[COleClientItem::GetClipboardData](../Topic/COleClientItem::GetClipboardData.md)|Возвращает данные, которые будут помещены в буфер обмена, вызвав функцию\-член `CopyToClipboard`.|  
|[COleClientItem::GetDocument](../Topic/COleClientItem::GetDocument.md)|Возвращает объект `COleDocument`, содержащий элемент, присутствующий.|  
|[COleClientItem::GetDrawAspect](../Topic/COleClientItem::GetDrawAspect.md)|Возвращает текущее представление элемента для отрисовки.|  
|[COleClientItem::GetExtent](../Topic/COleClientItem::GetExtent.md)|Возвращает границы прямоугольника OLE элемента.|  
|[COleClientItem::GetIconFromRegistry](../Topic/COleClientItem::GetIconFromRegistry.md)|Retrives дескриптор для значка, связанный с сервером указанного идентификатора CLSID.|  
|[COleClientItem::GetIconicMetafile](../Topic/COleClientItem::GetIconicMetafile.md)|Возвращает метафайл используемый для рисования значок элемента.|  
|[COleClientItem::GetInPlaceWindow](../Topic/COleClientItem::GetInPlaceWindow.md)|Возвращает указатель в окне редактирования локально элемента.|  
|[COleClientItem::GetItemState](../Topic/COleClientItem::GetItemState.md)|Возвращает текущее состояние элемента.|  
|[COleClientItem::GetLastStatus](../Topic/COleClientItem::GetLastStatus.md)|Возвращает состояние последней операции OLE.|  
|[COleClientItem::GetLinkUpdateOptions](../Topic/COleClientItem::GetLinkUpdateOptions.md)|Возвращает режим обновления для связанного элемента \(продвинутой функций\).|  
|[COleClientItem::GetType](../Topic/COleClientItem::GetType.md)|Возвращает тип, связанный или внедренный \(static\) OLE элемента.|  
|[COleClientItem::GetUserType](../Topic/COleClientItem::GetUserType.md)|Возвращает строку, описывающую тип элемента.|  
|[COleClientItem::IsInPlaceActive](../Topic/COleClientItem::IsInPlaceActive.md)|Возвращает `TRUE` если элемент является активным в\- размещения.|  
|[COleClientItem::IsLinkUpToDate](../Topic/COleClientItem::IsLinkUpToDate.md)|Возвращает **TRUE** если связанный элемент актуален со своим исходным документом.|  
|[COleClientItem::IsModified](../Topic/COleClientItem::IsModified.md)|Возвращает `TRUE`, если элемент был изменен с момента последнего сохранения.|  
|[COleClientItem::IsOpen](../Topic/COleClientItem::IsOpen.md)|Возвращает `TRUE` если элемент в данный момент открыт в серверном приложении.|  
|[COleClientItem::IsRunning](../Topic/COleClientItem::IsRunning.md)|Возвращает `TRUE` если приложение сервера запущено элемента.|  
|[COleClientItem::OnActivate](../Topic/COleClientItem::OnActivate.md)|Вызываемый платформой для уведомления элемент, он активировать.|  
|[COleClientItem::OnActivateUI](../Topic/COleClientItem::OnActivateUI.md)|Вызываемый платформой для уведомления элемент, он должен активировать и отобразить его пользовательский интерфейс.|  
|[COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md)|Вызываемый, когда сервер изменяет элемент OLE.  Требуемая реализация.|  
|[COleClientItem::OnDeactivate](../Topic/COleClientItem::OnDeactivate.md)|Вызываемый платформой, когда элемент будет отключен.|  
|[COleClientItem::OnDeactivateUI](../Topic/COleClientItem::OnDeactivateUI.md)|Вызываемый платформой, когда сервер удалит его пользовательский интерфейс в\- размещения.|  
|[COleClientItem::OnGetClipboardData](../Topic/COleClientItem::OnGetClipboardData.md)|Вызываемый платформой для получения данных необходимо скопировать в буфер обмена.|  
|[COleClientItem::OnInsertMenus](../Topic/COleClientItem::OnInsertMenus.md)|Вызываемый платформой для создания составного меню.|  
|[COleClientItem::OnRemoveMenus](../Topic/COleClientItem::OnRemoveMenus.md)|Вызываемый платформой для удаления меню контейнера из составного меню.|  
|[COleClientItem::OnSetMenu](../Topic/COleClientItem::OnSetMenu.md)|Вызываемый платформой для установки и удаления составное меню.|  
|[COleClientItem::OnShowControlBars](../Topic/COleClientItem::OnShowControlBars.md)|Вызываемый платформой, чтобы отображать и скрывать область элементов управления.|  
|[COleClientItem::OnUpdateFrameTitle](../Topic/COleClientItem::OnUpdateFrameTitle.md)|Вызываемый платформой для обновления заголовок окна фреймового окна.|  
|[COleClientItem::ReactivateAndUndo](../Topic/COleClientItem::ReactivateAndUndo.md)|Повторно активирует элемент и отменяет последнюю операцию редактирования локально.|  
|[COleClientItem::Release](../Topic/COleClientItem::Release.md)|Освобождает соединение к элементу связанному OLE и закрывает его, если он был открыт.  Не удаляет элемент клиента.|  
|[COleClientItem::Reload](../Topic/COleClientItem::Reload.md)|Перезапускает элемент после вызова метода `ActivateAs`.|  
|[COleClientItem::Run](../Topic/COleClientItem::Run.md)|Запускает приложение, связанное с элементом.|  
|[COleClientItem::SetDrawAspect](../Topic/COleClientItem::SetDrawAspect.md)|Задает текущее представление элемента для отрисовки.|  
|[COleClientItem::SetExtent](../Topic/COleClientItem::SetExtent.md)|Задает прямоугольник OLE элемента.|  
|[COleClientItem::SetHostNames](../Topic/COleClientItem::SetHostNames.md)|Устанавливает имена редактирования сервер указывает элемент OLE.|  
|[COleClientItem::SetIconicMetafile](../Topic/COleClientItem::SetIconicMetafile.md)|Кэширует метафайл в кэш, используемый для рисования значок элемента.|  
|[COleClientItem::SetItemRects](../Topic/COleClientItem::SetItemRects.md)|Устанавливает ограничивающий прямоугольник элемента.|  
|[COleClientItem::SetLinkUpdateOptions](../Topic/COleClientItem::SetLinkUpdateOptions.md)|Задает режим обновления для связанных элементов \(продвинутой функций\).|  
|[COleClientItem::SetPrintDevice](../Topic/COleClientItem::SetPrintDevice.md)|Задает модуль печат\- целевого объекта для данного элемента клиента.|  
|[COleClientItem::UpdateLink](../Topic/COleClientItem::UpdateLink.md)|Обновляет кэш представления элемента.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleClientItem::CanActivate](../Topic/COleClientItem::CanActivate.md)|Вызываемый средой, чтобы определить, следует ли разрешена встроенной активации.|  
|[COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)|Вызываемый платформой, если позиция элемента изменится.|  
|[COleClientItem::OnDeactivateAndUndo](../Topic/COleClientItem::OnDeactivateAndUndo.md)|Вызываемый платформой, чтобы отменить после активации.|  
|[COleClientItem::OnDiscardUndoState](../Topic/COleClientItem::OnDiscardUndoState.md)|Вызываемый платформой для отмены отката сведения о состоянии элемента.|  
|[COleClientItem::OnGetClipRect](../Topic/COleClientItem::OnGetClipRect.md)|Вызываемый платформой, для которого необходимо получить диапазон звука\- прямоугольник элемента координатах.|  
|[COleClientItem::OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md)|Вызываемый платформой, чтобы получить позицию элемента по отношению к представлению.|  
|[COleClientItem::OnGetWindowContext](../Topic/COleClientItem::OnGetWindowContext.md)|Вызываемый платформой, когда элемент будет активировать на месте.|  
|[COleClientItem::OnScrollBy](../Topic/COleClientItem::OnScrollBy.md)|Вызываемый платформой, чтобы прокрутить элемент в представление.|  
|[COleClientItem::OnShowItem](../Topic/COleClientItem::OnShowItem.md)|Вызываемый платформой для отображения OLE элемента.|  
  
## Заметки  
 Элемент OLE представляет данные, созданные и поддерживаемые серверным приложением, которое может быть "легко" включаемым в документ таким образом, чтобы он будет отображаться, что пользователю был одинарным документом.  Результат \- "составного документа" являются OLE элемента и содержащего документа.  
  
 Элемент OLE может внедрить или связи.  Если он внедрен, то его данные хранятся как часть составного документа.  Если она связаны, то его данные хранятся в рамках отдельного файла, созданного серверным приложением, и только ссылка на этот файл сохраняется в составном документе.  Все элементы содержат сведения, указывающие, OLE серверное приложение, которое должно быть вызываются, чтобы изменить их.  
  
 `COleClientItem` определяет несколько функций переопределяемого метода, которые Вызываются в ответ на запросы из серверного приложения; эти переопределяемые методы, как правило, являются уведомления.  Это позволяет серверное приложение сообщить контейнер изменений пользователь делает элемент OLE, редактирования или получать сведения, необходимые во время редактирования.  
  
 `COleClientItem` может быть использован с классом [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) или [COleServerDoc](../Topic/COleServerDoc%20Class.md).  Для использования `COleClientItem`, унаследуйте класс от него и реализуйте функции\-члена [OnChange](../Topic/COleClientItem::OnChange.md), который определяет, как контейнер, реагирует на сделанные изменения элемента.  Для поддержки встроенной активации, следует переопределить функцию\-член [OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md).  Эта функция предоставляет сведения об указанном положении OLE элемента.  
  
 Дополнительные сведения об использовании интерфейса контейнера см. статьи [контейнеры: Реализация контейнера](../../mfc/containers-implementing-a-container.md) и [активация](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] ссылается внедренные и связанные элементы, такие как "объекты" и относится к типам элементов, как "класс". Использование этой ссылки термин "элемент" отличить от соответствующего объекта OLE сущность C\+\+ и термин "тип", чтобы отличить категории OLE из класса C\+\+.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [Образец MFCBIND MFC](../../top/visual-cpp-samples.md)   
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)