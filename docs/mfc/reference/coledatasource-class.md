---
title: Класс COleDataSource
ms.date: 11/04/2016
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
ms.openlocfilehash: 062234b9bc3c538e8cd5fcade002a2892eea259f
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741623"
---
# <a name="coledatasource-class"></a>Класс COleDataSource

Играет роль кэша, в который приложение помещает данные, которые оно будет предлагать во время операций передачи данных, таких как операции с буфером обмена или операции перетаскивания.

## <a name="syntax"></a>Синтаксис

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleDataSource:: COleDataSource](#coledatasource)|Создает объект `COleDataSource`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleDataSource:: Качедата](#cachedata)|Предоставляет данные в указанном формате с помощью `STGMEDIUM` структуры.|
|[COleDataSource:: Качеглобалдата](#cacheglobaldata)|Предоставляет данные в указанном формате с помощью ХГЛОБАЛ.|
|[COleDataSource::D Елайрендердата](#delayrenderdata)|Предоставляет данные в указанном формате с помощью отложенной отрисовки.|
|[COleDataSource::D Елайрендерфиледата](#delayrenderfiledata)|Предлагает данные в указанном формате в `CFile` указателе.|
|[COleDataSource::D Елайсетдата](#delaysetdata)|Вызывается для каждого формата, поддерживаемого `OnSetData`в.|
|[COleDataSource::D Одрагдроп](#dodragdrop)|Выполняет операции перетаскивания с источником данных.|
|[COleDataSource:: Empty](#empty)|`COleDataSource` Очищает объект данных.|
|[COleDataSource:: Флушклипбоард](#flushclipboard)|Отображает все данные в буфере обмена.|
|[COleDataSource:: Жетклипбоардовнер](#getclipboardowner)|Проверяет, что данные, помещенные в буфер обмена, остались там.|
|[COleDataSource:: Онрендердата](#onrenderdata)|Извлекает данные в рамках отложенной отрисовки.|
|[COleDataSource:: Онрендерфиледата](#onrenderfiledata)|Извлекает данные в `CFile` как часть отложенной отрисовки.|
|[COleDataSource:: Онрендерглобалдата](#onrenderglobaldata)|Извлекает данные в ХГЛОБАЛ в рамках отложенной подготовки к просмотру.|
|[COleDataSource:: Онсетдата](#onsetdata)|Вызывается для замены данных в `COleDataSource` объекте.|
|[COleDataSource:: Сетклипбоард](#setclipboard)|Помещает `COleDataSource` объект в буфер обмена.|

## <a name="remarks"></a>Примечания

Источники данных OLE можно создавать напрямую. Кроме того, классы [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md) создают источники данных OLE в ответ на их `CopyToClipboard` функции и `DoDragDrop` члены. Краткое описание см. в разделе [COleServerItem:: копитоклипбоард](../../mfc/reference/coleserveritem-class.md#copytoclipboard) . Переопределите функцию `CopyToClipboard` `DoDragDrop` члена клиентского элемента или класса серверного элемента, чтобы добавить дополнительные форматы буфера обмена для данных в источнике данных OLE, созданном для функции члена или. `OnGetClipboardData`

При необходимости подготовки данных для перемещения следует создать объект этого класса и заполнить его данными с помощью наиболее подходящего метода для данных. Способ вставки данных в источник данных напрямую зависит от того, предоставлены ли данные немедленно (немедленное отображение) или по запросу (отложенная визуализация). Для каждого формата буфера обмена, в котором данные предоставляются путем передачи используемого формата буфера обмена (и необязательной структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) ), вызовите [делайрендердата](#delayrenderdata).

Дополнительные сведения об источниках данных и передаваемых данных см. в статье [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Кроме того, в [разделах, посвященных буферу](../../mfc/clipboard.md) обмена статей, ОПИСЫВАЕТСЯ механизм OLE Clipboard.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="cachedata"></a>COleDataSource:: Качедата

Вызовите эту функцию, чтобы указать формат, в котором данные предоставляются во время операций по переносу данных.

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат буфера обмена, в котором будут предложены данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпстгмедиум*<br/>
Указывает на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) , содержащую данные в указанном формате.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором будут предложены данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="remarks"></a>Примечания

Необходимо указать данные, так как эта функция предоставляет ее с помощью немедленного отображения. Данные кэшируются, пока не потребуются.

Укажите данные с помощью структуры [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) . Вы также можете использовать функцию `CacheGlobalData` -член, если объем предоставленных данных достаточно мал для эффективного переноса с помощью хглобал.

`CacheData` После вызова `ptd` члена и`lpFormatEtc` содержимого *лпстгмедиум* объект данных не является вызывающим объектом.

Чтобы использовать отложенную отрисовку, вызовите функцию члена [делайрендердата](#delayrenderdata) или [делайрендерфиледата](#delayrenderfiledata) . Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Дополнительные сведения см. в разделе структуры [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="cacheglobaldata"></a>COleDataSource:: Качеглобалдата

Вызовите эту функцию, чтобы указать формат, в котором данные предоставляются во время операций по переносу данных.

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат буфера обмена, в котором будут предложены данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*хглобал*<br/>
Обработчик для глобального блока памяти, содержащего данные в указанном формате.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором будут предложены данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция предоставляет данные с помощью немедленного отображения, поэтому при вызове функции необходимо указать данные. данные кэшируются, пока не потребуются. Используйте функцию `CacheData` -член, если вы предоставляете большой объем данных или если требуется структурированный носитель хранилища.

Чтобы использовать отложенную отрисовку, вызовите функцию члена [делайрендердата](#delayrenderdata) или [делайрендерфиледата](#delayrenderfiledata) . Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Дополнительные сведения см. в описании структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="coledatasource"></a>COleDataSource:: COleDataSource

Создает объект `COleDataSource`.

```
COleDataSource();
```

##  <a name="delayrenderdata"></a>COleDataSource::D Елайрендердата

Вызовите эту функцию, чтобы указать формат, в котором данные предоставляются во время операций по переносу данных.

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат буфера обмена, в котором будут предложены данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором будут предложены данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция предоставляет данные с помощью отложенной отрисовки, поэтому данные не предоставляются немедленно. Для запроса данных вызывается функция-член [онрендердата](#onrenderdata) или [онрендерглобалдата](#onrenderglobaldata) .

Используйте эту функцию, если вы не собираетесь предоставлять данные через `CFile` объект. Если данные будут предоставлены через `CFile` объект, вызовите функцию-член [делайрендерфиледата](#delayrenderfiledata) . Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Чтобы использовать немедленное отображение, вызовите функцию члена [качедата](#cachedata) или [качеглобалдата](#cacheglobaldata) .

Дополнительные сведения см. в описании структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="delayrenderfiledata"></a>COleDataSource::D Елайрендерфиледата

Вызовите эту функцию, чтобы указать формат, в котором данные предоставляются во время операций по переносу данных.

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат буфера обмена, в котором будут предложены данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором будут предложены данные. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция предоставляет данные с помощью отложенной отрисовки, поэтому данные не предоставляются немедленно. Функция-член [онрендерфиледата](#onrenderfiledata) вызывается для запроса данных.

Используйте эту функцию, если вы собираетесь использовать `CFile` объект для передачи данных. Если вы не собираетесь использовать `CFile` объект, вызовите функцию-член [делайрендердата](#delayrenderdata) . Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Чтобы использовать немедленное отображение, вызовите функцию члена [качедата](#cachedata) или [качеглобалдата](#cacheglobaldata) .

Дополнительные сведения см. в описании структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="delaysetdata"></a>COleDataSource::D Елайсетдата

Вызывайте эту функцию для поддержки изменения содержимого источника данных.

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*кфформат*<br/>
Формат буфера обмена, в котором должны размещаться данные. Этот параметр может быть одним из стандартных форматов буфера обмена или значением, возвращаемым собственной функцией [Регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) Windows.

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , описывающую формат, в котором данные должны быть заменены. Укажите значение для этого параметра, если требуется указать дополнительные сведения о форматировании после формата буфера обмена, заданного параметром *кфформат*. Если он имеет значение null, для других полей в `FORMATETC` структуре используются значения по умолчанию.

### <a name="remarks"></a>Примечания

В этом случае [онсетдата](#onsetdata) будет вызываться платформой. Используется только в том случае, если платформа Возвращает источник данных из [COleServerItem::-DataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Если `DelaySetData` не вызывается `OnSetData` , функция никогда не будет вызываться. `DelaySetData`должен вызываться для каждого поддерживаемого `FORMATETC` буфера обмена или формата.

Дополнительные сведения см. в описании структуры [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

Дополнительные сведения см. в разделе [регистерклипбоардформат](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

##  <a name="dodragdrop"></a>COleDataSource::D Одрагдроп

Вызовите `DoDragDrop` функцию- члендлявыполненияоперацииперетаскиваниядляэтогоисточникаданных,какправило,вобработчике [CWnd:: OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>Параметры

*двеффектс*<br/>
Операции перетаскивания, разрешенные для этого источника данных. Может быть одним или несколькими из следующих:

- DROPEFFECT_COPY может быть выполнена операция копирования.

- DROPEFFECT_MOVE операция перемещения может быть выполнена.

- DROPEFFECT_LINK можно установить ссылку из удаленных данных в исходные.

- DROPEFFECT_SCROLL указывает, что может произойти операция перетаскивания.

*лпректстартдраг*<br/>
Указатель на прямоугольник, который определяет, где фактически начинается перетаскивание. Дополнительные сведения см. в разделе "Примечания".

*пдропсаурце*<br/>
Указывает на источник перетаскивания. Если значение равно NULL, будет использоваться реализация [коледропсаурце](../../mfc/reference/coledropsource-class.md) по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Действие перетаскивания, созданное операцией перетаскивания; в противном случае DROPEFFECT_NONE, если операция никогда не начинается, поскольку пользователь отпускает кнопку мыши до выхода из предоставленного прямоугольника.

### <a name="remarks"></a>Примечания

Операция перетаскивания не запускается немедленно. Он ждет, пока курсор мыши не покидает прямоугольник, заданный параметром *лпректстартдраг* , или до тех пор, пока не пройдет указанное число миллисекунд. Если *лпректстартдраг* имеет значение null, размер прямоугольника равен одному пикселю.

Время задержки задается параметром раздела реестра. Время задержки можно изменить, вызвав [CWinApp:: вритепрофилестринг](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp:: вритепрофилеинт](../../mfc/reference/cwinapp-class.md#writeprofileint). Если не указать время задержки, используется значение по умолчанию 200 миллисекунд. Время задержки перетаскивания сохраняется следующим образом:

- Время задержки перетаскивания Windows NT хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.

- Время задержки перетаскивания Windows 3. x сохраняется в ВЫИГРЫШе. INI-файл в разделе [Windows}.

- Время задержки перетаскивания Windows 95/98 хранится в кэшированной версии WIN. Ссылки.

Дополнительные сведения о том, как данные задержки перетаскивания хранятся в реестре или в. INI-файла см. в разделе [вритепрофилестринг](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) в Windows SDK.

Дополнительные сведения см. в статье [перетаскивание: Реализация источника](../../mfc/drag-and-drop-implementing-a-drop-source.md)удаления.

##  <a name="empty"></a>COleDataSource:: Empty

Вызовите эту функцию, чтобы `COleDataSource` очистить объект данных.

```
void Empty();
```

### <a name="remarks"></a>Примечания

Форматы кэширования и отложенной визуализации очищены, поэтому их можно использовать повторно.

Дополнительные сведения см. в разделе [релеасестгмедиум](/windows/win32/api/ole2/nf-ole2-releasestgmedium) в Windows SDK.

##  <a name="flushclipboard"></a>COleDataSource:: Флушклипбоард

Отрисовывает данные, наявляющиеся в буфере обмена, а затем позволяет вставлять данные из буфера обмена после завершения работы приложения.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>Примечания

Используйте [сетклипбоард](#setclipboard) для размещения данных в буфере обмена.

##  <a name="getclipboardowner"></a>COleDataSource:: Жетклипбоардовнер

Определяет, изменились ли данные в буфере обмена с момента последнего вызова [сетклипбоард](#setclipboard) и, если да, определяет текущего владельца.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>Возвращаемое значение

Источник данных, находящийся в буфере обмена, или значение NULL, если в буфере нет ничего или если буфер обмена не принадлежит вызывающему приложению.

##  <a name="onrenderdata"></a>COleDataSource:: Онрендердата

Вызывается платформой для получения данных в указанном формате.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором запрашиваются сведения.

*лпстгмедиум*<br/>
Указывает на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) , в которой должны возвращаться данные.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Указанный формат — один, ранее помещенный в `COleDataSource` объект с помощью функции-члена [делайрендердата](#delayrenderdata) или [делайрендерфиледата](#delayrenderfiledata) для отложенной отрисовки. Реализация по умолчанию этой функции будет вызывать [онрендерфиледата](#onrenderfiledata) или [онрендерглобалдата](#onrenderglobaldata) , если указанный носитель является либо файлом, либо памятью соответственно. Если ни один из этих форматов не указан, реализация по умолчанию возвратит 0 и не выполняет никаких действий. Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Если *лпстгмедиум*-> *тимед* имеет значение TYMED_NULL, `STGMEDIUM` то должно быть выделено и заполнено, как указано *лпформатетк-> тимед*. Если это не TYMED_NULL, `STGMEDIUM` необходимо заполнить данные.

Это расширенный переопределяемый объект. Переопределите эту функцию, чтобы предоставить данные в запрошенном формате и среднем. В зависимости от данных может потребоваться переопределить одну из других версий этой функции. Если данные невелики и имеют фиксированный размер, `OnRenderGlobalData`Переопределите. Если данные находятся в файле или имеют переменный размер, переопределите `OnRenderFileData`.

Дополнительные сведения см. в разделе структуры [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) и [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , тип перечисления [Тимед](/windows/win32/api/objidl/ne-objidl-tymed) и [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

##  <a name="onrenderfiledata"></a>COleDataSource:: Онрендерфиледата

Вызывается платформой для получения данных в указанном формате, если указанный носитель является файлом.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором запрашиваются сведения.

*pFile*<br/>
Указывает на объект [кфиле](../../mfc/reference/cfile-class.md) , в котором должны быть визуализированы данные.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Указанный формат — один, ранее помещенный в `COleDataSource` объект с помощью функции-члена [делайрендердата](#delayrenderdata) для отложенной отрисовки. Реализация по умолчанию этой функции просто возвращает значение FALSE.

Это расширенный переопределяемый объект. Переопределите эту функцию, чтобы предоставить данные в запрошенном формате и среднем. В зависимости от данных может потребоваться переопределить одну из других версий этой функции. Если требуется работать с несколькими носителями хранилища, переопределите [онрендердата](#onrenderdata). Если данные находятся в файле или имеют переменный размер, переопределите `OnRenderFileData`. Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Дополнительные сведения см. в разделе Структура [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) и [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

##  <a name="onrenderglobaldata"></a>COleDataSource:: Онрендерглобалдата

Вызывается платформой для получения данных в указанном формате, если указанный носитель является глобальной памятью.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором запрашиваются сведения.

*фглобал*<br/>
Указывает на указатель на глобальную память, в которой должны возвращаться данные. Если он еще не выделен, этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Указанный формат — один, ранее помещенный в `COleDataSource` объект с помощью функции-члена [делайрендердата](#delayrenderdata) для отложенной отрисовки. Реализация по умолчанию этой функции просто возвращает значение FALSE.

Если *фглобал* имеет значение null, то новый хглобал должен быть выделен и возвращен в *фглобал*. В противном случае ХГЛОБАЛ, заданный параметром *фглобал* , должен быть заполнен данными. Объем данных, помещаемых в ХГЛОБАЛ, не должен превышать текущий размер блока памяти. Кроме того, блок нельзя перераспределить до большего размера.

Это расширенный переопределяемый объект. Переопределите эту функцию, чтобы предоставить данные в запрошенном формате и среднем. В зависимости от данных может потребоваться переопределить одну из других версий этой функции. Если требуется работать с несколькими носителями хранилища, переопределите [онрендердата](#onrenderdata). Если данные находятся в файле или имеют переменный размер, переопределите [онрендерфиледата](#onrenderfiledata). Дополнительные сведения о отложенной отрисовке, обрабатываемой MFC, см. [в статьях объекты данных и источники данных. Обработка](../../mfc/data-objects-and-data-sources-manipulation.md).

Дополнительные сведения см. в разделе Структура [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) и [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

##  <a name="onsetdata"></a>COleDataSource:: Онсетдата

Вызывается платформой для задания или замены данных в `COleDataSource` объекте в указанном формате.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Параметры

*лпформатетк*<br/>
Указывает на структуру [форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) , указывающую формат, в котором заменяются данные.

*лпстгмедиум*<br/>
Указывает на структуру [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) , содержащую данные, которые будут заменять текущее содержимое `COleDataSource` объекта.

*брелеасе*<br/>
Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающий объект решает, кто отвечает за освобождение ресурсов, выделенных от имени среды хранения. Вызывающий объект делает это, настроив *брелеасе*. Если *брелеасе* имеет ненулевое значение, источник данных берет на себя владение, освобождая носитель по завершении его использования. Если *брелеасе* имеет значение 0, вызывающий объект удерживает владение, и источник данных может использовать среду хранения только на время вызова.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Источник данных не принимает владение данными, пока он не будет успешно получен. То есть он не принимает владение, если `OnSetData` возвращает 0. Если источник данных принимает владение, он освобождает среду хранения, вызывая функцию [релеасестгмедиум](/windows/win32/api/ole2/nf-ole2-releasestgmedium) .

Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию, чтобы заменить данные в указанном формате. Это расширенный переопределяемый объект.

Дополнительные сведения см. в разделе структуры [стгмедиум](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) и [Форматетк](/windows/win32/api/objidl/ns-objidl-formatetc) и функции [Релеасестгмедиум](/windows/win32/api/ole2/nf-ole2-releasestgmedium) и [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в Windows SDK.

##  <a name="setclipboard"></a>COleDataSource:: Сетклипбоард

Помещает данные, содержащиеся `COleDataSource` в объекте, в буфер обмена после вызова одной из следующих функций: [Качедата](#cachedata), [качеглобалдата](#cacheglobaldata), [делайрендердата](#delayrenderdata)или [делайрендерфиледата](#delayrenderfiledata).

```
void SetClipboard();
```

## <a name="see-also"></a>См. также

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDataObject](../../mfc/reference/coledataobject-class.md)
