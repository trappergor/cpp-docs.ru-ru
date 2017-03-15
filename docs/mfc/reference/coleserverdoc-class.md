---
title: "Класс COleServerDoc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerDoc
dev_langs:
- C++
helpviewer_keywords:
- servers, OLE
- OLE server applications, managing server documents
- container/server applications
- OLE server documents
- COleServerDoc class
- server documents, OLE
- OLE containers, server documents
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
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
ms.openlocfilehash: db50c2a5709fbc07d0e0db99a4cffc733c4b6ead
ms.lasthandoff: 02/24/2017

---
# <a name="coleserverdoc-class"></a>Класс COleServerDoc
Базовый класс для серверной документации OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Создает объект `COleServerDoc`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Активируется связанный документ DocObject.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Активирует документ для редактирования на месте.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Отключает пользовательский интерфейс сервера.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Удаляет сведения состояния отмены.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Извлекает указатель на базовый `IOleClientSite` интерфейса.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Возвращает указатель на элемент, представляющий весь документ.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Возвращает текущий прямоугольник отсечения для редактирования на месте.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Возвращает текущий прямоугольник позиции относительно клиентской области приложения-контейнера для редактирования на месте.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Возвращает значение масштаба в пикселях.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Определяет, является ли документ DocObject.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Указывает, внедренный в документе-контейнере или выполнение автономного документа.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Возвращает `TRUE` , если элемент в настоящее время активации на месте.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Уведомляет контейнеры, что пользователь изменил документа.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Уведомляет контейнеры, что пользователь закрыл документа.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Уведомляет контейнеры, пользователь переименовала документа.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Уведомляет контейнеры, что пользователь сохранил документ.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Вызывается платформой, когда пользователь отключает элемент, который был активирован на месте.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Вызывается платформой для уничтожения элементов управления и других элементов пользовательского интерфейса, созданный для активации на месте.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Вызывается инфраструктурой при контейнера документа фрейм окна, активируется или деактивируется.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Вызывается инфраструктурой при изменении размера окна фрейма или окна документа приложения-контейнера.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Вызывается платформой для отображения или скрытия панели элементов управления для редактирования на месте.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Вызывается инфраструктурой при сохранении документа сервера, являющегося встроенного элемента обновление копии контейнера элемента.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Изменение положения фрейма редактирования на месте.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Указывает приложения-контейнера, чтобы сохранить документ.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Прокручивает документе-контейнере.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Уведомляет контейнеры, что пользователь изменил документа.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Вызывается платформой для создания окна фрейма для редактирования на месте.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Вызывается платформой для уничтожения рамку окна для редактирования на месте.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Переопределить эту функцию для создания нового `CDocObjectServer` объекта и указывают, что этот документ является контейнером DocObject.|  
|[COleServerDoc::OnClose](#onclose)|Вызывается платформой, когда контейнер запрашивает закройте документ.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Выполняет указанную команду или отображает справку по команде.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Вызывается инфраструктурой при контейнера фрейм окна, активируется или деактивируется.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Вызывается для получения `COleServerItem` представляет весь документ; используется для получения встроенного элемента. Требуется реализация.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Вызывается средой, чтобы отменить изменения, внесенные во время редактирования на месте.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Вызывается платформой, когда контейнер задает заголовок окна для внедренного объекта.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Вызывается платформой для размещения окна фрейма на месте для редактирования в окне приложения-контейнера.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Вызывается платформой для отображения или скрытия документа.|  
  
## <a name="remarks"></a>Примечания  
 Серверный документ может содержать [производного от COleServerItem](../../mfc/reference/coleserveritem-class.md) объекты, которые представляют собой интерфейс сервером внедренные или связанные элементы. При запуске серверного приложения контейнером для редактирования внедренного элемента элемент загружается как свой собственный серверный документ; `COleServerDoc` объект содержит только один `COleServerItem` объект, состоящий из всего документа. При запуске серверного приложения в контейнере, чтобы изменить связанный элемент существующий документ загружается с диска; часть содержимого документа будет выделен для обозначения связанного элемента.  
  
 `COleServerDoc`объекты также могут содержать элементы [COleClientItem](../../mfc/reference/coleclientitem-class.md) класса. Это позволяет создать контейнер серверных приложений. Платформа предоставляет функции, чтобы правильно сохранить `COleClientItem` элементы во время обслуживания `COleServerItem` объектов.  
  
 Если серверное приложение не поддерживает ссылки, серверного документа всегда будет содержать только один серверный элемент, который представляет весь внедренный объект как документ. Если приложение сервера поддерживает ссылки, его необходимо создать серверный элемент каждый раз, когда выбор копируется в буфер обмена.  
  
 Для использования `COleServerDoc`, создайте класс, производный от него и реализовать [OnGetEmbeddedItem](#ongetembeddeditem) функция-член, что позволяет серверу для поддержки встроенных элементов. Производный класс от `COleServerItem` для реализации элементов в документах и возврата объектов этого класса из `OnGetEmbeddedItem`.  
  
 Для поддержки связанных элементов `COleServerDoc` предоставляет [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) функции-члена. Можно использовать реализацию по умолчанию, или переопределить его, если у вас есть собственный способ управления элементов документа.  
  
 Требуется один `COleServerDoc`-производный класс для каждого типа сервера документов, поддерживаемых приложением. Например, если приложение сервера поддерживает листов и диаграмм, необходимы два `COleServerDoc`-производные классы.  
  
 Дополнительные сведения о серверах см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-nameactivatedocobjecta--coleserverdocactivatedocobject"></a><a name="activatedocobject"></a>COleServerDoc::ActivateDocObject  
 Активируется связанный документ DocObject.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `COleServerDoc` не поддерживает активных документов (также известной как DocObjects). Для включения такой поддержки, в разделе [GetDocObjectServer](#getdocobjectserver) и класс [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="a-nameactivateinplacea--coleserverdocactivateinplace"></a><a name="activateinplace"></a>COleServerDoc::ActivateInPlace  
 Активирует элемент для редактирования на месте.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0, что свидетельствует о элемент полностью открытыми.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняет все операции, необходимые для активации на месте. Он создает окно фрейма на месте, она активируется и размеров его к элементу, настраивает общий меню и других элементов управления, прокрутке элемента и устанавливает фокус ввода в окне фрейма на месте.  
  
 Эта функция вызывается реализация по умолчанию [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Эта функция вызывается в том случае, если приложение поддерживает другую команду для активации на месте (например, воспроизведение).  
  
##  <a name="a-namecoleserverdoca--coleserverdoccoleserverdoc"></a><a name="coleserverdoc"></a>COleServerDoc::COleServerDoc  
 Создает `COleServerDoc` объекта без соединения с OLE системные библиотеки DLL.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) для связи с OLE. При использовании [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) в приложении, `COleLinkingDoc::Register` вызывается для вас `COleLinkingDoc`реализация `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
##  <a name="a-namecreateinplaceframea--coleserverdoccreateinplaceframe"></a><a name="createinplaceframe"></a>COleServerDoc::CreateInPlaceFrame  
 Платформа вызывает эту функцию для создания окна фрейма для редактирования на месте.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно приложения-контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно фрейма на месте или **NULL** в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию использует сведения, указанные в шаблоне документа для создания фрейма. Представление, используемое является первое представление, созданные для документа. В этом представлении ссылку на только что созданный кадра и временно отсоединить от исходного кадра.  
  
 Существует расширенная переопределяемыми.  
  
##  <a name="a-namedeactivateandundoa--coleserverdocdeactivateandundo"></a><a name="deactivateandundo"></a>COleServerDoc::DeactivateAndUndo  
 Эта функция вызывается в том случае, если отменить поддерживаемых приложением, и пользователь нажимает кнопку отмены после активации элемента, но перед его изменением.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Запись приложения-контейнера с помощью библиотеки Microsoft Foundation Class, вызов этой функции приводит к [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) вызов, который отключает пользовательский интерфейс сервера.  
  
##  <a name="a-namedestroyinplaceframea--coleserverdocdestroyinplaceframe"></a><a name="destroyinplaceframe"></a>COleServerDoc::DestroyInPlaceFrame  
 Платформа вызывает эту функцию для уничтожении окна фрейма на месте и вернуть сервер в окне документа приложения в состояние до выполнения активации на месте.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrameWnd`  
 Указатель фрейма на месте окна будут уничтожены.  
  
### <a name="remarks"></a>Примечания  
 Существует расширенная переопределяемыми.  
  
##  <a name="a-namediscardundostatea--coleserverdocdiscardundostate"></a><a name="discardundostate"></a>COleServerDoc::DiscardUndoState  
 Если пользователь выполняет операцию редактирования, который не может быть отменено, эта функция вызывается для принудительного приложения-контейнера, отменить ее состояния отмены.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обеспечивает, чтобы серверы, поддерживающие отмены можно освободить ресурсы, которые в противном случае будет использоваться сведения о состоянии отмены, не может использоваться.  
  
##  <a name="a-namegetclientsitea--coleserverdocgetclientsite"></a><a name="getclientsite"></a>COleServerDoc::GetClientSite  
 Извлекает указатель на базовый `IOleClientSite` интерфейса.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель на базовый [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) интерфейса.  
  
##  <a name="a-namegetdocobjectservera--coleserverdocgetdocobjectserver"></a><a name="getdocobjectserver"></a>COleServerDoc::GetDocObjectServer  
 Переопределить эту функцию для создания нового `CDocObjectServer` элемент и возвращает указатель на него.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Параметры  
 `pDocSite`  
 Указатель на `IOleDocumentSite` интерфейс, который будет подключиться к серверу в этом документе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CDocObjectServer`; **NULL** при сбое операции.  
  
### <a name="remarks"></a>Примечания  
 При активации сервера DocObject, возвращаемое отличного от **NULL** указатель мыши показывает, что клиент может поддерживать DocObjects. Реализация по умолчанию возвращает **NULL**.  
  
 Типичная реализация для документа, который поддерживает DocObjects просто выделить новый `CDocObjectServer` объекта и возвращения его вызывающему. Например:  
  
 [!code-cpp[NVC_MFCOleServer&#3;](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="a-namegetembeddeditema--coleserverdocgetembeddeditem"></a><a name="getembeddeditem"></a>COleServerDoc::GetEmbeddedItem  
 Эта функция вызывается для получения указателя на элемент, представляющий весь документ.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, представляющий весь документ; **NULL** при сбое операции.  
  
### <a name="remarks"></a>Примечания  
 Он вызывает [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), виртуальной функции без реализации по умолчанию.  
  
##  <a name="a-namegetitemcliprecta--coleserverdocgetitemcliprect"></a><a name="getitemcliprect"></a>COleServerDoc::GetItemClipRect  
 Вызов `GetItemClipRect` функции-члена для получения координат прямоугольник отсечения изменяемого элемента на месте.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpClipRect`  
 Указатель на `RECT` структуры или `CRect` объект для получения прямоугольник отсечения координаты элемента.  
  
### <a name="remarks"></a>Примечания  
 Координаты измеряются в пикселях относительно клиентской области окна приложения контейнера.  
  
 Рисование не должно возникать вне прямоугольник отсечения. Как правило документ автоматически ограничен. Эта функция позволяет определить, является ли пользователь прокручивает за пределы видимой области документа. в этом случае, прокрутите страницу контейнера документа с помощью вызова [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="a-namegetitempositiona--coleserverdocgetitemposition"></a><a name="getitemposition"></a>COleServerDoc::GetItemPosition  
 Вызов `GetItemPosition` функции-члена для получения координат изменяемый элемент на месте.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpPosRect`  
 Указатель на `RECT` структуры или `CRect` объект для получения координаты элемента.  
  
### <a name="remarks"></a>Примечания  
 Координаты измеряются в пикселях относительно клиентской области окна приложения контейнера.  
  
 Положение элемента можно сравнить с текущим прямоугольником отсечения, чтобы определить область, к которой элемент является видимым (или не отображается) на экране.  
  
##  <a name="a-namegetzoomfactora--coleserverdocgetzoomfactor"></a><a name="getzoomfactor"></a>COleServerDoc::GetZoomFactor  
 `GetZoomFactor` Функция-член определяет «масштаб» элемента, который был активирован для редактирования на месте.  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpSizeNum*  
 Указатель на объект класса `CSize` , будет содержать числитель коэффициента масштабирования. Может быть **NULL**.  
  
 *lpSizeDenom*  
 Указатель на объект класса `CSize` , будет содержать знаменатель коэффициента масштабирования. Может быть **NULL**.  
  
 `lpPosRect`  
 Указатель на объект класса `CRect` , описывающий новой позиции. Если этот аргумент равен **NULL**, функция использует текущую позицию элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент активируется для непосредственного редактирования и его масштаб отличается от 100% (1:1); в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Коэффициент масштабирования, в пикселях, представляет собой долю размера элемента в его текущем степени. Если приложение контейнера не задал степени элемента, его естественное экстент (что определяется [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) используется.  
  
 Эта функция устанавливает его первых двух аргументов для числителя и знаменателя элемента «коэффициент масштабирования.» Если элемент не редактируется на месте, функция присваивает значение по умолчанию 100% (или 1:1) эти аргументы и возвращает ноль. Дополнительные сведения см. в разделе 40 технических Обратите внимание, [MFC/OLE по месту изменение размеров и масштабирование](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="a-nameisdocobjecta--coleserverdocisdocobject"></a><a name="isdocobject"></a>COleServerDoc::IsDocObject  
 Определяет, является ли документ DocObject.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если документ является DocObject; в противном случае **FALSE**.  
  
##  <a name="a-nameisembeddeda--coleserverdocisembedded"></a><a name="isembedded"></a>COleServerDoc::IsEmbedded  
 Вызов `IsEmbedded` функцию-член, чтобы определить, представляет ли документ объекта, встроенного в контейнере.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `COleServerDoc` объект является документ, который представляет объект, внедренный в контейнере; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Документ, загруженный из файла не внедряются, несмотря на то, что он может управляться приложение контейнера как ссылка. Документ, который внедряется в документе-контейнере считается для внедрения.  
  
##  <a name="a-nameisinplaceactivea--coleserverdocisinplaceactive"></a><a name="isinplaceactive"></a>COleServerDoc::IsInPlaceActive  
 Вызов `IsInPlaceActive` функции-члена для определения того, находится ли элемент в активном состоянии на месте.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `COleServerDoc` объект является активным в месте; в противном случае — 0.  
  
##  <a name="a-namenotifychangeda--coleserverdocnotifychanged"></a><a name="notifychanged"></a>COleServerDoc::NotifyChanged  
 Эта функция вызывается для уведомления всех связанных элементов, подключенных к документу измененного документа.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Как правило эта функция вызывается, когда пользователь изменит некоторые глобальный атрибут, например измерений серверного документа. Если элемент OLE связан документ с автоматической связью, элемент обновляется для отражения изменений. В контейнере приложений, написанных с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
> [!NOTE]
>  Эта функция включена для совместимости с OLE 1. Новые приложения должны использовать [UpdateAllItems](#updateallitems).  
  
##  <a name="a-namenotifycloseda--coleserverdocnotifyclosed"></a><a name="notifyclosed"></a>COleServerDoc::NotifyClosed  
 Эта функция вызывается для уведомления контейнеры, что документ был закрыт.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает команду «Закрыть» из меню «Файл» `NotifyClosed` вызывается `COleServerDoc`реализация [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) функции-члена. В контейнере приложений, написанных с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
##  <a name="a-namenotifyrenamea--coleserverdocnotifyrename"></a><a name="notifyrename"></a>COleServerDoc::NotifyRename  
 Эта функция вызывается после пользователь переименовывает серверного документа.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszNewName`  
 Указатель на строку, указав имя нового сервера документа. Обычно это полный путь.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает команду Сохранить как в меню Файл `NotifyRename` вызывается `COleServerDoc`реализация [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) функции-члена. Эта функция уведомляет системы OLE библиотеки DLL, которые в свою очередь уведомление контейнеров. В контейнере приложений, написанных с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
##  <a name="a-namenotifysaveda--coleserverdocnotifysaved"></a><a name="notifysaved"></a>COleServerDoc::NotifySaved  
 Эта функция вызывается после пользователь сохраняет документ сервера.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает команду «Сохранить» из меню «Файл» `NotifySaved` вызывается для вас `COleServerDoc`реализация [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Эта функция уведомляет системы OLE библиотеки DLL, которые в свою очередь уведомление контейнеров. В контейнере приложений, написанных с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
##  <a name="a-nameonclosea--coleserverdoconclose"></a><a name="onclose"></a>COleServerDoc::OnClose  
 Вызывается платформой, когда контейнер запрашивает закрытие серверного документа.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCloseOption`  
 Значение из перечисления `OLECLOSE`. Этот параметр может принимать одно из следующих значений:  
  
- `OLECLOSE_SAVEIFDIRTY`Файл сохраняется в том случае, если он был изменен.  
  
- `OLECLOSE_NOSAVE`Файл не будет закрыт без сохранения.  
  
- `OLECLOSE_PROMPTSAVE`Если файл был изменен, пользователю предлагается его сохранении.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `CDocument::OnCloseDocument`.  
  
 Дополнительные сведения и дополнительные значения в разделе [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameondeactivatea--coleserverdocondeactivate"></a><a name="ondeactivate"></a>COleServerDoc::OnDeactivate  
 Вызывается платформой, когда пользователь отключает внедренного или связанного элемента, который является активным в данный момент на месте.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция восстанавливает исходное состояние пользовательского интерфейса приложения-контейнера, а также уничтожает все меню и других элементов управления, которые были созданы для активации на месте.  
  
 Сведения о состоянии отмены должен освобождаться безусловно на этом этапе.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...  
  
##  <a name="a-nameondeactivateuia--coleserverdocondeactivateui"></a><a name="ondeactivateui"></a>COleServerDoc::OnDeactivateUI  
 Вызывается, когда пользователь отключает элемент, который был активирован на месте.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Параметры  
 `bUndoable`  
 Указывает, можно ли отменить изменения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция восстанавливает пользовательский интерфейс приложения-контейнера в исходное состояние, скрывая все меню и других элементов управления, которые были созданы для активации на месте.  
  
 Платформа всегда устанавливает `bUndoable` для **FALSE**. Если сервер поддерживает отмены, и операция, которая может быть отменено, вызовите реализацию базового класса с `bUndoable` значение **TRUE**.  
  
##  <a name="a-nameondocwindowactivatea--coleserverdocondocwindowactivate"></a><a name="ondocwindowactivate"></a>COleServerDoc::OnDocWindowActivate  
 Платформа вызывает эту функцию, чтобы включить или отключить окно документа для редактирования на месте.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `bActivate`  
 Указывает, является ли окно документа для активации или деактивации.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию удаляет или добавляет элементы интерфейса пользователя на уровне кадров соответствующим образом. Переопределите эту функцию, если требуется выполнить дополнительные действия, когда документ, содержащий элемент активируется или деактивируется.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...  
  
##  <a name="a-nameonexecolecmda--coleserverdoconexecolecmd"></a><a name="onexecolecmd"></a>COleServerDoc::OnExecOleCmd  
 Платформа вызывает эту функцию для выполнения определенной команды или отображение справки для команды.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>Параметры  
 `pguidCmdGroup`  
 Указатель на GUID, который определяет набор команд. Может быть **NULL** для указания группы по умолчанию команд.  
  
 `nCmdID`  
 Команда для выполнения. Должен находиться в группе, определенной `pguidCmdGroup`.  
  
 *nCmdExecOut*  
 Способ выполнения объектом команды для одного или нескольких из следующих значений из **OLECMDEXECOPT** перечисления:  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 Указатель на **VARIANTARG** содержащий входных аргументов для команды. Может быть **NULL**.  
  
 `pvarargOut`  
 Указатель на **VARIANTARG** для получения возвращаемых значений выходных данных команды. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` при успехе; в противном случае — один из следующих кодов ошибки:  
  
|Значение|Описание|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Произошла непредвиденная ошибка|  
|**E_FAIL**|Произошла ошибка|  
|**E_NOTIMPL**|Указывает MFC сам должен попытаться перевести и распределения команды|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`не **NULL** , но не указана группа распознанной команды|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`не является допустимой команды в группу`pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|Команда, идентифицируемый `nCmdID` отключена и не может быть выполнена|  
|**OLECMDERR_NOHELP**|Вызывающий объект запрашивает справки о команде, определяемый `nCmdID` , но Справка недоступна|  
|**OLECMDERR_CANCELED**|Выполнение отменено пользователем|  
  
### <a name="remarks"></a>Примечания  
 `COleCmdUI`можно использовать для включения, обновления и задать другие свойства DocObject команд пользовательского интерфейса. После инициализации команды можно выполнить их при помощи `OnExecOleCmd`.  
  
 Платформа вызывает функцию перед попыткой преобразования и отправляет команду документа OLE. Не нужно переопределить эту функцию для обработки стандартных команд документа OLE, но переопределение этой функции необходимо указывать, если требуется обрабатывать собственные команды или обработки команд, которые принимают параметры или возвращать результаты.  
  
 Большинство команд не принимают аргументы и возвращаемые значения. Для большинства команд вызывающий код может передать **NULL**s для `pvarargIn` и `pvarargOut`. Для команд, которые ожидают, что входные значения, можно объявить и инициализировать вызывающий **VARIANTARG** переменной и передать указатель на переменную в `pvarargIn`. Для команд, которые требуют одно значение, аргумент может храниться непосредственно в **VARIANTARG** и передается в функцию. Несколько аргументов должны быть упакованы в **VARIANTARG** с помощью одного из поддерживаемых типов (таких как `IDispatch` и **SAFEARRAY** ).  
  
 Аналогичным образом, если команда возвращает аргументы, вызывающий объект должен объявить **VARIANTARG**, инициализируйте его, чтобы `VT_EMPTY`и передать его адрес в `pvarargOut`. Если команда возвращает одно значение, объект можно сохранить это значение непосредственно в `pvarargOut`. Несколько выходных значений должны быть упакованы каким-либо образом подходит для **VARIANTARG**.  
  
 Реализация базового класса данной функции поможет **OLE_COMMAND_MAP** структуры, связанный с целевой объект команды и попытке отправки команды соответствующий обработчик. Реализация базового класса работает только с командами, которые не принимают аргументы и возвращаемые значения. Если требуется для обработки команд, которые принимают аргументы и возвращаемые значения, необходимо переопределить эту функцию и работать с `pvarargIn` и `pvarargOut` параметры самостоятельно.  
  
##  <a name="a-nameonframewindowactivatea--coleserverdoconframewindowactivate"></a><a name="onframewindowactivate"></a>COleServerDoc::OnFrameWindowActivate  
 Платформа вызывает эту функцию, когда окно приложения-контейнера, активируется или деактивируется.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `bActivate`  
 Указывает, является ли окно области активации или деактивации.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отменяет любых режимов справки возможно фрейме окна. Переопределите эту функцию, если вы хотите выполнять специальную обработку, если окно активируется или деактивируется.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...  
  
##  <a name="a-nameongetembeddeditema--coleserverdocongetembeddeditem"></a><a name="ongetembeddeditem"></a>COleServerDoc::OnGetEmbeddedItem  
 Вызывается платформой, когда приложение контейнера вызывает серверное приложение для создания или редактирования внедренного элемента.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, представляющий весь документ; **NULL** при сбое операции.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию, чтобы вернуть объект, представляющий весь документ. Это возвращаемое значение должно быть объектом `COleServerItem`-производного класса.  
  
##  <a name="a-nameonreactivateandundoa--coleserverdoconreactivateandundo"></a><a name="onreactivateandundo"></a>COleServerDoc::OnReactivateAndUndo  
 Платформа вызывает данную функцию, если пользователь решает отменить изменения, внесенные в элемент, который был активирован в месте, меняется и впоследствии отключены.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий кроме возвращаемое **FALSE** для сигнализации об ошибке.  
  
 Переопределите эту функцию, если приложение поддерживает отмены. Обычно необходимо выполнить операцию отмены, а затем Активация элемента путем вызова `ActivateInPlace`. Если приложение контейнера написан с помощью библиотеки Microsoft Foundation Class, при вызове `COleClientItem::ReactivateAndUndo` вызывает эту функцию для вызова.  
  
##  <a name="a-nameonresizebordera--coleserverdoconresizeborder"></a><a name="onresizeborder"></a>COleServerDoc::OnResizeBorder  
 Платформа вызывает эту функцию изменения размера окна фрейма приложения-контейнера.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRectBorder`  
 Указатель на `RECT` структуры или `CRect` , указывающий координаты границы.  
  
 `lpUIWindow`  
 Указатель на объект класса **IOleInPlaceUIWindow** , которому принадлежит текущий сеанс редактирования на месте.  
  
 *обработки b-кадров*  
 **Значение TRUE,** Если `lpUIWindow` указывает окну верхнего уровня кадра приложения-контейнера, или **FALSE** Если `lpUIWindow` указывает на уровне документа фрейм окна приложения-контейнера.  
  
### <a name="remarks"></a>Примечания  
 Эта функция изменяет размеры и настройка панелей инструментов и других элементов пользовательского интерфейса в соответствии с нового размера окна.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Существует расширенная переопределяемыми.  
  
##  <a name="a-nameonsethostnamesa--coleserverdoconsethostnames"></a><a name="onsethostnames"></a>COleServerDoc::OnSetHostNames  
 Вызывается платформой, когда контейнер задает или изменяет имена узлов для этого документа.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszHost`  
 Указатель на строку, указывающее имя приложения-контейнера.  
  
 `lpszHostObj`  
 Указатель на строку, указывающее имя контейнера для документа.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию изменяет заголовок документа все представления, ссылающиеся на этот документ.  
  
 Переопределите эту функцию, если приложение задает заголовки посредством другого механизма.  
  
##  <a name="a-nameonsetitemrectsa--coleserverdoconsetitemrects"></a><a name="onsetitemrects"></a>COleServerDoc::OnSetItemRects  
 Платформа вызывает эту функцию для размещения окна фрейма на месте для редактирования в окне фрейма приложения-контейнера.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPosRect`  
 Указатель на `RECT` структуры или `CRect` , указывающий положение окна фрейма на месте относительно клиентской области его контейнера.  
  
 `lpClipRect`  
 Указатель на `RECT` структуры или `CRect` объект, который указывает прямоугольник отсечения окна фрейма на месте относительно клиентской области его контейнера.  
  
### <a name="remarks"></a>Примечания  
 При необходимости переопределите эту функцию для обновления масштаб представления.  
  
 Эта функция обычно вызывается в ответ на `RequestPositionChange` вызов, хотя он может вызываться в любое время в качестве контейнера для запроса на изменение положения элемента на месте.  
  
##  <a name="a-nameonshowcontrolbarsa--coleserverdoconshowcontrolbars"></a><a name="onshowcontrolbars"></a>COleServerDoc::OnShowControlBars  
 Платформа вызывает эту функцию для отображения или скрытия панели элементов управления серверное приложение, связанные с окном фрейма, идентифицируемый `pFrameWnd`.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrameWnd`  
 Указатель фрейма окна, панели элементов управления будет скрыто или показано.  
  
 `bShow`  
 Определяет, показаны или скрыты панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию перечисляет все панели элементов управления, принадлежащих этого окна фрейма и скрывает или отображает их.  
  
##  <a name="a-nameonshowdocumenta--coleserverdoconshowdocument"></a><a name="onshowdocument"></a>COleServerDoc::OnShowDocument  
 Платформа вызывает функцию `OnShowDocument` работают, когда серверный документ должен быть скрыт или показано.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 `bShow`  
 Указывает, является ли пользовательский интерфейс в документ быть отображены или скрыты.  
  
### <a name="remarks"></a>Примечания  
 Если `bShow` — **TRUE**, реализация по умолчанию активирует серверного приложения при необходимости и заставляет приложение контейнера прокрутите окно, чтобы элемент видим. Если `bShow` — **FALSE**, реализация по умолчанию отключает элемента путем вызова `OnDeactivate`, а затем уничтожает или скрывает все окна фрейма, которые были созданы для документа, кроме первого. Если остались без видимых документов, реализация по умолчанию скрывает серверного приложения.  
  
##  <a name="a-nameonupdatedocumenta--coleserverdoconupdatedocument"></a><a name="onupdatedocument"></a>COleServerDoc::OnUpdateDocument  
 Вызывается инфраструктурой при сохранении документа, встроенного элемента в составной документ.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно обновлен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [COleServerDoc::NotifySaved](#notifysaved) и [COleServerDoc::SaveEmbedding](#saveembedding) член функции, а затем помечает документ как очистить. Переопределите эту функцию, если вы хотите выполнить специальная обработка при обновлении встроенного элемента.  
  
##  <a name="a-namerequestpositionchangea--coleserverdocrequestpositionchange"></a><a name="requestpositionchange"></a>COleServerDoc::RequestPositionChange  
 Вызовите эту функцию-член для изменения положения элемента приложения-контейнера.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPosRect`  
 Указатель на `RECT` структуры или `CRect` объект, содержащий новое положение элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается (вместе с `UpdateAllItems`) при изменении данных в активный элемент на месте. После вызова этого метода, контейнер может или не может выполнить изменение путем вызова `OnSetItemRects`. Результирующая позиция может отличаться от запрошенного.  
  
##  <a name="a-namesaveembeddinga--coleserverdocsaveembedding"></a><a name="saveembedding"></a>COleServerDoc::SaveEmbedding  
 Эта функция вызывается для сообщить приложения-контейнера для сохранения внедренного объекта.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается автоматически `OnUpdateDocument`. Обратите внимание, что эта функция приводит к обновляться на диске, поэтому обычно он вызывается только в результате действий конкретного пользователя.  
  
##  <a name="a-namescrollcontainerbya--coleserverdocscrollcontainerby"></a><a name="scrollcontainerby"></a>COleServerDoc::ScrollContainerBy  
 Вызов `ScrollContainerBy` обозначается прокрутку контейнера документа на значение, в пикселях, функция-член `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Параметры  
 `sizeScroll`  
 Указывает, насколько документе-контейнере для прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Положительные значения указывают прокрутку вниз и вправо; отрицательные значения указывают прокрутку вверх и влево.  
  
##  <a name="a-nameupdateallitemsa--coleserverdocupdateallitems"></a><a name="updateallitems"></a>COleServerDoc::UpdateAllItems  
 Эта функция вызывается для уведомления всех связанных элементов, подключенных к документу измененного документа.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Параметры  
 `pSender`  
 Указатель на элемент, измененный документ, или **NULL** Если все элементы должны быть обновлены.  
  
 `lHint`  
 Содержит сведения об изменении.  
  
 `pHint`  
 Указатель на объект, хранения информации о изменения.  
  
 `nDrawAspect`  
 Определяет, как рисуемого элемента. Это значение из `DVASPECT` перечисления. Этот параметр может принимать одно из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается, когда пользователь изменит серверного документа. Если элемент OLE связан документ с автоматической связью, элемент обновляется для отражения изменений. В контейнере приложений, написанных с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
 Эта функция вызывает функцию `OnUpdate` функции-члена для каждого из элементов документа, за исключением отправки элементов, передавая `pHint`, `lHint`, и `nDrawAspect`. Эти параметры можно используйте для передачи информации об изменениях, внесенных в документ элементы. Можно закодировать с помощью сведения `lHint` или определить `CObject`-производный класс для хранения информации об изменениях и передайте объект этого класса, используя `pHint`. Переопределение `OnUpdate` функции-члена в вашей `COleServerItem`-производный класс для оптимизации обновление каждого элемента в зависимости от того, изменилось ли его представления.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)   
 [Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)

