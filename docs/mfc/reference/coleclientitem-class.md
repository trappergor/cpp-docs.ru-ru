---
title: "Класс COleClientItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleClientItem class
- OLE client item class
- container interface class
- OLE containers, interface class
- client items and OLE containers
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a200da03305c20eaf2d9c1de1ea585c82410c570
ms.lasthandoff: 02/24/2017

---
# <a name="coleclientitem-class"></a>Класс COleClientItem
Определяет контейнерный интерфейс для элементов OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|Создает объект `COleClientItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|Открытие объекта OLE для операции, а затем выполняет указанную команду.|  
|[COleClientItem::ActivateAs](#activateas)|Активирует элемент другого типа.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|Обращается к данным в OLE-объекта.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|Указывает, может ли приложение контейнера создать внедренный объект.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|Указывает, может ли приложение контейнера создать связанный объект.|  
|[COleClientItem::CanPaste](#canpaste)|Указывает, содержит ли буфер обмена встраиваемая или статического элемента OLE.|  
|[COleClientItem::CanPasteLink](#canpastelink)|Указывает, содержит ли буфер ссылок на основе элемента OLE.|  
|[COleClientItem::Close](#close)|Закрывает ссылку на сервер, но не уничтожает объекта OLE.|  
|[COleClientItem::ConvertTo](#convertto)|Преобразует элемент в другой тип.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|Копирует элемент OLE в буфер обмена.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|Создает копию существующего элемента.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|Создает внедренный элемент из буфера обмена.|  
|[COleClientItem::CreateFromData](#createfromdata)|Создает внедренный элемент из объекта данных.|  
|[COleClientItem::CreateFromFile](#createfromfile)|Создает внедренный элемент из файла.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|Создание связанного элемента из буфера обмена.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|Создание связанного элемента из объекта данных.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|Создает связанный элемент из файла.|  
|[COleClientItem::CreateNewItem](#createnewitem)|Создает новый внедренный элемент, запустив приложение сервера.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|Создание статического элемента из буфера обмена.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|Создание статического элемента из объекта данных.|  
|[COleClientItem::Deactivate](#deactivate)|Отключает элемент.|  
|[COleClientItem::DeactivateUI](#deactivateui)|Восстанавливает исходное состояние пользовательского интерфейса приложения-контейнера.|  
|[COleClientItem::Delete](#delete)|Удаляет или закрывает элемент OLE, если связанный элемент.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|Выполняет операцию и перетаскивания.|  
|[COleClientItem::DoVerb](#doverb)|Выполняет указанную команду.|  
|[COleClientItem::Draw](#draw)|Рисует элемент OLE.|  
|[COleClientItem::GetActiveView](#getactiveview)|Возвращает представление, на котором активируется элемента на месте.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|Возвращает границы прямоугольника объекта OLE.|  
|[COleClientItem::GetClassID](#getclassid)|Возвращает идентификатор присутствует элемент класса.|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|Возвращает данные, следует поместить в буфер обмена, вызвав `CopyToClipboard` функции-члена.|  
|[COleClientItem::GetDocument](#getdocument)|Возвращает `COleDocument` , содержащий присутствует элемент.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|Возвращает текущее представление элемента для подготовки к просмотру.|  
|[COleClientItem::GetExtent](#getextent)|Возвращает границы прямоугольника объекта OLE.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|Получает дескриптор значка, связанного с сервером для определенного идентификатора CLSID.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|Возвращает метафайла, используемую для рисования на значок элемента.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|Возвращает указатель на окно редактирования элемента на месте.|  
|[COleClientItem::GetItemState](#getitemstate)|Возвращает текущее состояние элемента.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|Возвращает состояние последней операции OLE.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|Возвращает режим обновления для связанного элемента (дополнительная возможность).|  
|[COleClientItem::GetType](#gettype)|Возвращает тип объекта OLE (внедренные, связанные или статический).|  
|[COleClientItem::GetUserType](#getusertype)|Возвращает строку, описывающую тип данного элемента.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|Возвращает `TRUE` , если элемент является активным на месте.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|Возвращает **TRUE** Если связанный элемент в курсе его исходный документ.|  
|[COleClientItem::IsModified](#ismodified)|Возвращает `TRUE` , если элемент был изменен с момента последнего сохранения.|  
|[COleClientItem::IsOpen](#isopen)|Возвращает `TRUE` , если элемент в данный момент открыт в серверном приложении.|  
|[COleClientItem::IsRunning](#isrunning)|Возвращает `TRUE` Если элемента серверное приложение выполняется.|  
|[COleClientItem::OnActivate](#onactivate)|Вызывается платформой для уведомления элемента он активируется.|  
|[COleClientItem::OnActivateUI](#onactivateui)|Вызывается платформой для уведомления элемента, он активируется и должен показывать его пользовательский интерфейс.|  
|[COleClientItem::OnChange](#onchange)|Вызывается при изменении сервера объекта OLE. Требуется реализация.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|Вызывается инфраструктурой при деактивации элемента.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|Вызывается платформой, когда сервер удалил его интерфейс пользователя на месте.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|Вызывается платформой для получения данных, копируемых в буфер обмена.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|Вызывается платформой для создания составного меню.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|Вызывается платформой для удаления меню контейнера из составного меню.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|Вызывается платформой для установки и удаления составного меню.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|Вызывается платформой для отображения и скрытия панели элементов управления.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|Вызывается платформой для обновления заголовка рамки окна.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|Повторно активирует элемент и отменяет последнюю операцию редактирования на месте.|  
|[COleClientItem::Release](#release)|Освобождает соединение для связанного элемента OLE и закрывает его, если он был открыт. Не разрушает клиентский элемент.|  
|[COleClientItem::Reload](#reload)|Перезагружает элемента после вызова `ActivateAs`.|  
|[COleClientItem::Run](#run)|Запускает приложение, связанное с элементом.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|Задает текущее представление элемента для подготовки к просмотру.|  
|[COleClientItem::SetExtent](#setextent)|Задает прямоугольник, ограничивающий элемент OLE.|  
|[COleClientItem::SetHostNames](#sethostnames)|Задает имена сервера отображаются при редактировании объекта OLE.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|Кэширует метафайла, используемую для рисования на значок элемента.|  
|[COleClientItem::SetItemRects](#setitemrects)|Задает прямоугольник, ограничивающий элемент.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|Задает режим обновления для связанного элемента (дополнительная возможность).|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|Задает печати целевого устройства для этого элемента клиента.|  
|[COleClientItem::UpdateLink](#updatelink)|Обновляет кэш представления элемента.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleClientItem::CanActivate](#canactivate)|Вызывается средой, чтобы определить, разрешена ли активация на месте.|  
|[COleClientItem::OnChangeItemPosition](#onchangeitemposition)|Вызывается инфраструктурой при изменении положения элемента.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|Вызывается платформой для отмены после активации.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|Вызывается платформой для отмены сведения о состоянии отмены элемента.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|Вызывается платформой для получения координаты элемента прямоугольник отсечения.|  
|[COleClientItem::OnGetItemPosition](#ongetitemposition)|Вызывается платформой для получения позиции относительно представления.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|Вызывается инфраструктурой при активизации элемента на месте.|  
|[COleClientItem::OnScrollBy](#onscrollby)|Вызывается платформой для прокрутки элемента в представлении.|  
|[COleClientItem::OnShowItem](#onshowitem)|Вызывается платформой для отображения объекта OLE.|  
  
## <a name="remarks"></a>Примечания  
 Элемент OLE представляет данные, создается и обслуживается приложение сервера, которое может быть ««встраивается в документ, чтобы он отображался пользователю, чтобы быть в один документ. Результатом является элемент OLE и содержащий документ «составного документа».  
  
 Элемент OLE можно внедренные или связанные. Если они внедрены данные хранятся как часть составного документа. Если он связан, его данные сохраняются как часть отдельный файл, созданный приложением сервера и ссылку на этот файл хранится в составном документе. Все элементы OLE содержат сведения, указав серверное приложение, который должен быть вызван для их изменения.  
  
 `COleClientItem`определяет несколько переопределяемые функции, которые вызываются в ответ на запросы из серверного приложения; Эти переопределяемости обычно используются в качестве уведомления. Это позволяет приложению сервера для информирования контейнера изменения, внесенные пользователем, при редактировании объекта OLE или получать сведения, необходимые во время редактирования.  
  
 `COleClientItem`может использоваться с любой [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), или [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) класса. Для использования `COleClientItem`, создайте класс, производный от него и реализовать [OnChange](#onchange) функция-член, который определяет реакцию на изменения, внесенные в элемент контейнера. Для поддержки активации на месте, переопределите [OnGetItemPosition](#ongetitemposition) функции-члена. Эта функция предоставляет сведения о положении отображаемого элемента OLE.  
  
 Дополнительные сведения об использовании интерфейса контейнера см. в статьях [контейнеры: реализация контейнера](../../mfc/containers-implementing-a-container.md) и [активации](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Ссылается на внедренные и связанные элементы, как «объекты» и ссылается на типы элементов в виде «классы». Эта ссылка используется термин «item» для выделения объекта OLE из соответствующего объекта C++ и термин «тип» для различения классов C++ категории OLE.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="activate"></a>COleClientItem::Activate  
 Эта функция вызывается для выполнения указанной команды вместо [DoVerb](#doverb) таким образом, чтобы можно было выполнять собственную обработку при возникновении исключения.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nVerb`  
 Указывает команду для выполнения. Это может быть одно из следующих:  
  
|Значение|Значение|Символ|  
|-----------|-------------|------------|  
|– 0|первичный глагол|`OLEIVERB_PRIMARY`|  
|– 1|Вторичный команд|(Нет)|  
|– 1|Отображение элемента для редактирования|`OLEIVERB_SHOW`|  
|– 2|Изменение элемента в отдельном окне|`OLEIVERB_OPEN`|  
|– 3|Скрытие элементов|`OLEIVERB_HIDE`|  
  
 Значение –&1;, обычно является псевдонимом для другой команды. Если открыть изменения не поддерживается, –&2; действует так же, как -1. Дополнительные значения в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pView`  
 Указатель на окно представления контейнера, содержащего элемент OLE; приложение-сервер используется для активации на месте. Этот параметр должен быть **NULL** Если контейнер не поддерживает активацию на месте.  
  
 `lpMsg`  
 Указатель на сообщение, вызвавшей элемента необходимо активировать.  
  
### <a name="remarks"></a>Примечания  
 Если серверное приложение было написано с помощью библиотеки Microsoft Foundation Class, эта функция приводит [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) функции-члена соответствующего `COleServerItem` объекта для выполнения.  
  
 Если первичный глагол редактирования и указано нулевое значение в `nVerb` параметр серверное приложение запускается, чтобы разрешить редактирование объекта OLE. Если приложение-контейнер поддерживает активацию на месте, изменения можно выполнить на месте. Если контейнер не поддерживает активация на месте (или если открыть указаны), сервер запускается в отдельном окне и редактирования можно использовать там. Как правило, когда приложения-контейнера двойном щелчке объекта OLE, значение первичный глагол в `nVerb` параметр определяет, какие действия пользователь может предпринять. Тем не менее, если сервер поддерживает только одно действие, у этого действия, независимо от того, что значение задано в `nVerb` параметр.  
  
 Дополнительные сведения см. в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="activateas"></a>COleClientItem::ActivateAs  
 Использует средства преобразования объектов OLE для активации элемента, как если бы он элемент типа, заданного параметром `clsidNew`.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszUserType*  
 Указатель на строку, представляющую тип объекта пользователя, такие как «Документ Word».  
  
 *clsidOld*  
 Ссылка на класс текущего элемента по идентификатору. Идентификатор класса должен представлять тип фактического объекта, как хранятся, пока это ссылка. В этом случае следует CLSID элемента, на который указывает эта ссылка. [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) автоматически предоставляет идентификатор правильного класса для элемента.  
  
 `clsidNew`  
 Ссылку на идентификатор целевого класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Это называется автоматически [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert). Он не вызывается обычно напрямую.  
  
##  <a name="attachdataobject"></a>COleClientItem::AttachDataObject  
 Эта функция вызывается для инициализации [COleDataObject](../../mfc/reference/coledataobject-class.md) для доступа к данным в элементе OLE.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *rDataObject*  
 Ссылка на `COleDataObject` объект, который будет инициализирован для доступа к данным в элементе OLE.  
  
##  <a name="canactivate"></a>COleClientItem::CanActivate  
 Вызывается инфраструктурой при запросе активации на месте элемента OLE; Эта функция возвращаемое значение определяет, разрешена ли активация на месте.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если разрешена активация на месте; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию позволяет активации на месте, если контейнер имеет допустимый окна. Переопределите эту функцию, чтобы реализовать специальную логику для принимает или отклоняет запрос на активацию. Например запрос на активацию можно отказано, если элемент OLE слишком маленькими, либо в настоящее время не отображается.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="cancreatefromdata"></a>COleClientItem::CanCreateFromData  
 Проверяет, может ли приложение контейнера создать внедренный объект из заданного `COleDataObject` объекта.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на [COleDataObject](../../mfc/reference/coledataobject-class.md) объекта, из которого будет создаваться объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если контейнер можно создать внедренный объект из `COleDataObject` объекта; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `COleDataObject` Класс используется в передаче данных для извлечения данных в разных форматах из буфера обмена путем перетаскивания или из встроенного элемента OLE.  
  
 Контейнеры можно использовать эту функцию следует включить или отключить их вставки, изменения и Специальная вставка команд.  
  
 Дополнительные сведения см. в статье [объектов данных и источников данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="cancreatelinkfromdata"></a>COleClientItem::CanCreateLinkFromData  
 Проверяет, может ли приложение контейнера создать связанный объект из заданного `COleDataObject` объекта.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на [COleDataObject](../../mfc/reference/coledataobject-class.md) объекта, из которого будет создаваться объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если контейнер можно создать связанный объект из `COleDataObject` объекта.  
  
### <a name="remarks"></a>Примечания  
 `COleDataObject` Класс используется в передаче данных для извлечения данных в разных форматах из буфера обмена путем перетаскивания или из встроенного элемента OLE.  
  
 Контейнеры можно использовать эту функцию следует включить или отключить их Специальная вставка и изменение связать команды.  
  
 Дополнительные сведения см. в статье [объектов данных и источников данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="canpaste"></a>COleClientItem::CanPaste  
 Эта функция используется для просмотра, можно ли вставить из буфера обмена встроенного элемента OLE.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если встроенного элемента OLE можно вставить из буфера обмена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) и [OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="canpastelink"></a>COleClientItem::CanPasteLink  
 Вызывайте эту функцию, чтобы увидеть, является ли связанный элемент OLE можно вставить из буфера обмена.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если связанный элемент OLE можно вставить из буфера обмена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) и [OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="close"></a>COleClientItem::Close  
 Эта функция вызывается для изменения состояния объекта OLE из активного состояния в загруженное состояние, то есть, загрузить его обработчик в памяти, но не сервером.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCloseOption`  
 Флаг, указывающий, при каких обстоятельствах объекта OLE сохраняется при возвращении в загруженное состояние. Он может принимать одно из следующих значений:  
  
- `OLECLOSE_SAVEIFDIRTY`Сохраните элемент OLE.  
  
- `OLECLOSE_NOSAVE`Не сохраняйте объекта OLE.  
  
- `OLECLOSE_PROMPTSAVE`Запрос на необходимость сохранения элемента OLE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не оказывает влияния при объекта OLE не работает.  
  
 Дополнительные сведения см. в разделе [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="coleclientitem"></a>COleClientItem::COleClientItem  
 Создает `COleClientItem` объекта и добавляет его в документе-контейнере коллекцию элементов документа, который создает объект C++ и не выполняет инициализацию OLE.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pContainerDoc`  
 Указатель контейнера документа, содержащего этот элемент. Это может быть любой [COleDocument](../../mfc/reference/coledocument-class.md) производный класс.  
  
### <a name="remarks"></a>Примечания  
 Если передать **NULL** указатель, добавление не выполняется в документе-контейнере. Необходимо явно вызвать [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem).  
  
 Перед использованием объекта OLE необходимо вызвать один из следующих функций создания элемента:  
  
- [CreateFromClipboard](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [CreateStaticFromClipboard](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>COleClientItem::ConvertTo  
 Вызовите эту функцию-член преобразовать элемент в тип, указанный в `clsidNew`.  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Параметры  
 `clsidNew`  
 Идентификатор класса типа целевого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Это называется автоматически [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md). Не нужно вызывать его напрямую.  
  
##  <a name="copytoclipboard"></a>COleClientItem::CopyToClipboard  
 Эта функция вызывается для объекта OLE скопировать в буфер обмена.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bIncludeLink`  
 **Значение TRUE,** Если информация о связи должны копироваться в буфер обмена, позволяя связанный элемент вставленного; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Как правило эта функция вызывается при написании обработчиков сообщений для команды Копировать или Вырезать в меню Правка. Выбор элемента необходимо реализовать в приложения-контейнера, если вы хотите реализовать команды Копировать или Вырезать.  
  
 Дополнительные сведения см. в разделе [OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createclonefrom"></a>COleClientItem::CreateCloneFrom  
 Эта функция вызывается для создания копии указанного элемента OLE.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pSrcItem*  
 Указатель на элемент OLE к дублированию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Копирование совпадает с исходным элементом. Эта функция используется для поддержки операции отмены.  
  
##  <a name="createfromclipboard"></a>COleClientItem::CreateFromClipboard  
 Эта функция вызывается для создания встроенного элемента из содержимого буфера обмена.  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Вы обычно эта функция вызывается из обработчика сообщений вставить команду в меню «Правка». (Команда Вставить включен платформой, если [CanPaste](#canpaste) функция-член возвращает ненулевое значение.)  
  
 Дополнительные сведения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createfromdata"></a>COleClientItem::CreateFromData  
 Эта функция вызывается для создания встроенного элемента из `COleDataObject` объекта.  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на [COleDataObject](../../mfc/reference/coledataobject-class.md) объекта, из которого будет создаваться объекта OLE.  
  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Укажите операций передачи данных, например вставки из буфера обмена или операции и перетащите `COleDataObject` объектов, содержащий сведения, предоставляемые серверное приложение. Обычно он используется в переопределении [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop).  
  
 Дополнительные сведения см. в разделе [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createfromfile"></a>COleClientItem::CreateFromFile  
 Эта функция вызывается для создания встроенного элемента OLE из файла.  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Указатель на имя файла, из которого будет создаваться объекта OLE.  
  
 `clsid`  
 Зарезервировано для будущего использования.  
  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию из [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) , если пользователь выбирает при выборе создания файла кнопки OK в диалоговом окне Вставка объекта.  
  
 Дополнительные сведения см. в разделе [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromclipboard"></a>COleClientItem::CreateLinkFromClipboard  
 Эта функция вызывается для создания связанного элемента из содержимого буфера обмена.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Вы обычно эта функция вызывается из обработчика сообщений связать команду в меню «Правка». (Команда Вставить связь включена в реализации по умолчанию [COleDocument](../../mfc/reference/coledocument-class.md) , если в буфере обмена содержатся объекта OLE, который может быть связан с.)  
  
 Дополнительные сведения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromdata"></a>COleClientItem::CreateLinkFromData  
 Эта функция вызывается для создания связанного элемента из `COleDataObject` объекта.  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на [COleDataObject](../../mfc/reference/coledataobject-class.md) объекта, из которого будет создаваться объекта OLE.  
  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызывает его во время операции перетаскивания, когда пользователь указывает, что необходимо создать ссылку. Он также может использоваться для обработки команды Edit Paste. Вызывается платформой в `COleClientItem::CreateLinkFromClipboard` и [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Если был выбран параметр Link.  
  
 Дополнительные сведения см. в разделе [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromfile"></a>COleClientItem::CreateLinkFromFile  
 Эта функция вызывается для создания связанного объекта OLE из файла.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Указатель на имя файла, из которого будет создаваться объекта OLE.  
  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает данную функцию, если пользователь выбирает ОК в диалоговом окне Вставка объекта, если выбрано создание файла кнопки и установлен флажок ссылка. Он вызывается из [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem).  
  
 Дополнительные сведения см. в разделе [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createnewitem"></a>COleClientItem::CreateNewItem  
 Эта функция вызывается для создания встроенного элемента; Эта функция запускает приложения сервера, которая служит для создания объекта OLE.  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Идентификатор, который однозначно определяет тип создаваемого элемента OLE.  
  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает данную функцию, если пользователь выбирает ОК в диалоговом окне Вставка объекта, если выбрана кнопка «Создать».  
  
 Дополнительные сведения см. в разделе [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstaticfromclipboard"></a>COleClientItem::CreateStaticFromClipboard  
 Эта функция вызывается для создания статического элемента из содержимого буфера обмена.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Статический элемент содержит представления данных, но не собственных данных; поэтому его нельзя изменить. Эта функция обычно вызывается при [CreateFromClipboard](#createfromclipboard) сбоя функции-члена.  
  
 Дополнительные сведения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstaticfromdata"></a>COleClientItem::CreateStaticFromData  
 Эта функция вызывается для создания статического элемента из `COleDataObject` объекта.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на [COleDataObject](../../mfc/reference/coledataobject-class.md) объекта, из которого будет создаваться объекта OLE.  
  
 *отрисовки*  
 Флаг, указывающий, как сервер будет обрабатывать объекта OLE. Возможные значения см. в разделе [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Задает формат данных буфера обмена для кэширования, при создании объекта OLE.  
  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, используемая при *визуализации* — **OLERENDER_FORMAT** или **OLERENDER_DRAW**. Укажите значение для этого параметра только в том случае, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если этот параметр не указан, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Статический элемент содержит представления данных, но не собственных данных; Следовательно нельзя изменять. Это по сути то же самое, как [CreateStaticFromClipboard](#createstaticfromclipboard) за исключением того, что статический элемент может быть создан из произвольного `COleDataObject`, не только из буфера обмена.  
  
 Используется в [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) при выборе Static.  
  
 Дополнительные сведения см. в разделе [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deactivate"></a>COleClientItem::Deactivate  
 Эта функция объекта OLE и освобождения любых связанных ресурсов.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Объект OLE по месту active обычно деактивировать, когда пользователь щелкает мышью на клиентскую область вне границ элемента. Обратите внимание, что отключение элемента OLE будут отменены состояние отмены, делая невозможным для вызова [ReactivateAndUndo](#reactivateandundo) функции-члена.  
  
 Если приложение поддерживает отмены, не следует вызывать `Deactivate`; вместо этого вызвать [DeactivateUI](#deactivateui).  
  
 Дополнительные сведения см. в разделе [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deactivateui"></a>COleClientItem::DeactivateUI  
 Эта функция вызывается, когда пользователь отключает элемент, который был активирован на месте.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция восстанавливает пользовательский интерфейс приложения-контейнера в исходное состояние, скрывая все меню и других элементов управления, которые были созданы для активации на месте.  
  
 Эта функция не сбрасывает сведения состояние отмены для элемента. Информация сохраняется, чтобы [ReactivateAndUndo](#reactivateandundo) позже можно выполнить команду отмены в серверном приложении, в случае выбора команды отмены контейнера сразу после деактивации элемента.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="delete"></a>COleClientItem::Delete  
 Эта функция вызывается для удаления объекта OLE из контейнера документа.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutoDelete`  
 Указывает, является ли элемент удален из документа.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию [выпуска](#release) функция-член, который в свою очередь удаляет объект C++ для элементов, окончательно удалить элемент OLE из документа. Если внедренного объекта OLE собственные данные для элемента удаляется. Она всегда закрывает работающем сервере; Таким образом Если элемент является открыть ссылку, эта функция закрывает его.  
  
##  <a name="dodragdrop"></a>COleClientItem::DoDragDrop  
 Вызов `DoDragDrop` для выполнения операции и перетащите функции-члена.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpItemRect`  
 Прямоугольник элемента на экране в координатах клиента (в пикселях).  
  
 `ptOffset`  
 Смещение от `lpItemRect` положением положением указателя мыши во время операции перетаскивания.  
  
 `bIncludeLink`  
 Задайте значение **TRUE** Если данные ссылки должны быть скопированы в буфер обмена. Задайте для него значение **FALSE** Если серверное приложение не поддерживает ссылки.  
  
 `dwEffects`  
 Определяет эффекты, которые источник перетаскивания будет разрешать в операции перетаскивания.  
  
 `lpRectStartDrag`  
 Указатель на прямоугольник, определяющий, где фактически начинает перетаскивание. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `DROPEFFECT`. Если это `DROPEFFECT_MOVE`, исходные данные должны удаляться.  
  
### <a name="remarks"></a>Примечания  
 Операции и перетащите начать немедленно. Он ждет, пока указатель мыши выходит за пределы прямоугольника, определяемого `lpRectStartDrag` или пока не прошли указанного числа миллисекунд. Если `lpRectStartDrag` — **NULL**, размер прямоугольника равно одному пикселю.  
  
 Время задержки задается параметр раздела реестра. Время задержки можно изменить с помощью [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если время задержки не указан, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите сохраняются следующим образом:  
  
-   Время задержки Windows NT перетащите хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Время задержки Windows 3.x перетащите хранится в WIN. INI-файл, в разделе [Windows}.  
  
-   Время задержки Windows 95/98 перетащите хранится в кэшированную версию WIN. INI.  
  
 Для перетащите Дополнительные сведения о том, как задержка сведения хранятся в реестре или. INI-файл, в разделе [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="doverb"></a>COleClientItem::DoVerb  
 Вызов `DoVerb` для выполнения указанной команды.  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nVerb`  
 Указывает команду для выполнения. Он может включать одно из следующих:  
  
|Значение|Значение|Символ|  
|-----------|-------------|------------|  
|– 0|первичный глагол|`OLEIVERB_PRIMARY`|  
|– 1|Вторичный команд|(Нет)|  
|– 1|Отображение элемента для редактирования|`OLEIVERB_SHOW`|  
|– 2|Изменение элемента в отдельном окне|`OLEIVERB_OPEN`|  
|– 3|Скрытие элементов|`OLEIVERB_HIDE`|  
  
 Значение –&1;, обычно является псевдонимом для другой команды. Если открыть изменения не поддерживается, –&2; действует так же, как -1. Дополнительные значения в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pView`  
 Указатель на окно представления; используется сервером для активации на месте. Этот параметр должен быть **NULL** Если приложение контейнера не допускает активации на месте.  
  
 `lpMsg`  
 Указатель на сообщение, вызвавшей элемента необходимо активировать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если команда была выполнена успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию [активировать](#activate) функции-члена для выполнения команды. Также улавливает исключения и отображает окно сообщения для пользователя, если оно создается.  
  
 Если первичный глагол редактирования и указано нулевое значение в `nVerb` параметр серверное приложение запускается, чтобы разрешить редактирование объекта OLE. Если приложение-контейнер поддерживает активацию на месте, изменения можно выполнить на месте. Если контейнер не поддерживает активация на месте (или если открыть указаны), сервер запускается в отдельном окне и редактирования можно использовать там. Как правило, когда приложения-контейнера двойном щелчке объекта OLE, значение первичный глагол в `nVerb` параметр определяет, какие действия пользователь может предпринять. Тем не менее, если сервер поддерживает только одно действие, у этого действия, независимо от того, что значение задано в `nVerb` параметр.  
  
##  <a name="draw"></a>COleClientItem::Draw  
 Эта функция вызывается для рисования элемента OLE в указанный ограничивающего прямоугольника, с помощью заданного контекста устройств.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объект, используемый для рисования элемента OLE.  
  
 `lpBounds`  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или `RECT` структура, определяющая ограничивающий прямоугольник для рисования объекта OLE (в логических единицах определяется контекст устройства).  
  
 `nDrawAspect`  
 Указывает аспект OLE элемента, то есть, как он должен отображаться. Если `nDrawAspect` –&1;, последний аспект, задайте с помощью [SetDrawAspect](#setdrawaspect) используется. Дополнительные сведения о возможных значениях этого флага см. в разделе [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция может использовать представление метафайла элемента OLE, созданные [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) функции-члена `COleServerItem`.  
  
 Обычно используется **рисовать** для просмотра на экране, передача контекста устройства экрана как `pDC`. В этом случае необходимо указать только первые два параметра.  
  
 `lpBounds` Параметр указывает прямоугольник в контексте целевого устройства (относительно своего текущего режима сопоставления). Отрисовка может включать в себя масштаба рисунка и может использоваться приложения контейнера, чтобы создать представление, которое масштабируется между отображаемому представлению и печатного изображения.  
  
 Дополнительные сведения см. в разделе [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getactiveview"></a>COleClientItem::GetActiveView  
 Возвращает представление, на котором она активации на месте.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на представления. в противном случае **NULL** , если она не активирована на месте.  
  
##  <a name="getcachedextent"></a>COleClientItem::GetCachedExtent  
 Эта функция вызывается для получения размера элемента OLE.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `lpSize`  
 Указатель на **размер** структуры или [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта, который будет получать сведения о размере.  
  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого должны быть получены. Возможные значения см. в разделе [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; 0, если пусто объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет те же сведения, что [GetExtent](#getextent). Тем не менее, можно вызвать `GetCachedExtent` для получения сведений экстентов во время обработки другие обработчики OLE, таких как [OnChange](#onchange). Измерения — в `MM_HIMETRIC` единиц.  
  
 Это возможно, поскольку `GetCachedExtent` использует [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) интерфейс, а не использовать [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) интерфейса, чтобы получить степень этого элемента. **IViewObject2** COM-объект кэширует сведения экстента, используемые в предыдущем вызове [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655).  
  
 Дополнительные сведения см. в разделе [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclassid"></a>COleClientItem::GetClassID  
 Возвращает идентификатор класса элемента в памяти, на который указывает `pClassID`.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pClassID`  
 Указатель на идентификатор типа [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) для получения идентификатора класса. Сведения о **CLSID**, в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Идентификатор класса — 128-разрядное число, которое однозначно определяет приложение, которое изменяет элемент.  
  
 Дополнительные сведения см. в разделе [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclipboarddata"></a>COleClientItem::GetClipboardData  
 Эта функция вызывается для получения `COleDataSource` объект, содержащий все данные, которые следует поместить в буфер обмена с помощью вызова [CopyToClipboard](#copytoclipboard) функции-члена.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataSource`  
 Указатель на [COleDataSource](../../mfc/reference/coledatasource-class.md) объекта, который будет получать данные, содержащиеся в элементе OLE.  
  
 `bIncludeLink`  
 **Значение TRUE,** Если ссылку данные должны быть включены; в противном случае **FALSE**.  
  
 `lpOffset`  
 Смещение указателя мыши от начала координат объекта в пикселях.  
  
 `lpSize`  
 Размер объекта в пикселях.  
  
### <a name="remarks"></a>Примечания  
 `GetClipboardData`вызывается реализация по умолчанию [OnGetClipboardData](#ongetclipboarddata). Переопределение `OnGetClipboardData` только в том случае, если вы хотите предложить форматы данных, отличные от предлагаемых `CopyToClipboard`. Поместите эти форматы в `COleDataSource` объекта до или после вызова метода `CopyToClipboard`и затем передайте `COleDataSource` объект [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) функции. Например, чтобы положение элемента OLE для контейнера документа прилагаются его в буфер обмена, можно определить свой собственный формат для передачи этой информации и поместите его в `COleDataSource` перед вызовом метода `CopyToClipboard`.  
  
##  <a name="getdocument"></a>COleClientItem::GetDocument  
 Эта функция вызывается для получения указателя в документ, содержащий элемент OLE.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент OLE. **NULL** Если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель позволяет получить доступ к `COleDocument` объекта, переданного в качестве аргумента `COleClientItem` конструктор.  
  
##  <a name="getdrawaspect"></a>COleClientItem::GetDrawAspect  
 Вызов `GetDrawAspect` функции-члена для определения текущего «аспекты» или отображения элемента.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение из `DVASPECT` перечисления, значения которого перечислены в справочнике [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Примечания  
 Аспект указывается как элемент для отображения.  
  
##  <a name="getextent"></a>COleClientItem::GetExtent  
 Эта функция вызывается для получения размера элемента OLE.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>Параметры  
 `lpSize`  
 Указатель на **размер** структуры или `CSize` объект, который будет получать сведения о размере.  
  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого должны быть получены. Возможные значения см. в разделе [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; 0, если пусто объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Если серверное приложение было написано с помощью библиотеки Microsoft Foundation Class, эта функция приводит [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) функции-члена соответствующего `COleServerItem` вызов объекта. Обратите внимание, что полученный размер может отличаться от последнего задается размер [SetExtent](#setextent) функция-член; размер, заданный свойством `SetExtent` рассматривается как предложение. Измерения — в `MM_HIMETRIC` единиц.  
  
> [!NOTE]
>  Не следует вызывать `GetExtent` во время обработки обработчика OLE, таких как [OnChange](#onchange). Вызов [GetCachedExtent](#getcachedextent) вместо.  
  
 Дополнительные сведения см. в разделе [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonfromregistry"></a>COleClientItem::GetIconFromRegistry  
 Вызовите эту функцию-член для получения дескриптора ресурс значка, связанного с сервером для определенного идентификатора CLSID.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Ссылка на идентификатор CLSID для сервера, связанного со значком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый дескриптор ресурс значка или **NULL** , если не удается найти сервер значок или значок по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член не будет запустить сервер или получить значок динамически, даже если на сервере уже выполняется. Вместо этого эта функция-член открывает исполняемого образа и получает статический значка, связанного с сервером, как он был зарегистрирован.  
  
##  <a name="geticonicmetafile"></a>COleClientItem::GetIconicMetafile  
 Извлекает метафайла, используемую для рисования на значок элемента.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если отсутствует текущий значок, возвращается значок по умолчанию. Это вызывается автоматически диалоговые окна MFC/OLE и обычно не вызывается напрямую.  
  
 Эта функция также вызывает [SetIconicMetafile](#seticonicmetafile) кэшировать метафайла, предназначенную для последующего использования.  
  
##  <a name="getinplacewindow"></a>COleClientItem::GetInPlaceWindow  
 Вызов `GetInPlaceWindow` функции-члена получить указатель в окно, в котором элемент был открыт для редактирования на месте.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно редактирования элемента на месте; **NULL** Если элемент не активна или если его сервер недоступен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только для элементов, которые являются активными в месте.  
  
##  <a name="getitemstate"></a>COleClientItem::GetItemState  
 Эта функция вызывается для получения текущего состояния объекта OLE.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COleClientItem::ItemState** перечисленное значение, которое может принимать одно из следующих действий: `emptyState`, **loadedState**, `openState`, `activeState`, `activeUIState`. Дополнительные сведения об этих состояниях см. в статье [контейнеров: состояния клиентских элементов](../../mfc/containers-client-item-states.md).  
  
### <a name="remarks"></a>Примечания  
 Чтобы получать уведомления при изменении состояния объекта OLE, используйте [OnChange](#onchange) функции-члена.  
  
 Дополнительные сведения см. в статье [контейнеров: состояния клиентских элементов](../../mfc/containers-client-item-states.md).  
  
##  <a name="getlaststatus"></a>COleClientItem::GetLastStatus  
 Возвращает код состояния последней операции OLE.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `SCODE`.  
  
### <a name="remarks"></a>Примечания  
 Для члена функции, которые возвращают **BOOL** значение **FALSE**, или другой член функции, которые возвращают **NULL**, `GetLastStatus` возвращает более подробные сведения об ошибке. Имейте в виду, что большинство функций-членов OLE исключений для более серьезных ошибок. Подробные сведения о Интерпретация `SCODE` зависит от базового вызова OLE, возвращается последнее `SCODE` значение.  
  
 Дополнительные сведения о `SCODE`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] документации.  
  
##  <a name="getlinkupdateoptions"></a>COleClientItem::GetLinkUpdateOptions  
 Эта функция вызывается для получения текущего значения параметра обновление связи для объекта OLE.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
- `OLEUPDATE_ALWAYS`Обновите связанный элемент, когда это возможно. Этот параметр поддерживает автоматическое обновление связи переключатель в диалоговом окне связи.  
  
- `OLEUPDATE_ONCALL`Обновить связанный элемент только по запросу приложения-контейнера (если [UpdateLink](#updatelink) вызывается функция-член). Этот параметр поддерживает переключатель ссылку обновления вручную в диалоговом окне связи.  
  
### <a name="remarks"></a>Примечания  
 Это является сложной операцией.  
  
 Эта функция вызывается автоматически [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) класса.  
  
 Дополнительные сведения см. в разделе [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettype"></a>COleClientItem::GetType  
 Эта функция вызывается для определения является внедренным или связанным объекта OLE или static.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число без знака с одним из следующих значений:  
  
- `OT_LINK`Элемент OLE является ссылкой.  
  
- `OT_EMBEDDED`Внедренного объекта OLE.  
  
- `OT_STATIC`Элемент OLE является статическим, то есть, содержит только представления, данные не в машинном коде и таким образом, не могут быть изменены.  
  
##  <a name="getusertype"></a>COleClientItem::GetUserType  
 Эта функция вызывается для получения видимыми строка, описывающая тип объекта OLE, например «Документ Word».  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>Параметры  
 *nUserClassType*  
 Значение, указывающее нужный вариант строка, описывающая тип объекта OLE. Это может иметь одно из следующих значений:  
  
- `USERCLASSTYPE_FULL`Полное имя типа для пользователя.  
  
- `USERCLASSTYPE_SHORT`Короткое имя (не более&15; знаков) для использования в всплывающих меню и в диалоговом окне Изменение связей.  
  
- `USERCLASSTYPE_APPNAME`Имя класса обслуживания приложения.  
  
 `rString`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, в который возвращается строка, описывающая тип объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Часто это является запись в системную базу данных регистрации.  
  
 Если полное имя запрошенного, но недоступен, вместо него используется короткое имя. Если нет записи для типа элемента OLE не найден в базе данных регистрации, или если типы не пользователь, зарегистрированный для данного типа объекта OLE, затем пользовательский тип хранящихся в используется объекта OLE. Если имя типа этого пользователя является пустой строкой, используется «Неизвестный объект».  
  
 Дополнительные сведения см. в разделе [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isinplaceactive"></a>COleClientItem::IsInPlaceActive  
 Эта функция вызывается для ли элемент OLE активным на месте.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент OLE является активным на месте; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чаще всего выполнить ту или иную логику в зависимости от того, было ли элемент редактируется на месте. Функция проверяет, равен ли текущее состояние элемента либо `activeState` или `activeUIState`.  
  
##  <a name="islinkuptodate"></a>COleClientItem::IsLinkUpToDate  
 Эта функция вызывается для объекта OLE ли обновлены.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент OLE актуальны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Связанный элемент может устареть, если его исходный документ был обновлен. Внедренный элемент, содержащий ссылки в нем можно аналогичным образом устареть. Функция выполняет проверку рекурсивного элемента OLE. Обратите внимание, что определить, является ли элемент OLE истек срок может быть дорогостоящим, чем фактически выполняет обновление.  
  
 Это называется автоматически [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) реализации.  
  
 Дополнительные сведения см. в разделе [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ismodified"></a>COleClientItem::IsModified  
 Эта функция вызывается для объекта OLE ли «грязный» (изменен с момента последнего сохранения).  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент OLE изменено; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isopen"></a>COleClientItem::IsOpen  
 Эта функция вызывается для объекта OLE ли открытым; то есть открыт в экземпляре серверное приложение, выполняющееся в отдельном окне.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент OLE открыт; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Он используется для определения времени рисования объекта с шаблон штриховки. Открытый объект должен иметь штриховая рисуется поверх объекта. Можно использовать [CRectTracker](../../mfc/reference/crecttracker-class.md) объект для выполнения этой задачи.  
  
##  <a name="isrunning"></a>COleClientItem::IsRunning  
 Вызывайте эту функцию, чтобы увидеть, работает ли элемент OLE; является ли элемент является загружен и запущен в серверном приложении.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент OLE выполняется; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onactivate"></a>COleClientItem::OnActivate  
 Вызывается платформой для уведомления элемента, что она только что была активирована на месте.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция вызывается для указания, что сервер работает не для того, чтобы указать, что пользовательский интерфейс был установлен в приложение контейнера. На этом этапе объект не имеет активных пользовательский интерфейс (не `activeUIState`). Она не установлена его меню или панели инструментов. [OnActivateUI](#onactivateui) функция-член вызывается, когда это происходит.  
  
 Реализация по умолчанию вызывает [OnChange](#onchange) функция-член с **OLE_CHANGEDSTATE** как параметр. Переопределите эту функцию для выполнения специальной обработки, когда элемент становится активным на месте.  
  
##  <a name="onactivateui"></a>COleClientItem::OnActivateUI  
 Платформа вызывает функцию `OnActivateUI` , когда объект вводятся в активное состояние пользовательского интерфейса.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>Примечания  
 Объект теперь установила его панели инструментов и меню.  
  
 Реализация по умолчанию запоминает сервера `HWND` позже **GetServerWindow** вызовов.  
  
##  <a name="onchange"></a>COleClientItem::OnChange  
 Вызывается платформой, когда пользователь изменяет, сохраняет или закрывает элемент OLE.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>Параметры  
 `nCode`  
 Причина сервера изменен этот элемент. Он может принимать одно из следующих значений:  
  
- `OLE_CHANGED`Внешний вид элемента OLE изменился.  
  
- `OLE_SAVED`Элемент OLE была сохранена.  
  
- `OLE_CLOSED`Элемент OLE был закрыт.  
  
- `OLE_CHANGED_STATE`Элемент OLE был изменен из одного состояния в другое.  
  
 `dwParam`  
 Если `nCode` — `OLE_SAVED` или `OLE_CLOSED`, этот параметр не используется. Если `nCode` — `OLE_CHANGED`, этот параметр указывает аспект объекта OLE, которая была изменена. Возможные значения см. в разделе `dwParam` параметр [COleClientItem::Draw](#draw). Если `nCode` — `OLE_CHANGED_STATE`, этот параметр является **COleClientItem::ItemState** значение перечисления и описывает состояние вводится. Он может иметь одно из следующих значений: `emptyState`, **loadedState**, `openState`, `activeState`, или `activeUIState`.  
  
### <a name="remarks"></a>Примечания  
 (Если серверное приложение создано с использованием библиотеки Microsoft Foundation Class, эта функция вызывается в ответ на `Notify` функции-члены `COleServerDoc` или `COleServerItem`.) Реализация по умолчанию отмечает контейнер документ как измененный, если `nCode` — `OLE_CHANGED` или `OLE_SAVED`.  
  
 Для `OLE_CHANGED_STATE`, текущее состояние, возвращаемое из [GetItemState](#getitemstate) по-прежнему будет старое состояние, то есть состояние, которая была текущей до этого изменения состояния.  
  
 Переопределите эту функцию для реагирования на изменения в состоянии объекта OLE. Обычно обновлении внешнего вида элемента недействительный область, в котором отображается элемент. Вызовите реализацию базового класса в начале переопределения.  
  
##  <a name="onchangeitemposition"></a>COleClientItem::OnChangeItemPosition  
 Вызывается платформой для уведомления контейнер, в котором элемент OLE экстент был изменен во время активации на месте.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>Параметры  
 *rectPos*  
 Указывает позицию элемента относительно клиентской области его контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если позиции элемента успешно изменен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию определяет новый прямоугольник видимым элемент OLE и вызовы [SetItemRects](#setitemrects) с новыми значениями. Реализация по умолчанию вычисляет Видимый прямоугольник для элемента и передает эти сведения на сервер.  
  
 Переопределите эту функцию, чтобы применить специальные правила для операции изменения размера или перемещения. Если приложение написано в MFC, этот вызов приводит, так как сервер называется [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange).  
  
##  <a name="ondeactivate"></a>COleClientItem::OnDeactivate  
 Вызывается инфраструктурой при переходе объекта OLE из активного состояния на месте ( `activeState`) в загруженное состояние, это означает, что отключена после активации на месте.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что эта функция вызывается для указания, что элемент OLE закрывается, не, его пользовательский интерфейс был удален из приложения-контейнера. Когда это происходит, [OnDeactivateUI](#ondeactivateui) вызывается функция-член.  
  
 Реализация по умолчанию вызывает [OnChange](#onchange) функция-член с **OLE_CHANGEDSTATE** как параметр. Переопределите эту функцию для выполнения специальной обработки при отключении активного элемента на месте. Например если требуется поддержка команды undo в приложения-контейнера, можно переопределить эту функцию для отклонения состояния отмены, указывающее, что последняя операция, выполненная на элемент OLE нельзя отменить после отключения элемента.  
  
##  <a name="ondeactivateandundo"></a>COleClientItem::OnDeactivateAndUndo  
 Вызывается платформой, когда пользователь вызывает команду отмены после активации элемента OLE на месте.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [DeactivateUI](#deactivateui) отключить пользовательский интерфейс сервера. При реализации в приложении контейнера команды undo переопределите эту функцию. Во время переопределения вызывать версию базовый класс функции, а затем отменить последнюю команду, выполняется в приложении.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondeactivateui"></a>COleClientItem::OnDeactivateUI  
 Вызывается, когда пользователь отключает элемент, который был активирован на месте.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Параметры  
 `bUndoable`  
 Указывает, являются ли отменяемой внесения изменений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция восстанавливает пользовательский интерфейс приложения-контейнера в исходное состояние, скрывая все меню и других элементов управления, которые были созданы для активации на месте.  
  
 Если `bUndoable` — **FALSE**, контейнер следует отключить команды undo, фактически удаляя состояния отмены контейнера, поскольку он указывает, что последняя операция, выполненная на сервере не удастся.  
  
##  <a name="ondiscardundostate"></a>COleClientItem::OnDiscardUndoState  
 Вызывается платформой, когда пользователь выполняет действие, которое сбрасывает состояние отмены при редактировании объекта OLE.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. При реализации в приложении контейнера команды undo переопределите эту функцию. Во время переопределения отклонения состояния отмены приложения-контейнера.  
  
 Если сервер был записан с помощью библиотеки Microsoft Foundation Class, сервер может привести к этой функции, которая вызывается путем вызова [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate).  
  
 Дополнительные сведения см. в разделе [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ongetclipboarddata"></a>COleClientItem::OnGetClipboardData  
 Вызывается платформой для получения `COleDataSource` объект, содержащий все данные, которые следует поместить в буфер обмена с помощью вызова либо [CopyToClipboard](#copytoclipboard) или [DoDragDrop](#dodragdrop) функции-члена.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Параметры  
 `bIncludeLink`  
 Задайте значение **TRUE** Если ссылку данные должны быть скопированы в буфер обмена. Задайте значение **FALSE** Если серверное приложение не поддерживает ссылки.  
  
 `lpOffset`  
 Указатель на смещение указателя мыши от начала координат объекта в пикселях.  
  
 `lpSize`  
 Указатель на размер объекта в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные из буфера обмена.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetcliprect"></a>COleClientItem::OnGetClipRect  
 Платформа вызывает функцию `OnGetClipRect` функции-члена для получения координат прямоугольник отсечения изменяемого элемента на месте.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>Параметры  
 *rClipRect*  
 Указатель на объект класса [CRect](../../atl-mfc-shared/reference/crect-class.md) , будет содержать прямоугольник отсечения координаты элемента.  
  
### <a name="remarks"></a>Примечания  
 Координаты измеряются в пикселях относительно клиентской области окна приложения контейнера.  
  
 Реализация по умолчанию просто возвращает клиентскую область представления, в котором элемент является активным на месте.  
  
##  <a name="ongetitemposition"></a>COleClientItem::OnGetItemPosition  
 Платформа вызывает функцию `OnGetItemPosition` функции-члена для получения координаты элемента, который редактируется на месте.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, который будет содержать координаты положения элемента.  
  
### <a name="remarks"></a>Примечания  
 Координаты измеряются в пикселях относительно клиентской области окна приложения контейнера.  
  
 Реализация по умолчанию этой функции не выполняет никаких действий. Приложения, которые поддерживают изменение на месте требуется его реализации.  
  
##  <a name="ongetwindowcontext"></a>COleClientItem::OnGetWindowContext  
 Вызывается инфраструктурой при активизации элемента на месте.  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `ppMainFrame`  
 Указатель на указатель фрейма главного окна.  
  
 `ppDocFrame`  
 Указатель на указатель на окно фрейма документа.  
  
 `lpFrameInfo`  
 Указатель на [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) структуру, которая будет получать сведения о кадре окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения информации о родительском окне объекта OLE.  
  
 Если контейнер является MDI-приложения, реализация по умолчанию возвращает указатель на [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) объекта в `ppMainFrame` и указатель на активный [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта в `ppDocFrame`. Если контейнер является приложением с интерфейсом SDI, реализация по умолчанию возвращает указатель на [CFrameWnd](../../mfc/reference/cframewnd-class.md) объекта в `ppMainFrame` и возвращает **NULL** в `ppDocFrame`. Реализация по умолчанию, а также заполняет элементы `lpFrameInfo`.  
  
 Переопределить эту функцию только в том случае, если реализация по умолчанию не соответствуют приложения; Например, если приложение имеет пользовательский интерфейс парадигма, которая отличается от SDI или интерфейса MDI. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceSite::GetWindowContext](http://msdn.microsoft.com/library/windows/desktop/ms694366) и [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oninsertmenus"></a>COleClientItem::OnInsertMenus  
 Вызывается средой во время активации на месте для вставки меню приложения-контейнера в пустое меню.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>Параметры  
 `pMenuShared`  
 Указывает на пустое меню.  
  
 `lpMenuWidths`  
 Указывает на массив из шести **ДЛИННЫЕ** значений, указывающее, сколько меню в каждом из следующих групп меню: файл, изменить, контейнер объекта окна справки. Приложения-контейнера, отвечает за файл, контейнер и окно группы меню, соответствующие элементам, 0, 2 и 4 данного массива.  
  
### <a name="remarks"></a>Примечания  
 Это меню, затем передается на сервер, который вставляет собственные меню, создание составного меню. Эта функция может вызываться несколько раз для построения несколько составного меню.  
  
 Реализация по умолчанию вставляет в `pMenuShared` меню контейнера на месте, то есть группы меню файл, контейнер и окна. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) используется для задания этого ресурса меню. Реализация по умолчанию также устанавливает соответствующие значения для элементов, 0, 2 и 4 в `lpMenuWidths`, в зависимости от ресурсов меню. Переопределить эту функцию, если реализация по умолчанию не подходит для вашего приложения; Например, если приложение не использует шаблоны документов для сопоставления ресурсов с помощью типов документов. Если переопределить эту функцию, необходимо переопределить [OnSetMenu](#onsetmenu) и [OnRemoveMenus](#onremovemenus). Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onremovemenus"></a>COleClientItem::OnRemoveMenus  
 Вызывается платформой для удаления контейнера меню из указанного составного меню при завершении активации на месте.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>Параметры  
 `pMenuShared`  
 Указывает составного меню, созданный путем вызова [OnInsertMenus](#oninsertmenus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию удаляет из `pMenuShared` меню на месте контейнера, которая является, файл, контейнер и окно группы меню. Переопределить эту функцию, если реализация по умолчанию не подходит для вашего приложения; Например, если приложение не использует шаблоны документов для сопоставления ресурсов с помощью типов документов. Если переопределить эту функцию, возможно, необходимо переопределить [OnInsertMenus](#oninsertmenus) и [OnSetMenu](#onsetmenu) также. Существует расширенная переопределяемыми.  
  
 Подменю на `pMenuShared` может быть общим для нескольких составного меню, если сервер несколько раз вызывается `OnInsertMenus`. Поэтому не следует удалять вложенные в переопределении `OnRemoveMenus`; необходимо только отключать их.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onscrollby"></a>COleClientItem::OnScrollBy  
 Вызывается платформой для прокрутки элемента OLE в ответ на запросы с сервера.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>Параметры  
 *sizeExtent*  
 Указывает расстояния, в пикселях, для прокрутки в x и y направлениях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был прокрутку; 0, если не выполнить прокрутку элемента.  
  
### <a name="remarks"></a>Примечания  
 Например если пользователь перемещает указатель за пределы видимой области во время выполнения редактирования на месте элемент OLE частично видимой, эта функция вызывается для отображение курсора. Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для прокрутки элемента на заданную величину. Обратите внимание, что в результате прокрутки, видимую часть объекта OLE можно изменить. Вызов [SetItemRects](#setitemrects) обновление элемента Видимый прямоугольник.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onsetmenu"></a>COleClientItem::OnSetMenu  
 Вызывается платформой два раза при активации на месте начинается и заканчивается; в первый раз, чтобы установить составного меню и второй раз (с `holemenu` равно **NULL**) для его удаления.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pMenuShared`  
 Указатель на составного меню, созданный путем вызова [OnInsertMenus](#oninsertmenus) функции-члена и `InsertMenu` функции.  
  
 `holemenu`  
 Дескриптор меню дескриптор, возвращенный **OleCreateMenuDescriptor** функция, или **NULL** при диспетчеризации кода должны быть удалены.  
  
 *hwndActiveObject*  
 Дескриптор окна редактирования для объекта OLE. Это окно, которое будет получать команд редактирования из OLE.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию устанавливает или удаляет составного меню, а затем вызывает [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831) функции для установки или удаления диспетчеризации кода. Переопределите эту функцию, если реализация по умолчанию не подходит для вашего приложения. Если переопределить эту функцию, возможно, необходимо переопределить [OnInsertMenus](#oninsertmenus) и [OnRemoveMenus](#onremovemenus) также. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415), [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831), и [IOleInPlaceFrame::SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onshowcontrolbars"></a>COleClientItem::OnShowControlBars  
 Вызывается платформой для отображения и скрытия панели элементов управления приложения-контейнера.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrameWnd`  
 Указатель фрейма окна приложения-контейнера. Это может быть фрейма главного окна или дочернего окна MDI.  
  
 `bShow`  
 Указывает ли панелей элементов управления должны быть отображены или скрыты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов функции приводит к изменению в состоянии панели элементов управления; 0, если в результате вызова не меняется или `pFrameWnd` не указывает на фрейм окна контейнера.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает 0, если панелей элементов управления уже находятся в состоянии, указанном в *bShow.* Это происходит, например, если скрыты панели элементов управления и `bShow` — **FALSE**.  
  
 Реализация по умолчанию удаляет панели инструментов в окне фрейма верхнего уровня.  
  
##  <a name="onshowitem"></a>COleClientItem::OnShowItem  
 Вызывается платформой для отображения объекта OLE, станет полностью видимым во время редактирования.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>Примечания  
 Он используется, когда приложение контейнера поддерживает ссылки на внедренные элементы (то есть, если производного класса документа из [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). Эта функция вызывается во время активации на месте или в элемент OLE источник связи, и пользователь хочет изменить его. Реализация по умолчанию активирует первое представление в документе-контейнере. Переопределите эту функцию для прокрутки документа, чтобы была видна объекта OLE.  
  
##  <a name="onupdateframetitle"></a>COleClientItem::OnUpdateFrameTitle  
 Вызывается средой во время активации на месте для обновления заголовка рамки окна.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эта функция успешно обновлены название рамки, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не изменяет заголовок окна фрейма. Переопределить эту функцию, если требуется другой кадр заголовок для вашего приложения, например « *серверного приложения* - *элемент* в *имя_документа*» (как, «Microsoft Excel — электронной таблицы в отчете. ДОКУМЕНТ»). Существует расширенная переопределяемыми.  
  
##  <a name="reactivateandundo"></a>COleClientItem::ReactivateAndUndo  
 Эта функция вызывается для повторной активации элемента OLE и отменить последняя операция, выполненная пользователем во время редактирования на месте.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если ваше приложение контейнера поддерживает команды undo, эта функция вызывается при выборе команды «Отменить» сразу после деактивации объекта OLE.  
  
 Если серверное приложение написано с помощью библиотек классов Microsoft Foundation, эта функция приводит вызвать [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo).  
  
 Дополнительные сведения см. в разделе [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="release"></a>COleClientItem::Release  
 Эта функция вызывается для очистки ресурсов, используемых объектом OLE.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCloseOption`  
 Флаг, указывающий, при каких обстоятельствах объекта OLE сохраняется при возвращении в загруженное состояние. Список возможных значений см. в разделе [COleClientItem::Close](#close).  
  
### <a name="remarks"></a>Примечания  
 **Выпуск** вызывается `COleClientItem` деструктор.  
  
 Дополнительные сведения см. в разделе [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="reload"></a>COleClientItem::Reload  
 Закрытие и повторная загрузка элемента.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов `Reload` функции после активации элемента как элемент другого типа путем вызова [ActivateAs](#activateas).  
  
##  <a name="run"></a>COleClientItem::Run  
 Запускает приложение, связанное с этим элементом.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов **запуска** запустить приложение сервера перед активацией элемента функция-член. Это делается автоматически [активировать](#activate) и [DoVerb](#doverb), поэтому он обычно нет необходимости вызывать данную функцию. Эта функция вызывается, если это необходимо для запуска сервера, чтобы задать атрибут элемента, такие как [SetExtent](#setextent), перед выполнением [DoVerb](#doverb).  
  
##  <a name="setdrawaspect"></a>COleClientItem::SetDrawAspect  
 Вызов `SetDrawAspect` функции-члена для задания «аспект» или отображения элемента.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Значение из перечисления `DVASPECT`. Этот параметр может принимать одно из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Пропорции определяет, как элемент должен быть обработан [рисовать](#draw) при значение по умолчанию для этой функции `nDrawAspect` используется аргумент.  
  
 Эта функция вызывается автоматически изменить значок (и других диалоговых окон, напрямую вызывать диалоговое окно Изменить значок) для включения аспект значками отображения при запросе пользователем.  
  
##  <a name="setextent"></a>COleClientItem::SetExtent  
 Эта функция используется для указания того, сколько места доступно для объекта OLE.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий сведения о размере.  
  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого должны быть заданы. Возможные значения см. в разделе [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Примечания  
 Если серверное приложение было написано с помощью библиотеки Microsoft Foundation Class, в результате [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) функции-члена соответствующего `COleServerItem` вызов объекта. Элемент OLE затем соответствующим образом настроить его отображение. Размер должен быть в `MM_HIMETRIC` единиц. Эта функция вызывается при изменении пользователем размера объекта OLE или если требуется поддержка какого-либо рода Согласование макета.  
  
 Дополнительные сведения см. в разделе [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sethostnames"></a>COleClientItem::SetHostNames  
 Эта функция используется для указания имени приложения-контейнера и имя контейнера для встроенного элемента OLE.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszHost`  
 Указатель на видимое пользователю имя приложения-контейнера.  
  
 `lpszHostObj`  
 Указатель на строку идентификации контейнера, который содержит элемент OLE.  
  
### <a name="remarks"></a>Примечания  
 Если серверное приложение было написано с помощью библиотеки Microsoft Foundation Class, эта функция вызывает функцию [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) функцию-член `COleServerDoc` документ, который содержит элемент OLE. Эта информация используется в заголовки окон, при редактировании объекта OLE. Каждый раз загружается контейнера документа, платформа вызывает эту функцию для всех элементов в документе OLE. `SetHostNames`применим только для встроенных элементов. Эта функция вызывается каждый раз активируется встроенного элемента OLE для редактирования необязательно.  
  
 Это также называется автоматически с именем приложения и имя документа при загрузке объекта или при сохранении файла под другим именем. Соответственно не обычно требуется напрямую вызывать эту функцию.  
  
 Дополнительные сведения см. в разделе [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="seticonicmetafile"></a>COleClientItem::SetIconicMetafile  
 Кэширует метафайла, используемую для рисования на значок элемента.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>Параметры  
 `hMetaPict`  
 Дескриптор метафайла, используемую для рисования на значок элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте [GetIconicMetafile](#geticonicmetafile) для получения метафайл.  
  
 `hMetaPict` Параметр копируется в элемент; таким образом, `hMetaPict` должен быть освобожден вызывающим объектом.  
  
##  <a name="setitemrects"></a>COleClientItem::SetItemRects  
 Эта функция вызывается для ограничивающего прямоугольника или Видимый прямоугольник элемента OLE.  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lprcPosRect*  
 Указатель на прямоугольник, содержащий границы элемента относительно его родительского окна в координатах клиента OLE.  
  
 *lprcClipRect*  
 Указатель на прямоугольник, содержащий границы видимой части OLE элемента относительно его родительского окна в координатах клиента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается реализация по умолчанию [OnChangeItemPosition](#onchangeitemposition) функции-члена. Эту функцию следует вызывать каждый раз, когда положения или видимую часть OLE элемент изменений. Обычно это означает вызов из вашего представления [OnSize](../../mfc/reference/cwnd-class.md#onsize) и [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) функции-члены.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlinkupdateoptions"></a>COleClientItem::SetLinkUpdateOptions  
 Эта функция вызывается для задания параметра обновление связи для представления указанного связанного элемента.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>Параметры  
 *dwUpdateOpt*  
 Значение параметра обновление связи для этого элемента. Это значение должно быть одним из следующих:  
  
- `OLEUPDATE_ALWAYS`Обновите связанный элемент, когда это возможно. Этот параметр поддерживает автоматическое обновление связи переключатель в диалоговом окне связи.  
  
- `OLEUPDATE_ONCALL`Обновить связанный элемент только по запросу приложения-контейнера (если [UpdateLink](#updatelink) вызывается функция-член). Этот параметр поддерживает переключатель ссылку обновления вручную в диалоговом окне связи.  
  
### <a name="remarks"></a>Примечания  
 Как правило не изменяйте параметры обновления, выбранного пользователем в диалоговом окне связи.  
  
 Дополнительные сведения см. в разделе [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setprintdevice"></a>COleClientItem::SetPrintDevice  
 Эта функция вызывается для печати целевое устройство для этого элемента изменить.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Параметры  
 `ptd`  
 Указатель на [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуру данных, которая содержит сведения о новых печати целевого устройства. Может быть **NULL**.  
  
 `ppd`  
 Указатель на [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940) структуру данных, которая содержит сведения о новых печати целевого устройства. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обновляет печати целевое устройство для элемента, но не обновляет кэш презентации. Чтобы обновить кэш презентации для элемента, вызовите [UpdateLink](#updatelink).  
  
 Аргументов для этой функции содержат информацию, системы OLE использует для идентификации целевого устройства. **PRINTDLG** структура содержит данные, используемые для инициализации общее диалоговое окно печати. После пользователь закроет диалоговое окно, Windows возвращает сведения о выбранных пользователем в этой структуре. `m_pd` Членом [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объект **PRINTDLG** структуры.  
  
 Дополнительные сведения об этой структуры см. в разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="updatelink"></a>COleClientItem::UpdateLink  
 Эта функция вызывается для немедленного обновления данных представления элемента OLE.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Для связанных элементов функция находит источник связи для получения нового представления для объекта OLE. Этот процесс может потребоваться запуск одного или нескольких серверных приложений, которые может занять много времени. Для встроенных элементов функция применяется рекурсивно, проверка, содержит ли встроенного элемента ссылки, которые могут быть устаревшими и их обновления. Пользователь может также вручную обновить отдельные ссылки с помощью диалогового окна связи.  
  
 Дополнительные сведения см. в разделе [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCBIND](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс CDocItem](../../mfc/reference/cdocitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класса, производного от COleServerItem](../../mfc/reference/coleserveritem-class.md)

