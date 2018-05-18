---
title: Класс COleDataSource | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4df2584bd9b74640266d8ddf87087e2820deaac8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="coledatasource-class"></a>COleDataSource-класс
Играет роль кэша, в который приложение помещает данные, которые оно будет предлагать во время операций передачи данных, таких как операции с буфером обмена или операции перетаскивания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|Создает объект `COleDataSource`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDataSource::CacheData](#cachedata)|Предоставляет данные в указанном формате, используя **STGMEDIUM** структуры.|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|Предоставляет данные в указанном формате, используя `HGLOBAL`.|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|Предоставляет данные в указанном формате, с использованием отложенной подготовки к просмотру.|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|Предоставляет данные в указанном формате в `CFile` указателя.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Вызывается для каждого формата, поддерживаемого в `OnSetData`.|  
|[COleDataSource::DoDragDrop](#dodragdrop)|Выполняет операции перетаскивания и вставки с источником данных.|  
|[COleDataSource::Empty](#empty)|Очищает `COleDataSource` объект данных.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Отображает все данные в буфер обмена.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Проверяет, что данные, помещенные в буфер обмена по-прежнему возможна.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Извлекает данные в рамках отложенной подготовки к просмотру.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Получает данные в `CFile` как часть отложенной подготовки к просмотру.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Получает данные в `HGLOBAL` как часть отложенной подготовки к просмотру.|  
|[COleDataSource::OnSetData](#onsetdata)|Вызывается для замены данных в `COleDataSource` объекта.|  
|[COleDataSource::SetClipboard](#setclipboard)|Окружение `COleDataSource` объектов в буфер обмена.|  
  
## <a name="remarks"></a>Примечания  
 Можно создавать источники данных OLE напрямую. Кроме того [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md) классы создают источников данных OLE в ответ на их `CopyToClipboard` и `DoDragDrop` функции-члены. В разделе [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) краткое описание. Переопределить `OnGetClipboardData` созданные функции-члена класса клиента элемента или сервер элемента будут добавляться дополнительные форматы буфера обмена данные в источнике данных OLE для `CopyToClipboard` или `DoDragDrop` функции-члена.  
  
 Каждый раз, когда вы хотите подготовить данные для передачи, следует создать объект этого класса и заполнить его данных с использованием наиболее подходящий метод для своих данных. Способ вставки в источник данных непосредственно зависит от ли немедленно заданы данные (немедленно подготовки) или по требованию (отложенная отрисовка). Для каждого формата буфера обмена, в котором данные предоставляются путем передачи формат буфера обмена для использования (необязательный [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры), вызовите [DelayRenderData](#delayrenderdata).  
  
 Дополнительные сведения об источниках данных и передача данных см. в статье [объектов данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Кроме того, статья [разделы буфер обмена](../../mfc/clipboard.md) Описание механизма буфера обмена OLE.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="cachedata"></a>  COleDataSource::CacheData  
 Эта функция используется для указания формата, в котором данные предлагается данных операций передачи.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpStgMedium`  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, содержащую данные в указанный формат.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором будет предлагаться данные. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать данные, поскольку эта функция обеспечивает его с помощью интерпретации подготовки к просмотру. Данные кэшируются, пока не требуется.  
  
 Предоставьте данные с помощью [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры. Можно также использовать `CacheGlobalData` функции-члена при указании объем данных слишком мало для передачи эффективно с использованием `HGLOBAL`.  
  
 После вызова `CacheData` **ptd** членом `lpFormatEtc` и содержимое `lpStgMedium` принадлежат объект данных не вызывающим объектом.  
  
 Использование отложенной подготовки к просмотру, вызовите [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функции-члена. Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData  
 Эта функция используется для указания формата, в котором данные предлагается данных операций передачи.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *hGlobal*  
 Дескриптор глобальной памяти блок, содержащий данные в указанный формат.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором будет предлагаться данные. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью немедленно модуль подготовки отчетов, поэтому необходимо указать данные, при вызове функции; данные кэшируются, пока не требуется. Используйте `CacheData` функция-член, если вы указали большой объем данных или если требуется средний структурированного хранилища.  
  
 Использование отложенной подготовки к просмотру, вызовите [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функции-члена. Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="coledatasource"></a>  COleDataSource::COleDataSource  
 Создает объект `COleDataSource`.  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData  
 Эта функция используется для указания формата, в котором данные предлагается данных операций передачи.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором будет предлагаться данные. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью отложенной подготовки к просмотру, поэтому данные не предоставляются непосредственно. [OnRenderData](#onrenderdata) или [OnRenderGlobalData](#onrenderglobaldata) функция-член вызывается для запроса данных.  
  
 Используйте эту функцию, если вы не собираетесь предоставить данные с помощью `CFile` объекта. Если необходимо предоставить данные с помощью `CFile` , вызовите [DelayRenderFileData](#delayrenderfiledata) функции-члена. Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Чтобы использовать немедленное отрисовки, вызовите [CacheData](#cachedata) или [CacheGlobalData](#cacheglobaldata) функции-члена.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData  
 Эта функция используется для указания формата, в котором данные предлагается данных операций передачи.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором будет предлагаться данные. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью отложенной подготовки к просмотру, поэтому данные не предоставляются непосредственно. [OnRenderFileData](#onrenderfiledata) функция-член вызывается для запроса данных.  
  
 Используйте эту функцию, если планируется использовать `CFile` объект в качестве источника данных. Если вы не собираетесь использовать `CFile` , вызовите [DelayRenderData](#delayrenderdata) функции-члена. Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Чтобы использовать немедленное отрисовки, вызовите [CacheData](#cachedata) или [CacheGlobalData](#cacheglobaldata) функции-члена.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData  
 Эта функция поддерживает изменение содержимого источника данных.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет размещаться данные. Этот параметр может принимать одно из стандартных форматов буфера обмена или значения, возвращенного приложениями Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором необходимо заменить данные. Укажите значение для этого параметра, если вы хотите указать формат дополнительных сведений Помимо буфера обмена с форматом, заданным `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 [OnSetData](#onsetdata) вызывается платформой, когда это происходит. Это используется, только когда платформа Возвращает источник данных, из [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Если `DelaySetData` не вызывается, ваш `OnSetData` функция никогда не будет вызываться. `DelaySetData` должен вызываться для каждого буфера обмена или **FORMATETC** требуется поддержка формата.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в Windows SDK.  
  
##  <a name="dodragdrop"></a>  COleDataSource::DoDragDrop  
 Вызовите `DoDragDrop` функции-члена для операции перетаскивания и вставки для этого источника данных, обычно в виде [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) обработчика.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwEffects`  
 И перетащите операции, разрешенные для этого источника данных. Может иметь одно или несколько из следующих:  
  
- `DROPEFFECT_COPY` Операция копирования может быть выполнена.  
  
- `DROPEFFECT_MOVE` Может быть выполнена операция перемещения.  
  
- `DROPEFFECT_LINK` Ссылка из перетаскиваемых данных с исходными данными может быть установлено.  
  
- `DROPEFFECT_SCROLL` Указывает, что может произойти прокрутки операции перетаскивания.  
  
 `lpRectStartDrag`  
 Указатель на прямоугольник, который определяет, где фактически начинает перетаскивание. Дополнительные сведения см. в разделе "Примечания".  
  
 *pDropSource*  
 Указывает источника перетаскивания. Если **NULL** затем реализацию по умолчанию [COleDropSource](../../mfc/reference/coledropsource-class.md) будет использоваться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Удалить эффект, созданные операцией перетаскивания и вставки; в противном случае `DROPEFFECT_NONE` Если операция никогда не начинается, так как пользователь отпущена перед выходом из предоставленного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Операции перетаскивания и вставки не начинается немедленно. Он ожидает, пока курсор мыши выходит за пределы прямоугольника, определяемого `lpRectStartDrag` или пока не были пройдены указанного числа миллисекунд. Если `lpRectStartDrag` — **NULL**, размер прямоугольника равно одному пикселю.  
  
 Время задержки задается параметр раздела реестра. Время задержки можно изменить путем вызова [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если время задержки не указан, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите хранится следующим образом:  
  
-   Время задержки Windows NT перетащите хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Время задержки перетащите 3.x Windows хранится в WIN. INI-файл, в разделе [Windows}.  
  
-   Время задержки Windows 95/98 перетащите хранится в кэшированная версия WIN. INI-ФАЙЛЕ.  
  
 Для перетащите Дополнительные сведения о том, как задержки сведения хранятся в реестре или. INI-файл, в разделе [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) в Windows SDK.  
  
 Дополнительные сведения см. в статье [перетаскивание: реализация источника Drop](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="empty"></a>  COleDataSource::Empty  
 Эта функция вызывается для пустой `COleDataSource` объект данных.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Примечания  
 Оба кэшируются и форматов подготовки к просмотру задержки очищаются, поэтому они могут использоваться повторно.  
  
 Дополнительные сведения см. в разделе [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) в Windows SDK.  
  
##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard  
 Отображает данные, в буфере обмена, а затем позволяет вставлять данные из буфера обмена после закрытия приложения.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [SetClipboard](#setclipboard) поместить данные в буфер обмена.  
  
##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner  
 Определяет, является ли данные в буфере обмена была изменена с момента [SetClipboard](#setclipboard) последнего вызова метода и если да, идентифицирует текущий владелец.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Источник данных в данный момент в буфере обмена или **NULL** Если нет ничего в буфер обмена или буфера обмена не является владельцем вызывающего приложения.  
  
##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData  
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
 Указанный формат является одним помещенный в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция будет вызывать [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData](#onrenderglobaldata) Если указанный носитель файла или памяти, соответственно. Если не указано ни одно из этих форматов, реализация по умолчанию возвращает значение 0 и не выполняют никаких действий. Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Если `lpStgMedium` ->  *tymed* — **TYMED_NULL**, **STGMEDIUM** следует выделять и заполнены в соответствии с *lpFormatEtc -> tymed*. Если это не **TYMED_NULL**, **STGMEDIUM** должно быть заполнено на месте с данными.  
  
 Существует расширенная overridable. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо него. Если данные хранятся в малых и фиксированного размера, переопределяют `OnRenderGlobalData`. Если данные в файле или является переменного размера, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) тип перечисления и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в Windows SDK.  
  
##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData  
 Вызывается платформой для извлечения данных в указанном формате, если указанный носитель — это файл.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `pFile`  
 Указывает на [CFile](../../mfc/reference/cfile-class.md) объект, в котором должен быть подготовлен к просмотру данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат является одним помещенный в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Существует расширенная overridable. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо него. Если для обработки нескольких носителей, необходимо переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределите `OnRenderFileData`. Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в Windows SDK.  
  
##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData  
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
 Указывает дескриптор глобальной памяти, в котором данные тоже должны быть возвращены. Если один еще не был выделен, этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат является одним помещенный в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Если `phGlobal` — **NULL**, затем новый `HGLOBAL` следует выделять и возвращаются в `phGlobal`. В противном случае `HGLOBAL` заданные `phGlobal` должно быть заполнено с данными. Объем данных помещаются в `HGLOBAL` не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен к значению большего размера.  
  
 Существует расширенная overridable. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо него. Если для обработки нескольких носителей, необходимо переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределите [OnRenderFileData](#onrenderfiledata). Дополнительные сведения о отложенной подготовки к просмотру как обработанное MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в Windows SDK.  
  
##  <a name="onsetdata"></a>  COleDataSource::OnSetData  
 Вызывается платформой для установки или замены данных в `COleDataSource` объекта в указанном формате.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат замены данных.  
  
 `lpStgMedium`  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, содержащую данные, который заменяет текущее содержимое `COleDataSource` объекта.  
  
 `bRelease`  
 Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающая сторона определяет, кто отвечает за освобождение ресурсов, выделенной среды хранения. Вызывающий объект устанавливается не `bRelease`. Если `bRelease` имеет ненулевое значение, источник данных принимает право на владение, освобождение среды после завершения его использования. Когда `bRelease` имеет значение 0, вызывающий объект продолжает владеть и источника данных можно использовать среду хранения только в течение всего вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Источник данных вступают в владения данных он получен успешно. То есть, он не стать владельцем, если `OnSetData` возвращает 0. Если источник данных принимает право на владение, он освобождает среду хранения путем вызова [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) функции.  
  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для замены данных в указанном формате. Существует расширенная overridable.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) функции в Windows SDK.  
  
##  <a name="setclipboard"></a>  COleDataSource::SetClipboard  
 Помещает данные, содержащиеся в `COleDataSource` объекта в буфере обмена после вызова одного из следующих функций: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), или [DelayRenderFileData](#delayrenderfiledata).  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDataObject](../../mfc/reference/coledataobject-class.md)
