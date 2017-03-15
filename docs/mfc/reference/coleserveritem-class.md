---
title: "Класса, производного от COleServerItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerItem
dev_langs:
- C++
helpviewer_keywords:
- servers, OLE
- OLE server applications, managing server documents
- OLE server applications, server interfaces
- OLE server documents
- COleServerItem class
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 23
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
ms.openlocfilehash: 49dd8cc258ebf96c91ac8ff1190f9a830b6bb5ec
ms.lasthandoff: 02/24/2017

---
# <a name="coleserveritem-class"></a>Класса, производного от COleServerItem
Предоставляет серверный интерфейс элементам OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|Создает объект `COleServerItem`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Помещает представления и преобразования форматов в `COleDataSource` объекта.|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Копирование элемента в буфер обмена.|  
|[COleServerItem::DoDragDrop](#dodragdrop)|Выполняет операцию и перетаскивания.|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|Возвращает источник данных для использования во время передачи данных (Перетаскивание или буфер обмена).|  
|[COleServerItem::GetDocument](#getdocument)|Возвращает серверного документа, которая содержит элемент.|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Возвращает **CF_EMBEDSOURCE** данные для объекта OLE.|  
|[COleServerItem::GetItemName](#getitemname)|Возвращает имя элемента. Используется только для связанных элементов.|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Возвращает `CF_LINKSOURCE` данные для объекта OLE.|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Возвращает **CF_OBJECTDESCRIPTOR** данные для объекта OLE.|  
|[COleServerItem::IsConnected](#isconnected)|Указывает, присоединен ли в данный момент элемента к контейнеру active.|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|Указывает, является ли этот элемент представляет связанный элемент OLE.|  
|[COleServerItem::NotifyChanged](#notifychanged)|Обновляет все контейнеры ссылку автоматического обновления.|  
|[COleServerItem::OnDoVerb](#ondoverb)|Вызывается для выполнения команды.|  
|[COleServerItem::OnDraw](#ondraw)|Вызывается, когда контейнер запрашивает для рисования элемента; требуется реализация.|  
|[COleServerItem::OnDrawEx](#ondrawex)|Вызывается для рисования специализированных элементов.|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Вызывается платформой для получения данных, будет скопирован в буфер обмена.|  
|[COleServerItem::OnGetExtent](#ongetextent)|Вызывается платформой для определения размера элемента OLE.|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|Вызывается платформой для инициализации объекта OLE, используя содержимое указанного объекта передачи данных.|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Вызывается, чтобы определить, требуется ли обновление все связанные элементы.|  
|[COleServerItem::OnRenderData](#onrenderdata)|Извлекает данные как часть отложенной подготовки к просмотру.|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Получает данные в `CFile` объект в рамках отложенной подготовки к просмотру.|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Получает данные в `HGLOBAL` в рамках отложенной подготовки к просмотру.|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Вызывается, чтобы задать цвет элемента.|  
|[COleServerItem::OnSetData](#onsetdata)|Вызывается для задания элемента данных.|  
|[COleServerItem::OnSetExtent](#onsetextent)|Вызывается платформой для установки размера объекта OLE.|  
|[COleServerItem::OnUpdate](#onupdate)|Вызывается при принадлежит некоторая часть документа элемента изменяется.|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|Вызывается для обновления всех элементов на серверном документе кэша презентации.|  
|[COleServerItem::SetItemName](#setitemname)|Задает имя элемента. Используется только для связанных элементов.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](#getdatasource)|Возвращает объект, используемый для хранения преобразования форматов.|  
|[COleServerItem::OnHide](#onhide)|Вызывается платформой для скрытия элемента OLE.|  
|[COleServerItem::OnOpen](#onopen)|Вызывается платформой для отображения объекта OLE в отдельном окне верхнего уровня.|  
|[COleServerItem::OnShow](#onshow)|Вызывается, когда контейнер запрашивает, чтобы отобразить элемент.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Сообщает серверу о часть объекта OLE является видимым.|  
  
## <a name="remarks"></a>Примечания  
 Связанный элемент может представлять некоторые или все из серверного документа. Внедренный элемент всегда представляет документ всего сервера.  
  
 `COleServerItem` Класс определяет несколько переопределяемый член функции, вызываемые OLE системы динамические библиотеки (DLL), обычно в ответ на запросы приложения-контейнера. Эти функции-члены позволяют приложения-контейнера для манипуляции элементом косвенно различными способами, например, путем отображения, выполнив его команд или извлечения данных в различных форматах.  
  
 Для использования `COleServerItem`, создайте класс, производный от него и реализовать [OnDraw](#ondraw) и [сериализации](../../mfc/reference/cobject-class.md#serialize) функции-члены. `OnDraw` Функция предоставляет представление метафайла элемента, что он будет отображен при открытии приложения контейнера составной документ. `Serialize` Функция `CObject` предоставляет собственное представление элемента, позволяя встроенного элемента будет передаваться между приложениями сервера и контейнера. [OnGetExtent](#ongetextent) предоставляет размеру элемента контейнера, включение контейнера изменить размер элемента.  
  
 Дополнительные сведения о серверах и щелкните ссылку, см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md) и «Создание контейнера и сервера приложений» в статье [контейнеров: Дополнительные функции](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-nameaddotherclipboarddataa--coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 Эта функция вызывается для размещения форматы представления и преобразование объекта OLE в указанном `COleDataSource` объекта.  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataSource`  
 Указатель на `COleDataSource` объект, в который следует поместить данные.  
  
### <a name="remarks"></a>Примечания  
 Должен реализован [OnDraw](#ondraw) функции-члена для предоставления формат представления (рисунок метафайл) для элемента. Для поддержки других форматов преобразования, зарегистрируйте их с помощью [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, возвращаемый [GetDataSource](#getdatasource) и Переопределите [OnRenderData](#onrenderdata) функции-члена для предоставления данных в форматах, которые требуется поддерживать.  
  
##  <a name="a-namecoleserveritema--coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>COleServerItem::COleServerItem  
 Создает `COleServerItem` объекта и добавляет его в коллекцию элементов документа серверного документа.  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 `pServerDoc`  
 Указатель на документ, который будет содержать новый элемент.  
  
 `bAutoDelete`  
 Флаг, указывающий, может ли объект удален, когда ссылка на него освобождается. Задайте значение **FALSE** Если `COleServerItem` объект является неотъемлемой частью данных в документе, который необходимо удалить. Задайте значение **TRUE** Если объект получателя структура, используемая для определения диапазона данных в документе, могут быть удалены по платформе.  
  
##  <a name="a-namecopytoclipboarda--coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 Эта функция вызывается для объекта OLE скопировать в буфер обмена.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bIncludeLink`  
 Задайте значение **TRUE** Если ссылку данные должны быть скопированы в буфер обмена. Задайте значение **FALSE** Если серверное приложение не поддерживает ссылки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция использует [OnGetClipboardData](#ongetclipboarddata) функции-члена для создания [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные элемента OLE в поддерживаемых форматах. Функция затем помещает `COleDataSource` объектов в буфер обмена с помощью [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) функции. `COleDataSource` Объект включает в себя элемент данных в собственном и его представление в `CF_METAFILEPICT` формате, а также данные в любой выбрать поддержку форматов преобразования. Должен реализован [сериализации](../../mfc/reference/cobject-class.md#serialize) и [OnDraw](#ondraw) для работы этой функции-члена.  
  
##  <a name="a-namedodragdropa--coleserveritemdodragdrop"></a><a name="dodragdrop"></a>COleServerItem::DoDragDrop  
 Вызов `DoDragDrop` для выполнения операции и перетащите функции-члена.  
  
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
 Смещение от `lpItemRect` положением положением указателя мыши во время операции перетаскивания.  
  
 `bIncludeLink`  
 Задайте значение **TRUE** Если ссылку данные должны быть скопированы в буфер обмена. Задайте для него значение **FALSE** Если приложение не поддерживает ссылки.  
  
 `dwEffects`  
 Определяет эффекты, которые источник перетаскивания будет разрешать в операции перетаскивания (сочетание копирования, перемещения и связи).  
  
 `lpRectStartDrag`  
 Указатель на прямоугольник, определяющий, где фактически начинает перетаскивание. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение из перечисления `DROPEFFECT`. Если это `DROPEFFECT_MOVE`, исходные данные должны удаляться.  
  
### <a name="remarks"></a>Примечания  
 Операции и перетащите начать немедленно. Он ждет, пока указатель мыши выходит за пределы прямоугольника, определяемого `lpRectStartDrag` или пока не прошли указанного числа миллисекунд. Если `lpRectStartDrag` — **NULL**, прямоугольник по умолчанию используется, чтобы перетаскивания начинается, когда указатель мыши перемещается на одну точку.  
  
 Время задержки задается параметр раздела реестра. Время задержки можно изменить с помощью [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если время задержки не указан, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите сохраняются следующим образом:  
  
-   Время задержки Windows NT перетащите хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Время задержки Windows 3.x перетащите хранится в WIN. INI-файл, в разделе [Windows}.  
  
-   Время задержки Windows 95/98 перетащите хранится в кэшированную версию WIN. INI.  
  
 Для перетащите Дополнительные сведения о том, как задержка сведения хранятся в реестре или. INI-файл, в разделе [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetclipboarddataa--coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 Эта функция вызывается для заполнения указанного [COleDataSource](../../mfc/reference/coledatasource-class.md) объекта со всеми данными, которые будут скопированы в буфер обмена при вызове [CopyToClipboard](#copytoclipboard) (те же данные будут также передаваться при вызове [DoDragDrop](#dodragdrop)).  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataSource`  
 Указатель на `COleDataSource` объект, который будет получать данные объекта OLE во всех поддерживаемых форматах.  
  
 `bIncludeLink`  
 **Значение TRUE,** Если ссылку данные должны быть скопированы в буфер обмена. **FALSE** Если серверное приложение не поддерживает ссылки.  
  
 `lpOffset`  
 Смещение в пикселях курсор мыши от начала координат объекта.  
  
 `lpSize`  
 Размер объекта в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию [GetEmbedSourceData](#getembedsourcedata) получить собственные данные для объекта OLE и вызывает функцию-член [AddOtherClipboardData](#addotherclipboarddata) функции-члена для получения формат представления и любые поддерживаемые форматы преобразования. Если `bIncludeLink` — **TRUE**, также вызывает функцию [GetLinkSourceData](#getlinksourcedata) для получения данных ссылки для элемента.  
  
 Переопределить эту функцию, если вы хотите поместить форматах `COleDataSource` объекта до или после этих форматов, предоставляемые `CopyToClipboard`.  
  
##  <a name="a-namegetdatasourcea--coleserveritemgetdatasource"></a><a name="getdatasource"></a>COleServerItem::GetDataSource  
 Эта функция вызывается для получения [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, используемый для хранения форматов преобразования, которые поддерживает приложение сервера.  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `COleDataSource` объект, используемый для хранения преобразования форматов.  
  
### <a name="remarks"></a>Примечания  
 Если требуется серверное приложение предоставлять данные в различные форматы во время передачи данных операций регистрации этих форматов с `COleDataSource` объект, возвращаемый этой функцией. Например, если требуется передать **CF_TEXT** представление элемента OLE для буфера обмена или операции и перетащите зарегистрировать формат с `COleDataSource` эта функция возвращает объект, а затем переопределить **OnRenderXxxData** функции-члена для предоставления данных.  
  
##  <a name="a-namegetdocumenta--coleserveritemgetdocument"></a><a name="getdocument"></a>COleServerItem::GetDocument  
 Эта функция вызывается для получения указателя в документ, содержащий элемент.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, который содержит элемент. **NULL** Если элемент не является частью документа.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет получить доступ для серверного документа, которая передается в качестве аргумента `COleServerItem` конструктор.  
  
##  <a name="a-namegetembedsourcedataa--coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 Эта функция вызывается для получения **CF_EMBEDSOURCE** данные для объекта OLE.  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, которая будет принимать **CF_EMBEDSOURCE** данные для объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Этот формат включает собственных данных элемента. Должен реализован `Serialize` функции-члена для правильной работы этой функции.  
  
 Результат может быть затем добавляется к источнику данных с помощью [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [COleServerItem::OnGetClipboardData](#ongetclipboarddata).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetitemnamea--coleserveritemgetitemname"></a><a name="getitemname"></a>COleServerItem::GetItemName  
 Эта функция вызывается для получения имени элемента.  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается только для связанных элементов.  
  
##  <a name="a-namegetlinksourcedataa--coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 Эта функция вызывается для получения `CF_LINKSOURCE` данные для объекта OLE.  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структура, получит `CF_LINKSOURCE` данные для объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот формат включает CLSID, описывающий тип объекта OLE и сведения, необходимые для поиска документа, содержащего объекта OLE.  
  
 Результат затем можно добавить к источнику данных с [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [OnGetClipboardData](#ongetclipboarddata).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetobjectdescriptordataa--coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 Эта функция вызывается для получения **CF_OBJECTDESCRIPTOR** данные для объекта OLE.  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpOffset`  
 Смещение щелчка мыши от верхнего левого угла элемента OLE. Может быть **NULL**.  
  
 `lpSize`  
 Размер объекта OLE. Может быть **NULL**.  
  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структура, получит **CF_OBJECTDESCRIPTOR** данные для объекта OLE.  
  
### <a name="remarks"></a>Примечания  
 Данные копируются в **STGMEDIUM** структуры, на который указывает `lpStgMedium`. Этот формат содержит сведения, необходимые для диалогового окна Специальная вставка.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisconnecteda--coleserveritemisconnected"></a><a name="isconnected"></a>COleServerItem::IsConnected  
 Эта функция используется для просмотра, подключен ли элемент OLE.  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент подключен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Элемент OLE считается подключен, если один или несколько контейнеров имеют ссылки на элемент. Элемент подключен, если счетчик ссылок на него больше 0 или если встроенного элемента.  
  
##  <a name="a-nameislinkeditema--coleserveritemislinkeditem"></a><a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 Эта функция вызывается для того, является ли элемент OLE связанный элемент.  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент имеет связанный элемент; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если элемент является допустимым и не возвращается в документе список внедренных элементов, связан элемент. Связанный элемент может или не может быть подключен к контейнеру.  
  
 Это обычно используется для связанных и внедренных элементов того же класса. `IsLinkedItem`позволяет сделать связанных элементов, которые ведут себя иначе, чем внедренных элементов, хотя обычно используется многократно кода.  
  
##  <a name="a-namemsizeextenta--coleserveritemmsizeextent"></a><a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 Этот элемент указывает, что сервер сколько объект является видимым в документе-контейнере.  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию [OnSetExtent](#onsetextent) задает этот член.  
  
##  <a name="a-namenotifychangeda--coleserveritemnotifychanged"></a><a name="notifychanged"></a>COleServerItem::NotifyChanged  
 Эта функция вызывается после изменения связанного элемента.  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Значение из `DVASPECT` перечисления, которое указывает, какие элементы объекта OLE был изменен. Этот параметр может иметь любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Если элемент контейнера связан документ с автоматической связью, элемент обновляется для отражения изменений. В контейнере приложений, использующих библиотеки классов Microsoft Foundation [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) вызывается в ответ.  
  
##  <a name="a-nameondoverba--coleserveritemondoverb"></a><a name="ondoverb"></a>COleServerItem::OnDoVerb  
 Вызывается платформой для выполнения указанной команды.  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Указывает команду для выполнения. Это может быть одним из следующих:  
  
|Значение|Значение|Символ|  
|-----------|-------------|------------|  
|0|первичный глагол|`OLEIVERB_PRIMARY`|  
|1|Вторичный команд|(Нет)|  
|– 1|Отображение элемента для редактирования|`OLEIVERB_SHOW`|  
|– 2|Изменение элемента в отдельном окне|`OLEIVERB_OPEN`|  
|– 3|Скрытие элементов|`OLEIVERB_HIDE`|  
  
 Значение –&1;, обычно является псевдонимом для другой команды. Если открыть изменения не поддерживается, –&2; действует так же, как -1. Дополнительные значения в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) соответствующего функцию-член `COleClientItem` вызывается. Реализация по умолчанию вызывает [OnShow](#onshow) Если функция-член первичный глагол или `OLEIVERB_SHOW` указан, [OnOpen](#onopen) Если вторичных команд или `OLEIVERB_OPEN` указано, и [OnHide](#onhide) Если `OLEIVERB_HIDE` указано. Реализация по умолчанию вызывает `OnShow` Если `iVerb` не является одной из команд, перечисленных выше.  
  
 Переопределите эту функцию, если ваш первичный глагол нет элемента. Например если элемент является запись звука и ее первичный глагол Play, вы не для отображения серверного приложения для воспроизведения элемента.  
  
 Дополнительные сведения см. в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameondrawa--coleserveritemondraw"></a><a name="ondraw"></a>COleServerItem::OnDraw  
 Вызывается платформой для отрисовки элемента OLE в метафайл.  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объекта, на котором выполняется отрисовка элемента. В контексте отображения автоматически подключается к контексте отображения атрибута, может вызывать функции атрибута, несмотря на то, что это сделает метафайл конкретного устройства.  
  
 `rSize`  
 Размер, в **HIMETRIC** единицы, в котором будет размещено в метафайл.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент успешно рисования; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Представление метафайла объекта OLE используется для отображения элемента в приложении-контейнере. Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, метафайл используется [рисовать](../../mfc/reference/coleclientitem-class.md#draw) функции-члена соответствующего [COleClientItem](../../mfc/reference/coleclientitem-class.md) объекта. Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию для рисования элемента в указанный контекст устройства.  
  
##  <a name="a-nameondrawexa--coleserveritemondrawex"></a><a name="ondrawex"></a>COleServerItem::OnDrawEx  
 Вызывается платформой для всех операций рисования.  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на [CDC](../../mfc/reference/cdc-class.md) объекта, на котором выполняется отрисовка элемента. Контроллер домена автоматически подключается к атрибута контроллера домена, может вызывать функции атрибута, несмотря на то, что это сделает метафайл конкретного устройства.  
  
 `nDrawAspect`  
 Значение из перечисления `DVASPECT`. Этот параметр может иметь любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
 `rSize`  
 Размер элемента в **HIMETRIC** единиц.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент успешно рисования; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `OnDraw` при `DVASPECT` равен `DVASPECT_CONTENT`; в противном случае происходит сбой.  
  
 Переопределить эту функцию для предоставления данных презентации для аспекты, отличные от `DVASPECT_CONTENT`, такие как `DVASPECT_ICON` или `DVASPECT_THUMBNAIL`.  
  
##  <a name="a-nameongetclipboarddataa--coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 Вызывается платформой для получения `COleDataSource` объект, содержащий все данные, которые следует поместить в буфер обмена с помощью вызова [CopyToClipboard](#copytoclipboard) функции-члена.  
  
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
 Смещение указателя мыши от начала координат объекта в пикселях.  
  
 `lpSize`  
 Размер объекта в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные из буфера обмена.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [GetClipboardData](#getclipboarddata).  
  
##  <a name="a-nameongetextenta--coleserveritemongetextent"></a><a name="ongetextent"></a>COleServerItem::OnGetExtent  
 Вызывается платформой для определения размера в **HIMETRIC** единиц объекта OLE.  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого должны быть получены. Этот параметр может иметь любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
 `rSize`  
 Ссылка на `CSize` объекта, который будет получить размер объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) соответствующего функцию-член `COleClientItem` вызывается. Реализация по умолчанию не выполняет никаких действий. Он должен реализовать самостоятельно. Переопределите эту функцию, если вы хотите выполнять специальную обработку при обработке запроса для определения размера элемента OLE.  
  
##  <a name="a-nameonhidea--coleserveritemonhide"></a><a name="onhide"></a>COleServerItem::OnHide  
 Вызывается платформой для скрытия элемента OLE.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию вызывает **COleServerDoc::OnShowDocument (FALSE)**. Функция также уведомляет о контейнере скрытый элемент OLE. Переопределите эту функцию, если вы хотите выполнять специальную обработку при скрытие элемента OLE.  
  
##  <a name="a-nameoninitfromdataa--coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 Вызывается средой для инициализации объекта OLE, используя содержимое `pDataObject`.  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Указатель на объект данных OLE, содержащий данные в различных форматах для инициализации объекта OLE.  
  
 `bCreation`  
 **Значение TRUE,** Если функция вызывается для инициализации объекта OLE, вновь создаваемого приложения-контейнера. **FALSE** Если функция вызывается для замены содержимого уже существующего элемента OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `bCreation` — **TRUE**, эта функция вызывается в том случае, если контейнер реализует вставки нового объекта на основе текущего выделения. Данные, выбранные используется при создании нового объекта OLE. Например, при Выбор диапазона ячеек в электронную, а затем создайте диаграмму с помощью вставить новый объект на основе значения из выбранного диапазона. Реализация по умолчанию не выполняет никаких действий. Переопределить эту функцию, чтобы выбрать допустимый формат по сравнению с предлагаемой `pDataObject` и инициализации объекта OLE, на основе предоставленных данных. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonopena--coleserveritemonopen"></a><a name="onopen"></a>COleServerItem::OnOpen  
 Вызывается платформой для отображения объекта OLE в отдельном экземпляре серверного приложения, а не на месте.  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию активирует первое окно фрейма, отображение документа, который содержит элемент OLE. Если приложение является мини-сервер, реализация по умолчанию показывает главного окна. Функция также уведомляет о контейнере открывавшихся объекта OLE.  
  
 Переопределите эту функцию, если вы хотите выполнять специальную обработку при открытии объекта OLE. Это самая распространенная связанных элементов, где требуется задавать выбранные ссылки при его открытии.  
  
 Дополнительные сведения см. в разделе [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonqueryupdateitemsa--coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 Вызывается платформой для определения, устарела ли все связанные элементы в текущем документе сервера.  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ содержит элементы, требующие обновления. 0, если все элементы в актуальном состоянии.  
  
### <a name="remarks"></a>Примечания  
 Элемент является устаревшим, если его исходный документ был изменен, но связанный элемент не был обновлен для отражения изменений в документе.  
  
##  <a name="a-nameonrenderdataa--coleserveritemonrenderdata"></a><a name="onrenderdata"></a>COleServerItem::OnRenderData  
 Вызывается платформой для получения данных в указанном формате.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `lpStgMedium`  
 Указывает [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, в котором возвращаются данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) или [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция вызывает [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData](#onrenderglobaldata), соответственно, если указанный носитель файле или памяти. Если ни один из этих форматов не предоставлен, реализация по умолчанию возвращает значение 0 и не выполняет никаких действий.  
  
 Если `lpStgMedium` ->  *tymed* — **TYMED_NULL**, **STGMEDIUM** следует выделить и заполняются в соответствии с *lpFormatEtc-> tymed*. Если не **TYMED_NULL**, **STGMEDIUM** должно быть заполнено месте с данными.  
  
 Существует расширенная переопределяемыми. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если данные фиксированного размера и небольшой, переопределите `OnRenderGlobalData`. Если данные в файле или имеет переменный размер, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), и [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonrenderfiledataa--coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 Вызывается платформой для получения данных в указанном формате, если среда хранения представляет собой файл.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `pFile`  
 Указывает на `CFile` объект, в котором для визуализации данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Существует расширенная переопределяемыми. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если требуется обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределить [OnRenderFileData](#onrenderfiledata).  
  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonrenderglobaldataa--coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
 Вызывается платформой для получения данных в указанном формате, если указанный носитель является глобальной памяти.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `phGlobal`  
 Указывает дескриптор глобальной памяти, в котором не возвращаются данные. Если выделена память, этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Если `phGlobal` — **NULL**, затем новый `HGLOBAL` следует выделить и возвращается в `phGlobal`. В противном случае — `HGLOBAL` определяется `phGlobal` должен быть заполнен данными. Объем данных, помещаются в `HGLOBAL` не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен до большего размера.  
  
 Существует расширенная переопределяемыми. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если требуется обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределить [OnRenderFileData](#onrenderfiledata).  
  
 Дополнительные сведения см. в разделе [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonsetcolorschemea--coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 Вызывается платформой для указания цветовую палитру для использования при редактировании объекта OLE.  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `lpLogPalette`  
 Указатель на Windows [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если используется цветовая палитра; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложения-контейнера, написанный с использованием библиотеки Microsoft Foundation Class, эта функция вызывается, когда [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) функция соответствующего `COleClientItem` объекта вызывается. Реализация по умолчанию возвращает **FALSE**. Переопределите эту функцию, если вы хотите использовать рекомендованную палитру. Серверное приложение не требуется для использования предлагаемую палитру.  
  
 Дополнительные сведения см. в разделе [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonsetdataa--coleserveritemonsetdata"></a><a name="onsetdata"></a>COleServerItem::OnSetData  
 Вызывается платформой для замены данных объекта OLE с заданными данными.  
  
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
 Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающая сторона определяет, кто несет ответственность за освобождение ресурсов, выделенной среду хранения. Вызывающий объект устанавливается не `bRelease`. Если `bRelease` имеет ненулевое значение, серверный элемент получает право на владение, освобождение носителя после завершения его использования. Когда `bRelease` имеет значение 0, вызывающий объект сохраняет владение и серверного элемента можно использовать среду хранения только во время выполнения вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Серверный элемент не распоряжаться данных пока он успешно получил его. То есть он не стать владельцем, если она возвращает 0. Если источник данных становится владельцем, он освобождает среду хранения путем вызова [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) функции.  
  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для замены данных объекта OLE с заданными данными. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), и [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonsetextenta--coleserveritemonsetextent"></a><a name="onsetextent"></a>COleServerItem::OnSetExtent  
 Вызывается средой определить элемент OLE объем доступных в документе-контейнере.  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>Параметры  
 `nDrawAspect`  
 Указывает аспект объекта OLE, границы которого были заданы. Этот параметр может иметь любое из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
 `size`  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) структуры, указав новый размер объекта OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) соответствующего функцию-член `COleClientItem` вызывается. Наборы данных для реализации по умолчанию [m_sizeExtent](#m_sizeextent) элемента заданного размера при `nDrawAspect` — `DVASPECT_CONTENT`; в противном случае возвращается 0. Переопределите эту функцию, чтобы выполнять специальную обработку при изменении размера элемента.  
  
##  <a name="a-nameonshowa--coleserveritemonshow"></a><a name="onshow"></a>COleServerItem::OnShow  
 Вызывается платформой для указания серверное приложение для отображения объекта OLE в месте.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается, когда пользователь приложения-контейнера создает элемент или выполняет команды, такие как изменение, требующее, чтобы элемент будет отображаться. Реализация по умолчанию попыток активации на месте. Если это не удается, вызовы функций `OnOpen` функции-члена для отображения объекта OLE в отдельном окне.  
  
 Переопределите эту функцию, если вы хотите выполнять специальную обработку при отображении элемента OLE.  
  
##  <a name="a-nameonupdatea--coleserveritemonupdate"></a><a name="onupdate"></a>COleServerItem::OnUpdate  
 Вызывается инфраструктурой при изменении элемента.  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Параметры  
 `pSender`  
 Указатель на элемент, измененный документ. Может быть **NULL**.  
  
 `lHint`  
 Содержит сведения об изменении.  
  
 `pHint`  
 Указатель на объект, хранения информации о изменения.  
  
 `nDrawAspect`  
 Значение из перечисления `DVASPECT`. Этот параметр может принимать одно из следующих значений:  
  
- `DVASPECT_CONTENT`Элемент представлен таким образом, он может отображаться в виде внедренного объекта внутри контейнера.  
  
- `DVASPECT_THUMBNAIL`Элемент отображается в представлении «эскиз», чтобы оно отображается в средствах просмотра.  
  
- `DVASPECT_ICON`Элемент представлен значком.  
  
- `DVASPECT_DOCPRINT`Элемент представлен, как если бы печати с помощью команды печати из меню «файл».  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [NotifyChanged](#notifychanged), независимо от того, указание или отправителя.  
  
##  <a name="a-nameonupdateitemsa--coleserveritemonupdateitems"></a><a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 Вызывается платформой для обновления всех элементов на серверном документе.  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) для всех `COleClientItem` объектов в документе.  
  
##  <a name="a-namesetitemnamea--coleserveritemsetitemname"></a><a name="setitemname"></a>COleServerItem::SetItemName  
 Эта функция вызывается при создании связанного элемента, чтобы задать его имя.  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItemName`  
 Указатель на имя нового элемента.  
  
### <a name="remarks"></a>Примечания  
 Имя должно быть уникальным в пределах документа. При вызове серверного приложения для редактирования связанный элемент, приложение использует это имя для поиска элемента. Эта функция вызывается для встроенных элементов необязательно.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс CDocItem](../../mfc/reference/cdocitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)

