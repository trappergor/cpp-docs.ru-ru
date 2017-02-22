---
title: "COleServerItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerItem class"
  - "приложения сервера OLE, managing server documents"
  - "приложения сервера OLE, server interfaces"
  - "OLE server documents"
  - "серверы, OLE"
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает интерфейс OLE элементы сервера.  
  
## Синтаксис  
  
```  
class COleServerItem : public CDocItem  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleServerItem::COleServerItem](../Topic/COleServerItem::COleServerItem.md)|Создает объект `COleServerItem`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleServerItem::AddOtherClipboardData](../Topic/COleServerItem::AddOtherClipboardData.md)|Форматы презентации и преобразования мест в `COleDataSource` объект.|  
|[COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md)|Копирует элемент в буфер обмена.|  
|[COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md)|Выполняет операцию перетаскивания.|  
|[COleServerItem::GetClipboardData](../Topic/COleServerItem::GetClipboardData.md)|Возвращает источник данных для использования при передаче данных \(перетаскивание или буфер обмена\).|  
|[COleServerItem::GetDocument](../Topic/COleServerItem::GetDocument.md)|Возвращает документ сервера, содержащего элемент.|  
|[COleServerItem::GetEmbedSourceData](../Topic/COleServerItem::GetEmbedSourceData.md)|Возвращает данные элемента для **CF\_EMBEDSOURCE** OLE.|  
|[COleServerItem::GetItemName](../Topic/COleServerItem::GetItemName.md)|Возвращает имя элемента.  Используемого для связанных элементов.|  
|[COleServerItem::GetLinkSourceData](../Topic/COleServerItem::GetLinkSourceData.md)|Возвращает данные элемента для `CF_LINKSOURCE` OLE.|  
|[COleServerItem::GetObjectDescriptorData](../Topic/COleServerItem::GetObjectDescriptorData.md)|Возвращает данные элемента для **CF\_OBJECTDESCRIPTOR** OLE.|  
|[COleServerItem::IsConnected](../Topic/COleServerItem::IsConnected.md)|Указывает, вложен ли элемент в данный момент к активному контейнер.|  
|[COleServerItem::IsLinkedItem](../Topic/COleServerItem::IsLinkedItem.md)|Указывает, представляет ли элемент связанный элемент OLE.|  
|[COleServerItem::NotifyChanged](../Topic/COleServerItem::NotifyChanged.md)|Обновляет все контейнеры с обновлением автоматической ссылки.|  
|[COleServerItem::OnDoVerb](../Topic/COleServerItem::OnDoVerb.md)|Вызываемый для выполнения команды.|  
|[COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)|Когда запросы с именем контейнера для рисования элемента; требуемая реализация.|  
|[COleServerItem::OnDrawEx](../Topic/COleServerItem::OnDrawEx.md)|Вызываемый для специализированного элемента документа.|  
|[COleServerItem::OnGetClipboardData](../Topic/COleServerItem::OnGetClipboardData.md)|Вызываемый платформой для получения данных, которые будут копируются в буфер обмена.|  
|[COleServerItem::OnGetExtent](../Topic/COleServerItem::OnGetExtent.md)|Вызываемый платформой для получения размер OLE элемента.|  
|[COleServerItem::OnInitFromData](../Topic/COleServerItem::OnInitFromData.md)|Вызываемый платформой для инициализации элемент OLE с помощью содержимого заданного объекта передачи данных.|  
|[COleServerItem::OnQueryUpdateItems](../Topic/COleServerItem::OnQueryUpdateItems.md)|Вызванный, чтобы определить, требуются ли какие\-либо связанные элементы обновления.|  
|[COleServerItem::OnRenderData](../Topic/COleServerItem::OnRenderData.md)|Извлекает данные в ходе отложенной обработки.|  
|[COleServerItem::OnRenderFileData](../Topic/COleServerItem::OnRenderFileData.md)|Извлечение данных в `CFile` объект как часть отложенной обработки.|  
|[COleServerItem::OnRenderGlobalData](../Topic/COleServerItem::OnRenderGlobalData.md)|Извлекает данные в `HGLOBAL` как часть отложенной обработки.|  
|[COleServerItem::OnSetColorScheme](../Topic/COleServerItem::OnSetColorScheme.md)|Вызываемый для задания цветовую схему элемента.|  
|[COleServerItem::OnSetData](../Topic/COleServerItem::OnSetData.md)|Вызываемый для задания сведений об элементе.|  
|[COleServerItem::OnSetExtent](../Topic/COleServerItem::OnSetExtent.md)|Вызываемый платформой, чтобы задать размер OLE элемента.|  
|[COleServerItem::OnUpdate](../Topic/COleServerItem::OnUpdate.md)|Вызывается, когда некоторая часть документа принадлежит элемент внутри изменяется.|  
|[COleServerItem::OnUpdateItems](../Topic/COleServerItem::OnUpdateItems.md)|Вызываемый для обновления кэша представления всех элементов в документе сервера.|  
|[COleServerItem::SetItemName](../Topic/COleServerItem::SetItemName.md)|Задает имя элемента.  Используемого для связанных элементов.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleServerItem::GetDataSource](../Topic/COleServerItem::GetDataSource.md)|Возвращает объект, используемый в форматы преобразования хранилища.|  
|[COleServerItem::OnHide](../Topic/COleServerItem::OnHide.md)|Вызываемый платформой, чтобы скрыть элемент OLE.|  
|[COleServerItem::OnOpen](../Topic/COleServerItem::OnOpen.md)|Вызываемый платформой для отображения OLE элемента в своем собственном окне верхнего уровня.|  
|[COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md)|Когда запросы с именем контейнера, чтобы отобразить элемент.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleServerItem::m\_sizeExtent](../Topic/COleServerItem::m_sizeExtent.md)|Сообщает серверу о том, какая часть элемента OLE видимым.|  
  
## Заметки  
 Связанный элемент может представлять некоторые или все из документа сервера.  Внедренный элемент всегда является весь документ сервера.  
  
 Класс `COleServerItem` определяет несколько функции\-члены переопределяемого метода, которые Вызываются OLE динамически подключаемыми системы библиотеки \(DLL\), обычно в ответ на запросы от контейнерного приложения.  Такие функции\-члены позволяют управлять приложение\-контейнер элемент косвенно различными способами, например, отображая ее выполнение его команды или извлечь данные в разных форматах.  
  
 Для использования `COleServerItem`, унаследуйте класс от него и реализуйте функции\-члены [OnDraw](../Topic/COleServerItem::OnDraw.md) и [Serialize](../Topic/CObject::Serialize.md).  Функция `OnDraw` предоставляет представление метафайла элемента, позволяя его, отображаемой при открытии приложение\-контейнер составного документа.  Функция `Serialize``CObject` предоставляет собственные представления элементов, внедренный элемент для переключения между сервером и приложение\-контейнерами.  Натуральный [OnGetExtent](../Topic/COleServerItem::OnGetExtent.md) предоставляет размер элемента контейнера, что контейнер для определения размера элемента.  
  
 Дополнительные сведения о серверах и связанных разделах см. в статье [Серверы. Реализация сервер](../../mfc/servers-implementing-a-server.md) и "создание контейнера и серверное приложение" в статье [контейнеры: Расширенные функции](../../mfc/containers-advanced-features.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [MFC просматривает HIERSVR](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc Class](../Topic/COleServerDoc%20Class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)