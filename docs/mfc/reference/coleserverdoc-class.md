---
title: Класс COleServerDoc | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs:
- C++
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7df4ea13313758c517188e1c4ce0441618a99b4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039073"
---
# <a name="coleserverdoc-class"></a>Класс COleServerDoc
Базовый класс для серверной документации OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Создает объект `COleServerDoc`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Активируется связанный документ DocObject.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Активирует документ для редактирования по месту.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Отключает пользовательский интерфейс сервера.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Удаляет сведения состояния отмены.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Извлекает указатель на базовый `IOleClientSite` интерфейса.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Возвращает указатель на элемент, представляющий весь документ.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Возвращает текущий прямоугольник отсечения для редактирования по месту.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Возвращает текущий прямоугольник позиции относительно клиентской области приложения-контейнера для редактирования по месту.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Возвращает значение масштаба в пикселях.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Определяет, является ли документ DocObject.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Указывает, внедренный в документе-контейнере или выполнение автономного документа.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Возвращает `TRUE` тогда, когда элемент активируется в настоящее время на месте.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Уведомляет контейнеров, что пользователь изменил документа.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Уведомляет контейнеры, пользователь закрыл документа.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Уведомляет контейнеров, что пользователь переименован документа.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Уведомляет контейнеров, что сохраненные документа.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Вызывается платформой, когда пользователь делает элемент, который был активирован на месте.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Вызывается платформой для удаления элементов управления и других элементов пользовательского интерфейса, созданные для активации на месте.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Вызывается платформой при активации или отключении окном фрейма документа контейнера.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Вызывается платформой при изменении размера окна фрейма приложения-контейнера или окно документа.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Вызывается платформой для отображения или скрытия панели элементов управления для редактирования по месту.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Вызывается платформой при сохранении документа сервера, который является встроенного элемента, обновление копии контейнера элемента.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Изменяет положение фрейма редактирования по месту.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Сообщает приложению контейнера для сохранения документа.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Выполняет прокрутку документа-контейнера.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Уведомляет контейнеров, что пользователь изменил документа.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Вызывается платформой для создания окна фрейма для встроенного редактирования.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Вызывается платформой для уничтожения окна фрейма для встроенного редактирования.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Переопределить эту функцию для создания нового `CDocObjectServer` объекта и указать, что в этом документе DocObject контейнера.|  
|[COleServerDoc::OnClose](#onclose)|Вызывается платформой, когда контейнер запрашивает Закрытие документа.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Выполняет указанную команду или отображает справку по команде.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Вызывается платформой при активации или отключении окна фрейма контейнера.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Вызывается для получения `COleServerItem` представляет весь документ; используется для получения встроенного элемента. Требуется реализация.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Вызывается платформой, чтобы отменить изменения, внесенные во время редактирования по месту.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Вызывается платформой, когда контейнер устанавливает заголовок окна для внедренного объекта.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Вызывается платформой для размещения окна фрейма на месте для редактирования в окне приложения-контейнера.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Вызывается платформой для отображения или скрытия документа.|  
  
## <a name="remarks"></a>Примечания  
 Серверный документ может содержать [COleServerItem](../../mfc/reference/coleserveritem-class.md) объектов, которые представляют собой интерфейс сервера внедренные или связанные элементы. При запуске серверного приложения контейнера для редактирования внедренного элемента, элемент загружается как свой собственный серверный документ; `COleServerDoc` объект содержит только один `COleServerItem` объект, состоящий из всего документа. Если серверное приложение запускается в контейнере, чтобы изменить связанный элемент, существующий документ загружается с диска; часть содержимого документа будет выделен для обозначения связанного элемента.  
  
 `COleServerDoc` объекты могут также содержать объектов [COleClientItem](../../mfc/reference/coleclientitem-class.md) класса. Это позволяет создавать приложения контейнера сервера. Платформа предоставляет функции для хранения правильно `COleClientItem` элементов во время обслуживания `COleServerItem` объектов.  
  
 Если серверное приложение не поддерживает ссылки, серверный документ всегда будет содержать только один элемент сервера, который представляет весь внедренный объект как документ. Если серверное приложение поддерживает ссылки, его необходимо создать серверный элемент каждый раз, когда фрагмент копируется в буфер обмена.  
  
 Для использования `COleServerDoc`, создайте класс, производный от него и реализации [OnGetEmbeddedItem](#ongetembeddeditem) функция-член, что позволяет серверу для поддержки встроенных элементов. Производный класс `COleServerItem` для реализации элементов в документах и возврата объектов этого класса из `OnGetEmbeddedItem`.  
  
 Для поддержки связанных элементов `COleServerDoc` предоставляет [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) функции-члена. Можно использовать реализацию по умолчанию, или переопределить его, если у вас есть собственный способ управления элементов документа.  
  
 Требуется один `COleServerDoc`-производный класс для каждого типа сервера документа, поддерживаемых приложением. Например, если серверное приложение поддерживает листы и диаграммы, необходимы два `COleServerDoc`-производные классы.  
  
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
  
##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject  
 Активируется связанный документ DocObject.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `COleServerDoc` не поддерживает активные документы (также называемый DocObjects). Для включения такой поддержки. в разделе [GetDocObjectServer](#getdocobjectserver) и класс [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace  
 Активирует элемент для редактирования по месту.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае значение равно 0, указывающая, что элемент является полностью открытыми.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняет все операции, необходимые для активации на месте. Он создает окно фрейма на месте, она активируется и размеров его к элементу, настраивает общего меню и других элементов управления, прокручивает элемент в представлении и устанавливает фокус на окно фрейма на месте.  
  
 Эта функция вызывается с использованием реализации по умолчанию [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Эта функция вызывается в том случае, если приложение поддерживает другую команду для активации на месте (например, "Воспроизведение").  
  
##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc  
 Создает `COleServerDoc` объекта без соединения с OLE системные библиотеки DLL.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) открыть связь с OLE. При использовании [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) в вашем приложении `COleLinkingDoc::Register` вызывается для вас `COleLinkingDoc`реализация `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame  
 Платформа вызывает эту функцию для создания окна фрейма для редактирования по месту.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pParentWnd*  
 Указатель на родительское окно приложения-контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно фрейма на месте или **NULL** в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию использует сведения, указанные в шаблоне документа для создания фрейма. Представление, используемое — первое представление, созданные для документа. В этом представлении временно отсоединяется от исходного кадра и присоединяется к только что созданный кадр.  
  
 Существует расширенная overridable.  
  
##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo  
 Эта функция вызывается в том случае, если отменить поддерживаемых приложением, и пользователь нажимает кнопку отмены после активации элемента, но перед его изменением.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Если контейнер приложение создано с помощью библиотеки классов Microsoft Foundation, вызов этой функции приводит [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) для вызова, который отключает пользовательский интерфейс сервера.  
  
##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame  
 Платформа вызывает эту функцию для уничтожения окна фрейма на месте и вернуть сервер окна документа приложения в состояние до активации на месте.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pFrameWnd*  
 Указатель на окно фрейма на месте будут уничтожены.  
  
### <a name="remarks"></a>Примечания  
 Существует расширенная overridable.  
  
##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState  
 Если пользователь выполняет операцию редактирования, который не может быть отменено, эта функция вызывается для принудительного приложения-контейнера для отмены его состояния отмены сведения.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предназначена, чтобы серверы, поддерживающие отмены может освободить ресурсы, которые в противном случае будет использоваться состояния отмены сведения, который не может использоваться.  
  
##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite  
 Извлекает указатель на базовый `IOleClientSite` интерфейса.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель на базовый [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) интерфейса.  
  
##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer  
 Переопределить эту функцию для создания нового `CDocObjectServer` элемент и возвращает указатель на него.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Параметры  
 *pDocSite*  
 Указатель на `IOleDocumentSite` интерфейс, который будет соединиться с сервером в этом документе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CDocObjectServer`; **NULL** при сбое операции.  
  
### <a name="remarks"></a>Примечания  
 При активации сервер DocObject, возвращает значение, отличное от **NULL** указатель мыши показывает, что клиент может поддерживать DocObjects. Реализация по умолчанию возвращает **NULL**.  
  
 Типичная реализация для документа, который поддерживает DocObjects просто выделить новый `CDocObjectServer` объекта и возвращает его в вызывающий объект. Пример:  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem  
 Эта функция вызывается для получения указателя на элемент, представляющий весь документ.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, представляющий весь документ; **NULL** при сбое операции.  
  
### <a name="remarks"></a>Примечания  
 Он вызывает [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), виртуальная функция с реализация по умолчанию отсутствует.  
  
##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect  
 Вызовите `GetItemClipRect` функции-члена для получения координат прямоугольника обрезки элемента, который изменяется на месте.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpClipRect*  
 Указатель на `RECT` структуры или `CRect` объект для получения координат прямоугольника обрезки элемента.  
  
### <a name="remarks"></a>Примечания  
 Координаты задаются в пикселях относительно клиентской области окна приложения контейнера.  
  
 Рисование не будет выполняться вне прямоугольника отсечения. Как правило рисунок будет автоматически ограничен. Эта функция позволяет определить, является ли пользователь прокручивает за пределы видимой области документа. в этом случае Прокрутить документ контейнера, при необходимости с помощью вызова [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition  
 Вызовите `GetItemPosition` функции-члена для получения координат элемента редактируемого на месте.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpPosRect*  
 Указатель на `RECT` структуры или `CRect` объект для получения координат элемента.  
  
### <a name="remarks"></a>Примечания  
 Координаты задаются в пикселях относительно клиентской области окна приложения контейнера.  
  
 Положение элемента можно сравнить с текущим прямоугольником отсечения, чтобы определить степень, в которой элемент видимыми (или не отображается) на экране.  
  
##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor  
 `GetZoomFactor` Функция-член определяет «масштаб» элемента, который был активирован для редактирования по месту.  
  
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
  
 *lpPosRect*  
 Указатель на объект класса `CRect` , описывающий новое положение элемента. Если этот аргумент является **NULL**, эта функция использует текущую позицию элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент активируется для непосредственного редактирования и его коэффициента масштабирования отличается от 100% (1:1); в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Значение масштаба в пикселях является долю размер элемента в его текущем степени. Если приложение-контейнер не задал степени элемента, его естественное экстент (как определено [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) используется.  
  
 Функция присваивает его первых двух аргументов числитель и знаменатель элемента «коэффициента масштабирования.» Если элемент не редактируется на месте, функция задает значение по умолчанию 100% (или 1:1) эти аргументы и возвращает ноль. Дополнительные сведения см. в разделе технической 40 Обратите внимание, [MFC/OLE по месту изменение размеров и изменение масштаба](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject  
 Определяет, является ли документ DocObject.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если документ является DocObject; в противном случае **FALSE**.  
  
##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded  
 Вызовите `IsEmbedded` функции-члена для определения того, представляет ли объекта, встроенного в контейнере документа.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `COleServerDoc` объект является документ, который представляет объект, внедренный в контейнере; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Несмотря на то, что он может управляться как ссылка приложения-контейнера документа, загруженного из файла не внедряется. Для внедрения считается документ, который внедряется в документе-контейнере.  
  
##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive  
 Вызовите `IsInPlaceActive` функции-члена, чтобы определить, является ли элемент в данный момент в активном состоянии на месте.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `COleServerDoc` объект является активным в месте; в противном случае — 0.  
  
##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged  
 Эта функция вызывается для уведомления всех связанных элементов, которые подключены к документу, который документ был изменен.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Как правило эта функция вызывается, когда пользователь изменит некоторые глобальный атрибут, например измерений серверного документа. Если объект OLE связан документ с автоматически обновляемую связь, элемент обновляется для отражения изменений. В контейнере приложения, написанные с помощью библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
> [!NOTE]
>  Эта функция включена для совместимости с OLE-1. Новые приложения должны использовать [UpdateAllItems](#updateallitems).  
  
##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed  
 Эта функция вызывается для уведомления контейнеров, что документ был закрыт.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает команду "Закрыть" в меню "файл" `NotifyClosed` вызывается `COleServerDoc`реализация [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) функции-члена. В контейнере приложения, написанные с помощью библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename  
 Эта функция вызывается после пользователь переименовывает серверного документа.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszNewName*  
 Указатель на строку, указав новое имя серверного документа; Обычно это полный путь.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает команду «Сохранить как» из меню «Файл» `NotifyRename` вызывается `COleServerDoc`реализация [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) функции-члена. Эта функция уведомляет системы OLE библиотеки DLL, которые в свою очередь уведомление контейнеров. В контейнере приложения, написанные с помощью библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved  
 Эта функция вызывается после пользователь сохраняет документ сервера.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает команду «Сохранить» из меню «Файл» `NotifySaved` вызывается для вас `COleServerDoc`реализация [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Эта функция уведомляет системы OLE библиотеки DLL, которые в свою очередь уведомление контейнеров. В контейнере приложения, написанные с помощью библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
##  <a name="onclose"></a>  COleServerDoc::OnClose  
 Вызывается платформой, когда контейнер запрашивает закрытие серверного документа.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Параметры  
 *dwCloseOption*  
 Значение из перечисления `OLECLOSE`. Этот параметр может принимать одно из следующих значений:  
  
- `OLECLOSE_SAVEIFDIRTY` Файл сохраняется в том случае, если он был изменен.  
  
- `OLECLOSE_NOSAVE` Файл не будет закрыт без сохранения.  
  
- `OLECLOSE_PROMPTSAVE` Если файл был изменен, пользователю предлагается его сохранении.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `CDocument::OnCloseDocument`.  
  
 Дополнительные сведения и дополнительные значения см. в разделе [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) в Windows SDK.  
  
##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate  
 Вызывается платформой, когда пользователь делает внедренного или связанного элемента, который является активным в данный момент на месте.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция восстанавливает в исходное состояние пользовательского интерфейса из приложения контейнера и уничтожает любого меню и других элементов управления, которые были созданы для активации на месте.  
  
 Сведения о состоянии отмены следует безусловно освободить на этом этапе.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI  
 Вызывается, когда пользователь делает неактивным элемент, который был активирован на месте.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Параметры  
 *bUndoable*  
 Указывает, можно ли отменить внесения изменений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция пользовательского интерфейса из приложения контейнера восстанавливает в исходное состояние, скрытие любого меню и других элементов управления, которые были созданы для активации на месте.  
  
 Всегда устанавливает платформу *bUndoable* для **FALSE**. Если сервер поддерживает отмены и выполняется операция, которое может быть отменено, вызовите реализацию базового класса с *bUndoable* значение **TRUE**.  
  
##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate  
 Платформа вызывает эту функцию, чтобы активировать или деактивировать окно документа для редактирования по месту.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 *bActivate*  
 Указывает, является ли окно документа активировать или деактивировать.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию, удаляет или добавляет элементы уровня кадров пользовательского интерфейса соответствующим образом. Переопределите эту функцию, если требуется выполнить дополнительные действия при активации или деактивации документ, содержащий элемент.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...  
  
##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd  
 Платформа вызывает эту функцию для выполнения указанной команды или отобразить справку по команде.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>Параметры  
 *параметром pguidCmdGroup*  
 Указатель на GUID, который определяет набор команд. Может быть **NULL** для указания группы команд по умолчанию.  
  
 *nCmdID*  
 Команда для выполнения. Должен находиться в группе, определенной *параметром pguidCmdGroup*.  
  
 *nCmdExecOut*  
 Способ объект должен выполнить команду для одного или нескольких из следующих значений из **OLECMDEXECOPT** перечисления:  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 *pvarargIn*  
 Указатель на **VARIANTARG** содержащий входных аргументов для команды. Может быть **NULL**.  
  
 *pvarargOut*  
 Указатель на **VARIANTARG** для получения возвращаемых значений выходных данных команды. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` Если успешно; в противном случае — одно из следующих кодов ошибки:  
  
|Значение|Описание:|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Произошла непредвиденная ошибка|  
|**E_FAIL**|Произошла ошибка|  
|**E_NOTIMPL**|Указывает MFC сам следует попытаться перевести и отправляет команду|  
|**OLECMDERR_E_UNKNOWNGROUP**|*параметром pguidCmdGroup* не является **NULL** , но не указана группа распознано в качестве команды|  
|**OLECMDERR_E_NOTSUPPORTED**|*nCmdID* не является допустимой команды в группе *параметром pguidCmdGroup*|  
|**OLECMDERR_DISABLED**|Команда определяется *nCmdID* отключена и не может быть выполнена|  
|**OLECMDERR_NOHELP**|Вызывающий объект запрашивает справки на команду по *nCmdID* , но Справка недоступна|  
|**OLECMDERR_CANCELED**|Выполнение отменено пользователем|  
  
### <a name="remarks"></a>Примечания  
 `COleCmdUI` можно использовать для включения, обновления и задать другие свойства команд DocObject пользовательского интерфейса. После инициализации команды можно выполнить их при помощи `OnExecOleCmd`.  
  
 Платформа вызывает функцию перед попыткой преобразования и отправляет команду документа OLE. Не нужно переопределить эту функцию для обработки стандартные команды OLE документа, но вы должны предоставить переопределение, чтобы эта функция, если требуется обрабатывать пользовательские команды или обработки команд, которые принимают параметры и возвращать результаты.  
  
 Большинство команд не принимает аргументов и возвращаемых значений. Для большинства команд вызывающий объект передавать **NULL**s для *pvarargIn* и *pvarargOut*. Команды, которые ожидают, что входные значения, вызывающего объекта можно объявить и инициализировать **VARIANTARG** переменной и передать указатель на переменную в *pvarargIn*. Для команд, требующих одно значение, аргумент может храниться непосредственно в **VARIANTARG** и передается в функцию. Несколько аргументов должны быть упакованы в **VARIANTARG** с помощью одного из поддерживаемых типов (например, `IDispatch` и **SAFEARRAY** ).  
  
 Аналогичным образом, если команда возвращает аргументы, вызывающий объект должен объявить **VARIANTARG**, инициализируйте его, чтобы `VT_EMPTY`и передать его адрес в *pvarargOut*. Если команда возвращает одно значение, объект можно сохранить это значение непосредственно в *pvarargOut*. Несколько выходных значений, которые должны быть упакованы каким-либо образом подходит для **VARIANTARG**.  
  
 Описывает реализацию базового класса этой функции **OLE_COMMAND_MAP** структур, связанных с целевой объект команды и попробуйте диспетчеризации команду, чтобы соответствующий обработчик. Реализация базового класса работает только с командами, которые не принимают аргументы и возвращаемые значения. Если требуется для обработки команд, аргументов и возвращаемых значений, необходимо переопределить эту функцию и работать с *pvarargIn* и *pvarargOut* параметры самостоятельно.  
  
##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate  
 Эта функция вызывается платформой при активации или отключении окна фрейма приложения-контейнера.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 *bActivate*  
 Указывает, является ли окно области быть активирован или деактивирован.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отменяет какие-либо режимы справки может выполняться фрейм окна. Переопределите эту функцию, если вы хотите выполнять специальную обработку при активации или отключении окна фрейма.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem  
 Вызывается платформой, когда приложение контейнера вызывает серверное приложение для создания или редактирования внедренного элемента.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, представляющий весь документ; **NULL** при сбое операции.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию для возвращения элемента, который представляет весь документ. Это возвращаемое значение должно быть объектом `COleServerItem`-производного класса.  
  
##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo  
 Платформа вызывает эту функцию, если пользователь решит отменить изменения, внесенные в элемент, который был активирован в месте, меняется и впоследствии деактивации.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий, за исключением возвращаемого **FALSE** при сбое.  
  
 Переопределите эту функцию, если приложение поддерживает отмены. Обычно необходимо выполнить операцию отмены, а затем активировать элемент, вызвав `ActivateInPlace`. Если контейнер приложение создано с помощью библиотеки классов Microsoft Foundation, при вызове `COleClientItem::ReactivateAndUndo` вызывает эту функцию, чтобы вызвать.  
  
##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder  
 Платформа вызывает эту функцию, изменении размера окна фрейма приложения-контейнера.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Параметры  
 *lpRectBorder*  
 Указатель на `RECT` структуры или `CRect` объект, определяющий координаты границы.  
  
 *lpUIWindow*  
 Указатель на объект класса **IOleInPlaceUIWindow** , которому принадлежит текущий сеанс редактирования по месту.  
  
 *bFrame*  
 **Значение TRUE,** Если *lpUIWindow* указывает на приложение контейнера фрейме верхнего уровня, или **FALSE** Если *lpUIWindow* указывает на контейнер окна фрейма документа уровня приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция изменяет размеры и корректирует панелей инструментов и других элементов пользовательского интерфейса в соответствии с нового размера окна.  
  
 Дополнительные сведения см. в разделе [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) в Windows SDK.  
  
 Существует расширенная overridable.  
  
##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames  
 Вызывается платформой, когда контейнер устанавливает или изменяет имена узлов для этого документа.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszHost*  
 Указатель на строку, которая указывает имя приложения-контейнера.  
  
 *lpszHostObj*  
 Указатель на строку, которая указывает имя контейнера для документа.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию изменяет заголовок документа все представления, ссылающиеся на этот документ.  
  
 Переопределите эту функцию, если приложение задает заголовки использованием другого механизма.  
  
##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects  
 Платформа вызывает эту функцию, чтобы изменить расположение окна фрейма на месте для редактирования в окне фрейма приложения-контейнера.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Параметры  
 *lpPosRect*  
 Указатель на `RECT` структуры или `CRect` , указывающий положение окна фрейма на месте относительно клиентской области его контейнера.  
  
 *lpClipRect*  
 Указатель на `RECT` структуры или `CRect` , указывающий прямоугольник отсечения окна фрейма на месте относительно клиентской области его контейнера.  
  
### <a name="remarks"></a>Примечания  
 При необходимости переопределите эту функцию для представления коэффициента масштабирования, обновления.  
  
 Эта функция обычно вызывается в ответ на `RequestPositionChange` вызвать, несмотря на то, что он может быть вызван в любое время в контейнере для запроса на изменение позиции для элемента на месте.  
  
##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars  
 Платформа вызывает эту функцию для отображения или скрытия панели элементов управления серверного приложения, связанные с окном фрейма, обозначенную *pFrameWnd*.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 *pFrameWnd*  
 Указатель на фрейм окна, столбцы которой элемент управления будет скрыто или показано.  
  
 *bShow*  
 Определяет, отображении и скрытии панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию перечисляет все панели элементов управления, принадлежащих этого окна фрейма и скрывает или отображает их.  
  
##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument  
 Платформа вызывает `OnShowDocument` работать, когда серверный документ должен будет скрыто или показано.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 *bShow*  
 Указывает, является ли пользовательский интерфейс в документ отображаться или скрываться.  
  
### <a name="remarks"></a>Примечания  
 Если *bShow* — **TRUE**, реализация по умолчанию активирует приложение сервера, при необходимости, в результате чего приложение-контейнер для прокрутки окна ее, чтобы элемент был виден. Если *bShow* — **FALSE**, реализация по умолчанию деактивирует элемента посредством вызова `OnDeactivate`, удаляет или скрывает все окна фрейма, которые были созданы для документа, кроме первого одно. Если остались документов не отображается, реализация по умолчанию скрывает серверного приложения.  
  
##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument  
 Вызывается платформой при сохранении документа, внедренный элемент в составных документов.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно обновлен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [COleServerDoc::NotifySaved](#notifysaved) и [COleServerDoc::SaveEmbedding](#saveembedding) члена функции и затем помечается как очистить. Переопределите эту функцию, если вы хотите выполнить специальная обработка при обновлении встроенного элемента.  
  
##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange  
 Вызовите эту функцию-член для изменения положения элемента приложение контейнера.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Параметры  
 *lpPosRect*  
 Указатель на `RECT` структуры или `CRect` объект, содержащий новое положение элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается (вместе с `UpdateAllItems`) при изменении данных в активный элемент на месте. После вызова этого метода, контейнер может или не может выполнить изменение путем вызова `OnSetItemRects`. Итоговая позиция может отличаться от от запрошенного.  
  
##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding  
 Вызывайте эту функцию, чтобы сообщить приложения-контейнера для сохранения внедренного объекта.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается автоматически из `OnUpdateDocument`. Обратите внимание, что эта функция приводит его, чтобы обновить на диске, поэтому обычно он вызывается только в результате действия пользователя.  
  
##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy  
 Вызовите `ScrollContainerBy` функции-члена прокрутку документа-контейнера значение, в пикселях, обозначенном `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Параметры  
 *sizeScroll*  
 Указывает, насколько документе-контейнере для прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Положительные значения указывают прокрутку вниз и вправо; отрицательные значения указывают, прокрутку вверх и влево.  
  
##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems  
 Эта функция вызывается для уведомления всех связанных элементов, которые подключены к документу, который документ был изменен.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Параметры  
 *pSender*  
 Указатель на элемент, изменение в документ или **NULL** Если все элементы должны быть обновлены.  
  
 *lHint*  
 Содержит сведения об изменении.  
  
 *pHint*  
 Указатель на объект, хранения информации об изменении.  
  
 *nDrawAspect*  
 Определяет, как для отображения элемента. Это значение из `DVASPECT` перечисления. Этот параметр может принимать одно из следующих значений:  
  
- `DVASPECT_CONTENT` Элемент представлен таким образом, может быть отображен как внедренный объект внутри контейнера.  
  
- `DVASPECT_THUMBNAIL` Элемент отображается в представлении «эскиз», чтобы оно может отображаться в средстве просмотра.  
  
- `DVASPECT_ICON` Элемент будет представлен значок.  
  
- `DVASPECT_DOCPRINT` Элемент представляется, как если бы выводились с помощью команды «Печать» из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Как правило, эта функция вызывается, когда пользователь изменит серверного документа. Если объект OLE связан документ с автоматически обновляемую связь, элемент обновляется для отражения изменений. В контейнере приложения, написанные с помощью библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.  
  
 Эта функция вызывает `OnUpdate` функция-член для каждого из элементов документа, за исключением отправки элементов, передавая *pHint*, *lHint*, и *nDrawAspect*. Используйте эти параметры для передачи информации об изменениях, внесенных в документ элементы. Можно закодировать с помощью сведения *lHint* или можно определить `CObject`-производный класс для хранения информации об изменениях и передать объект этого класса с помощью *pHint*. Переопределить `OnUpdate` функции-члена в вашей `COleServerItem`-производного класса, чтобы оптимизировать обновление каждого элемента в зависимости от того, изменилось ли их представлением.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)   
 [Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
