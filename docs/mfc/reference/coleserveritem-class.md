---
title: "Класс COleServerItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
dev_langs:
- C++
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd64d6a2cf4fe36e62f5c6599521780c4ee002ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coleserveritem-class"></a>Класс COleServerItem
Предоставляет серверный интерфейс элементам OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|Создает объект `COleServerItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Помещает форматов представления и преобразования в `COleDataSource` объекта.|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Копирование элемента в буфер обмена.|  
|[COleServerItem::DoDragDrop](#dodragdrop)|Выполняет операцию перетаскивания и вставки.|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|Возвращает источник данных для использования во время передачи данных (Перетаскивание или буфер обмена).|  
|[COleServerItem::GetDocument](#getdocument)|Возвращает серверный документ, который содержит элемент.|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Возвращает **CF_EMBEDSOURCE** данные для объекта OLE.|  
|[COleServerItem::GetItemName](#getitemname)|Возвращает имя элемента. Используется только для связанных элементов.|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Возвращает `CF_LINKSOURCE` данные для объекта OLE.|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Возвращает **CF_OBJECTDESCRIPTOR** данные для объекта OLE.|  
|[COleServerItem::IsConnected](#isconnected)|Указывает, является ли элемент в настоящее время присоединена к контейнеру active.|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|Указывает, является ли этот элемент представляет связанный элемент OLE.|  
|[COleServerItem::NotifyChanged](#notifychanged)|Обновляет все контейнеры ссылку автоматическое обновление.|  
|[COleServerItem::OnDoVerb](#ondoverb)|Вызывается для выполнения команды.|  
|[COleServerItem::OnDraw](#ondraw)|Вызывается, когда контейнер запрашивает для рисования элемента; требуется реализация.|  
|[COleServerItem::OnDrawEx](#ondrawex)|Вызывается для специальных элементов рисования.|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Вызывается платформой для получения данных, которые необходимо скопировать в буфер обмена.|  
|[COleServerItem::OnGetExtent](#ongetextent)|Вызывается платформой для получения размера элемента OLE.|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|Вызывается платформой для инициализации объекта OLE, используя содержимое заданного объекта передачи данных.|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Вызывается, чтобы определить, требуется ли обновление устаревших связанных элементов.|  
|[COleServerItem::OnRenderData](#onrenderdata)|Извлекает данные в рамках отложенной подготовки к просмотру.|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Получает данные в `CFile` объект как часть отложенной подготовки к просмотру.|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Получает данные в `HGLOBAL` как часть отложенной подготовки к просмотру.|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Вызывается, чтобы задать цвет элемента.|  
|[COleServerItem::OnSetData](#onsetdata)|Вызывается для задания элемента данных.|  
|[COleServerItem::OnSetExtent](#onsetextent)|Вызывается платформой для изменения размера объекта OLE.|  
|[COleServerItem::OnUpdate](#onupdate)|Вызывается при принадлежит какой-либо части документа элемента изменяется.|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|Вызывается для обновления всех элементов на серверном документе кэша презентации.|  
|[COleServerItem::SetItemName](#setitemname)|Задает имя элемента. Используется только для связанных элементов.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](#getdatasource)|Возвращает объект, используемый для хранения форматов преобразования.|  
|[COleServerItem::OnHide](#onhide)|Вызывается платформой для скрытия элемента OLE.|  
|[COleServerItem::OnOpen](#onopen)|Вызывается платформой для отображения объекта OLE в отдельном окне верхнего уровня.|  
|[COleServerItem::OnShow](#onshow)|Вызывается, когда контейнер запрашивает, чтобы отобразить элемент.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Сервер сообщает о какая часть элемента OLE является видимым.|  
  
## <a name="remarks"></a>Примечания  
 Связанный элемент может представлять все или некоторые из серверного документа. Внедренный элемент всегда представляет документ всего сервера.  
  
 `COleServerItem` Класс определяет несколько функций переопределяемый член, которые вызываются методом OLE системные библиотеки динамической компоновки (DLL), обычно в ответ на запросы из приложения контейнера. Эти функции-члены позволяют приложению контейнера манипуляции элементом косвенно различными способами, например, его отображение, выполнение его команд или извлекает свои данные в различных форматах.  
  
 Для использования `COleServerItem`, создайте класс, производный от него и реализации [OnDraw](#ondraw) и [сериализации](../../mfc/reference/cobject-class.md#serialize) функции-члены. `OnDraw` Функция предоставляет представление метафайла элемента, позволяя ему отображаются в том случае, когда приложение контейнера открывает составных документов. `Serialize` Функция `CObject` предоставляет собственные представления элемента, позволяя встроенного элемента будет передаваться между приложениями сервера и контейнера. [OnGetExtent](#ongetextent) предоставляет размеру элемента контейнера, включение контейнера для определения размера элемента.  
  
 Дополнительные сведения о серверах и щелкните ссылку, см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md) и «Создание контейнера и сервера приложений» в статье [контейнеры: Дополнительные функции](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 Вызывайте эту функцию для размещения форматы презентации и преобразования для элемента OLE в указанном `COleDataSource` объекта.  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataSource`  
 Указатель на `COleDataSource` объект, в который следует поместить данные.  
  
### <a name="remarks"></a>Примечания  
 Должен реализован [OnDraw](#ondraw) функции-члена для предоставления формата представления (рисунок метафайл) для элемента. Для поддержки других форматов преобразования, зарегистрируйте их с помощью [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, возвращаемый [GetDataSource](#getdatasource) и Переопределите [OnRenderData](#onrenderdata) функция-член предоставляют данные в форматах, которые требуется поддерживать.  
  
##  <a name="coleserveritem"></a>COleServerItem::COleServerItem  
 Создает `COleServerItem` объекта и добавляет ее коллекцию серверный документ элементов документа.  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 `pServerDoc`  
 Указатель на документ, который будет содержать новый элемент.  
  
 `bAutoDelete`  
 Флаг, указывающий, является ли объект может быть удален при отпускании ссылку на него. Задайте значение **FALSE** Если `COleServerItem` объект является составной частью данных в документе, который необходимо удалить. Задайте значение **TRUE** Если объект является вторичной структура, используемая для определения диапазона данных в документе, могут быть удалены платформой.  
  
##  <a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 Эта функция используется для копирования в буфер обмена элемента OLE.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bIncludeLink`  
 Задайте значение **TRUE** Если связать данные следует копировать в буфер обмена. Задайте значение **FALSE** Если серверное приложение не поддерживает ссылки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция использует [OnGetClipboardData](#ongetclipboarddata) функции-члена для создания [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные элемента OLE в форматах, поддерживаемых. Функция затем помещает `COleDataSource` объектов в буфер обмена с помощью [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) функции. `COleDataSource` Объект включает собственных данных элемента и его представление в `CF_METAFILEPICT` формате, а также данные в любой выбрать поддержку форматов преобразования. Должен реализован [сериализации](../../mfc/reference/cobject-class.md#serialize) и [OnDraw](#ondraw) для работы этой функции-члена.  
  
##  <a name="dodragdrop"></a>COleServerItem::DoDragDrop  
 Вызовите `DoDragDrop` функции-члена для выполнения операции перетаскивания и вставки.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpRectItem*  
 Прямоугольник элемента на экране, в пикселях, относительно клиентской области.  
  
 `ptOffset`  
 Смещение от `lpItemRect` положением позиции мыши во время операции перетаскивания.  
  
 `bIncludeLink`  
 Задайте значение **TRUE** Если связать данные следует копировать в буфер обмена. Задайте для него значение **FALSE** Если приложение не поддерживает ссылки.  
  
 `dwEffects`  
 Определяет эффекты, которые источник перетаскивания разрешает в операции перетаскивания (сочетание копирования, перемещения и связи).  
  
 `lpRectStartDrag`  
 Указатель на прямоугольник, который определяет, где фактически начинает перетаскивание. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение из перечисления `DROPEFFECT`. Если это `DROPEFFECT_MOVE`, следует удалить исходных данных.  
  
### <a name="remarks"></a>Примечания  
 Операции перетаскивания и вставки не начинается немедленно. Он ожидает, пока курсор мыши выходит за пределы прямоугольника, определяемого `lpRectStartDrag` или пока не были пройдены указанного числа миллисекунд. Если `lpRectStartDrag` — **NULL**, прямоугольник по умолчанию используется, чтобы перетаскивание начинается, когда указатель мыши перемещается на один пиксель.  
  
 Время задержки задается параметр раздела реестра. Время задержки можно изменить путем вызова [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если время задержки не указан, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите хранится следующим образом:  
  
-   Время задержки Windows NT перетащите хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Время задержки перетащите 3.x Windows хранится в WIN. INI-файл, в разделе [Windows}.  
  
-   Время задержки Windows 95/98 перетащите хранится в кэшированная версия WIN. INI-ФАЙЛЕ.  
  
 Для перетащите Дополнительные сведения о том, как задержки сведения хранятся в реестре или. INI-файл, в разделе [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) в Windows SDK.  
  
##  <a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 Эта функция вызывается для заполнения указанного [COleDataSource](../../mfc/reference/coledatasource-class.md) объекта со всеми данными, которые необходимо скопировать в буфер обмена при вызове [CopyToClipboard](#copytoclipboard) (также будет переноситься те же данные, если вы вызывается [DoDragDrop](#dodragdrop)).  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataSource`  
 Указатель на `COleDataSource` объект, который будет получать данные элемента OLE в любом из поддерживаемых форматов.  
  
 `bIncludeLink`  
 **Значение TRUE,** Если связать данные следует копировать в буфер обмена. **FALSE** Если серверное приложение не поддерживает ссылки.  
  
 `lpOffset`  
 Смещение в пикселях от начала координат объекта указателя мыши.  
  
 `lpSize`  
 Размер объекта в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает [GetEmbedSourceData](#getembedsourcedata) получить собственные данные для объекта OLE и вызывает функцию-член [AddOtherClipboardData](#addotherclipboarddata) для получения формата представления и все функции-члена Поддерживаемые форматы преобразования. Если `bIncludeLink` — **TRUE**, также вызывает функцию [GetLinkSourceData](#getlinksourcedata) для получения данных ссылки для элемента.  
  
 Переопределить эту функцию, если вы хотите поместить в форматах `COleDataSource` объекта до или после этих форматах, предоставляемые `CopyToClipboard`.  
  
##  <a name="getdatasource"></a>COleServerItem::GetDataSource  
 Эта функция вызывается для получения [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, используемый для хранения форматов преобразования, которые поддерживает приложение сервера.  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `COleDataSource` объект, используемый для хранения форматов преобразования.  
  
### <a name="remarks"></a>Примечания  
 Если требуется серверное приложение предоставлять данные в различные форматы во время передачи данных операций регистрации этих форматов с `COleDataSource` объект, возвращаемый этой функцией. Например, если вы хотите указать **CF_TEXT** представление элемента OLE для буфера обмена или операции перетаскивания и вставки зарегистрировать формат с `COleDataSource` эта функция возвращает объект и затем переопределить  **OnRenderXxxData** функции-члена для предоставления данных.  
  
##  <a name="getdocument"></a>COleServerItem::GetDocument  
 Вызывайте эту функцию, чтобы получить указатель на документ, содержащий элемент.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент. **NULL** Если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет получить доступ к документу сервера, который передается в качестве аргумента для `COleServerItem` конструктор.  
  
##  <a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 Эта функция вызывается для получения **CF_EMBEDSOURCE** данные для объекта OLE.  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, который получит **CF_EMBEDSOURCE** данные для объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Этот формат включает элемента собственных данных. Должен реализован `Serialize` функции-члена для правильной работы этой функции.  
  
 Результат может затем добавить к источнику данных с помощью [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [COleServerItem::OnGetClipboardData](#ongetclipboarddata).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в Windows SDK.  
  
##  <a name="getitemname"></a>COleServerItem::GetItemName  
 Эта функция вызывается для получения имени элемента.  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается только для связанных элементов.  
  
##  <a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 Эта функция вызывается для получения `CF_LINKSOURCE` данные для объекта OLE.  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, который получит `CF_LINKSOURCE` данные для объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот формат включает CLSID, описывающее тип объекта OLE и сведения, необходимые для поиска документа, содержащего объекта OLE.  
  
 Результат можно добавить источник данных с [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [OnGetClipboardData](#ongetclipboarddata).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в Windows SDK.  
  
##  <a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 Эта функция вызывается для получения **CF_OBJECTDESCRIPTOR** данные для объекта OLE.  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpOffset`  
 Смещение от верхнего левого угла элемента OLE щелчка мыши. Может быть **NULL**.  
  
 `lpSize`  
 Размер элемента OLE. Может быть **NULL**.  
  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, который получит **CF_OBJECTDESCRIPTOR** данные для объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Данные копируются в **STGMEDIUM** структуры, на который указывает `lpStgMedium`. Этот формат включает сведения, необходимые для диалогового окна Специальная вставка.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в Windows SDK.  
  
##  <a name="isconnected"></a>COleServerItem::IsConnected  
 Вызывайте эту функцию, чтобы увидеть, подключен ли элемента OLE.  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент подключен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Объект OLE считается подключен, если один или несколько контейнеров связаны с элементом. Элемент подключен, если счетчик ссылок на него больше 0 или если это встроенного элемента.  
  
##  <a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 Вызывайте эту функцию, находится ли элемент OLE связанный элемент.  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент является связанный элемент; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если элемент является допустимым и не возвращается в документе список внедренных элементов связанного элемента. Связанный элемент может или не подключен к контейнеру.  
  
 Это обычно используется для связанных и внедренных элементов того же класса. `IsLinkedItem`позволяет сделать связанных элементов, которые ведут себя иначе, чем внедренные элементы, хотя обычно используется несколько раз код.  
  
##  <a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 Этот элемент указывает, что сервер сколько объекта отображается в документе-контейнере.  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию [OnSetExtent](#onsetextent) задает этот член.  
  
##  <a name="notifychanged"></a>COleServerItem::NotifyChanged  
 Эта функция вызывается после изменения связанного элемента.  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Значение из `DVASPECT` перечисление, указывающее, какие элементы объекта OLE был изменен. Этот параметр может принимать любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, может быть отображен как внедренный объект внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно может отображаться в средстве просмотра.  
  
- `DVASPECT_ICON`Элемент будет представлен значок.  
  
- `DVASPECT_DOCPRINT`Элемент представляется, как если бы выводились с помощью команды «Печать» из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Если элемент-контейнер связан документ с автоматически обновляемую связь, элемент обновляется для отражения изменений. В контейнере приложений, использующих библиотеку классов Microsoft Foundation [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) вызывается в ответ.  
  
##  <a name="ondoverb"></a>COleServerItem::OnDoVerb  
 Вызывается платформой для выполнения указанной команды.  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Указывает команду для выполнения. Он может быть одним из следующих:  
  
|Значение|Значение|Символ|  
|-----------|-------------|------------|  
|0|первичный глагол|`OLEIVERB_PRIMARY`|  
|1|Команда получателя|(Нет)|  
|- 1|Отображение элемента для редактирования|`OLEIVERB_SHOW`|  
|- 2|Изменение элемента в отдельном окне|`OLEIVERB_OPEN`|  
|- 3|Скрытие элемента|`OLEIVERB_HIDE`|  
  
 Значение-1, обычно является псевдонимом для другой команды. Если открыть изменения не поддерживается, -2 действует так же, как -1. Для всех дополнительных значений в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с библиотеки классов Microsoft Foundation, эта функция вызывается, когда [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) функция-член соответствующего `COleClientItem` вызывается. Реализация по умолчанию вызывает [OnShow](#onshow) функцию-член, если первичный глагол или `OLEIVERB_SHOW` указано, [OnOpen](#onopen) Если вторичных команд или `OLEIVERB_OPEN` указано и [OnHide](#onhide) Если `OLEIVERB_HIDE` указано. Реализация по умолчанию вызывает `OnShow` Если `iVerb` не является одной из команд, перечисленных выше.  
  
 Переопределите эту функцию, если ваш первичный глагол не содержит элемент. Например если элемент является запись звука и его первичный глагол Play, не пришлось бы для отображения серверное приложение для воспроизведения элемента.  
  
 Дополнительные сведения см. в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в Windows SDK.  
  
##  <a name="ondraw"></a>COleServerItem::OnDraw  
 Вызывается платформой для отрисовки элемента OLE в метафайл.  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объекта, на котором выполняется отрисовка элемента. Контекст отображения автоматически подключается к контекст отображения атрибутов, можно вызывать функции атрибута, несмотря на то, что это сделает метафайла конкретного устройства.  
  
 `rSize`  
 Размер, в **HIMETRIC** единиц, в котором будет размещено в метафайл.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент успешно рисования; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Представление метафайла элемента OLE используется для отображения элемента в приложении-контейнере. Используется ли приложение-контейнер был записан с библиотеки классов Microsoft Foundation, метафайл [нарисовать](../../mfc/reference/coleclientitem-class.md#draw) функция-член соответствующего [COleClientItem](../../mfc/reference/coleclientitem-class.md) объекта. Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию для рисования элемента в указанном контексте устройства.  
  
##  <a name="ondrawex"></a>COleServerItem::OnDrawEx  
 Вызывается платформой для всех рисования.  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объекта, на котором выполняется отрисовка элемента. Контроллер домена автоматически подключается к атрибута контроллера домена, можно вызывать функции атрибута, несмотря на то, что это сделает метафайла конкретного устройства.  
  
 `nDrawAspect`  
 Значение из перечисления `DVASPECT`. Этот параметр может принимать любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, может быть отображен как внедренный объект внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно может отображаться в средстве просмотра.  
  
- `DVASPECT_ICON`Элемент будет представлен значок.  
  
- `DVASPECT_DOCPRINT`Элемент представляется, как если бы выводились с помощью команды «Печать» из меню «файл».  
  
 `rSize`  
 Размер элемента в **HIMETRIC** единицы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент успешно рисования; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `OnDraw` при `DVASPECT` равен `DVASPECT_CONTENT`; в противном случае он завершается.  
  
 Переопределить эту функцию для предоставления данных презентации аспектов, отличный от `DVASPECT_CONTENT`, такие как `DVASPECT_ICON` или `DVASPECT_THUMBNAIL`.  
  
##  <a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 Вызывается платформой для получения `COleDataSource` объект, содержащий все данные, которые были бы расставлены в буфере обмена, путем вызова [CopyToClipboard](#copytoclipboard) функции-члена.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Параметры  
 `bIncludeLink`  
 Задайте значение **TRUE** Если связать данные следует копировать в буфер обмена. Задайте значение **FALSE** Если серверное приложение не поддерживает ссылки.  
  
 `lpOffset`  
 Смещение курсора мыши от начала координат объекта в пикселях.  
  
 `lpSize`  
 Размер объекта в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные из буфера обмена.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetextent"></a>COleServerItem::OnGetExtent  
 Вызывается платформой для получения размера, в **HIMETRIC** единицы элемента OLE.  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого должны быть получены. Этот параметр может принимать любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, может быть отображен как внедренный объект внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно может отображаться в средстве просмотра.  
  
- `DVASPECT_ICON`Элемент будет представлен значок.  
  
- `DVASPECT_DOCPRINT`Элемент представляется, как если бы выводились с помощью команды «Печать» из меню «файл».  
  
 `rSize`  
 Ссылка на `CSize` объекта, который получит размер элемента OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с библиотеки классов Microsoft Foundation, эта функция вызывается, когда [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) функция-член соответствующего `COleClientItem` вызывается. Реализация по умолчанию не выполняет никаких действий. Он должен реализовать самостоятельно. Переопределите эту функцию, если нужно выполнить специальную обработку при обработке запроса для размера объекта OLE.  
  
##  <a name="onhide"></a>COleServerItem::OnHide  
 Вызывается платформой для скрытия элемента OLE.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию вызывает **COleServerDoc::OnShowDocument (FALSE)**. Функция уведомляет контейнера скрытого элемента OLE. Переопределите эту функцию, если нужно выполнить специальную обработку при скрытии элемента OLE.  
  
##  <a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 Вызывается платформой для инициализации объекта OLE, используя содержимое `pDataObject`.  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на объект OLE данных, содержащих данные в различные форматы для инициализации объекта OLE.  
  
 `bCreation`  
 **Значение TRUE,** Если функция вызывается для инициализации объекта OLE, вновь создаваемого приложения-контейнера. **FALSE** Если функция вызывается для замены содержимого уже существующего элемента OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bCreation` — **TRUE**, эта функция вызывается в том случае, если контейнер реализует вставки нового объекта на основе текущего выбора. Данные, выбранные используется при создании нового элемента OLE. Например, если выбор диапазона ячеек в электронную, а затем создайте диаграмму с помощью вставки нового объекта на основе значений в выбранном диапазоне. Реализация по умолчанию не выполняет никаких действий. Переопределить эту функцию, чтобы выбрать допустимый формат из числа предлагаемых `pDataObject` и инициализации объекта OLE, на основе предоставленных данных. Существует расширенная overridable.  
  
 Дополнительные сведения см. в разделе [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) в Windows SDK.  
  
##  <a name="onopen"></a>COleServerItem::OnOpen  
 Вызывается платформой для отображения объекта OLE в отдельном экземпляре серверного приложения, а не на месте.  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию активирует первое окно фрейма, отображение документ, который содержит элемент OLE. Если приложение является мини-сервера, реализация по умолчанию показано главное окно. Функция уведомляет контейнер открыт элемента OLE.  
  
 Переопределите эту функцию, если требуется специальная обработка выполняется при открытии элемента OLE. Такой метод особенно часто, с которой вы хотите выбрать в списке к ссылке при открытии связанных элементов.  
  
 Дополнительные сведения см. в разделе [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) в Windows SDK.  
  
##  <a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 Вызывается платформой для определения устаревших связанных элементов в текущем документе server устарела.  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ содержит элементы, требующие обновления. 0, если все элементы находятся в актуальном состоянии.  
  
### <a name="remarks"></a>Примечания  
 Элемент является устаревшим, если его исходный документ был изменен, но связанный элемент не была обновлена в соответствии с изменениями в документе.  
  
##  <a name="onrenderdata"></a>COleServerItem::OnRenderData  
 Вызывается платформой для извлечения данных в указанном формате.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `lpStgMedium`  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структура, в которой должны быть возвращены данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат является одним помещенный в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) или [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция вызывает [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData](#onrenderglobaldata), соответственно, если указанный носитель памяти или в файл. Если ни один из этих форматов предоставляется реализация по умолчанию возвращает значение 0 и не выполняет никаких действий.  
  
 Если `lpStgMedium` ->  *tymed* — **TYMED_NULL**, **STGMEDIUM** следует выделить и заполнены в соответствии с *lpFormatEtc -> tymed*. В противном случае **TYMED_NULL**, **STGMEDIUM** должно быть заполнено на месте с данными.  
  
 Существует расширенная overridable. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо него. Если данные хранятся в малых и фиксированного размера, переопределяют `OnRenderGlobalData`. Если данные в файле или является переменного размера, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), и [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) в Windows SDK.  
  
##  <a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 Вызывается платформой для извлечения данных в указанном формате, если среда хранения — это файл.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `pFile`  
 Указывает на `CFile` объект, в котором должен быть подготовлен к просмотру данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат является одним помещенный в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Существует расширенная overridable. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо него. Если для обработки нескольких носителей, необходимо переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределите [OnRenderFileData](#onrenderfiledata).  
  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в Windows SDK.  
  
##  <a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
 Вызывается платформой для получения данных в указанном формате, если указанный носитель является глобальной памяти.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `phGlobal`  
 Указывает дескриптор глобальной памяти, в котором данные тоже должны быть возвращены. Если выделена память, этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат является одним помещенный в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Если `phGlobal` — **NULL**, затем новый `HGLOBAL` следует выделять и возвращаются в `phGlobal`. В противном случае `HGLOBAL` заданные `phGlobal` должно быть заполнено с данными. Объем данных помещаются в `HGLOBAL` не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен к значению большего размера.  
  
 Существует расширенная overridable. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо него. Если для обработки нескольких носителей, необходимо переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределите [OnRenderFileData](#onrenderfiledata).  
  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в Windows SDK.  
  
##  <a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 Вызывается платформой для указания цветовую палитру для использования при редактировании объекта OLE.  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogPalette`  
 Указатель на Windows [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если используется цветовая палитра. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с помощью библиотеки классов Microsoft Foundation, эта функция вызывается, когда [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) функция соответствующего `COleClientItem` вызывается. Реализация по умолчанию возвращает **FALSE**. Переопределите эту функцию, если вы хотите использовать рекомендованную палитру. Серверное приложение не требуется для использования предлагаемую палитру.  
  
 Дополнительные сведения см. в разделе [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) в Windows SDK.  
  
##  <a name="onsetdata"></a>COleServerItem::OnSetData  
 Вызывается платформой для замены данных объекта OLE с указанными данными.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат данных.  
  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, в которой хранятся данные.  
  
 `bRelease`  
 Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающая сторона определяет, кто отвечает за освобождение ресурсов, выделенной среды хранения. Вызывающий объект устанавливается не `bRelease`. Если `bRelease` имеет ненулевое значение, серверный элемент принимает право на владение, освобождение среды после завершения его использования. Когда `bRelease` имеет значение 0, вызывающий объект продолжает владеть и серверный элемент можно использовать среду хранения только в течение всего вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Элемент сервера вступают в владения данных он получен успешно. То есть он не стать владельцем, если возвращается значение 0. Если источник данных принимает право на владение, он освобождает среду хранения путем вызова [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) функции.  
  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для замены данных объекта OLE с указанными данными. Существует расширенная overridable.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), и [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) в Windows SDK.  
  
##  <a name="onsetextent"></a>COleServerItem::OnSetExtent  
 Вызывается платформой для сообщения элементу OLE объем доступных в документе-контейнере.  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого были указаны. Этот параметр может принимать любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, может быть отображен как внедренный объект внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно может отображаться в средстве просмотра.  
  
- `DVASPECT_ICON`Элемент будет представлен значок.  
  
- `DVASPECT_DOCPRINT`Элемент представляется, как если бы выводились с помощью команды «Печать» из меню «файл».  
  
 `size`  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) структуры, указав новый размер объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с библиотеки классов Microsoft Foundation, эта функция вызывается, когда [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) функция-член соответствующего `COleClientItem` вызывается. Наборы данных для реализации по умолчанию [m_sizeExtent](#m_sizeextent) член до заданного размера Если `nDrawAspect` — `DVASPECT_CONTENT`; в противном случае возвращается значение 0. Переопределите эту функцию, чтобы выполнять специальную обработку при изменении размера элемента.  
  
##  <a name="onshow"></a>COleServerItem::OnShow  
 Вызывается платформой для указания серверное приложение для отображения объекта OLE на месте.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается, когда пользователь приложения-контейнера создает элемент или выполняет команды, такие как изменение, требующее, чтобы элемент, который будет отображаться. Реализация по умолчанию попыток активации на месте. Если это не удается, вызовы функций `OnOpen` функции-члена для отображения объекта OLE в отдельном окне.  
  
 Переопределите эту функцию, если вы хотите выполнять специальную обработку при отображении элемента OLE.  
  
##  <a name="onupdate"></a>COleServerItem::OnUpdate  
 Вызывается платформой при изменении элемента.  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Параметры  
 `pSender`  
 Указатель на элемент, изменение в документ. Может быть **NULL**.  
  
 `lHint`  
 Содержит сведения об изменении.  
  
 `pHint`  
 Указатель на объект, хранения информации об изменении.  
  
 `nDrawAspect`  
 Значение из перечисления `DVASPECT`. Этот параметр может принимать одно из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, может быть отображен как внедренный объект внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно может отображаться в средстве просмотра.  
  
- `DVASPECT_ICON`Элемент будет представлен значок.  
  
- `DVASPECT_DOCPRINT`Элемент представляется, как если бы выводились с помощью команды «Печать» из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [NotifyChanged](#notifychanged), независимо от того, указание или отправителя.  
  
##  <a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 Вызывается платформой для обновления всех элементов на серверном документе.  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) для всех `COleClientItem` объекты в документе.  
  
##  <a name="setitemname"></a>COleServerItem::SetItemName  
 Вызывайте эту функцию при создании связанный элемент, чтобы задать его имя.  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItemName`  
 Указатель на новое имя элемента.  
  
### <a name="remarks"></a>Примечания  
 Имя должно быть уникальным в пределах документа. При вызове серверного приложения для редактирования связанный элемент, приложение использует это имя для поиска элемента. Необходимо вызвать эту функцию для встроенных элементов.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс CDocItem](../../mfc/reference/cdocitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
