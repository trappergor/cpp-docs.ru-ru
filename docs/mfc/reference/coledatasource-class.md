---
title: Класс COleDataSource | Документация Майкрософт
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
ms.openlocfilehash: 839068647a6f4d118e1536f5fb4e0852657d963f
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027785"
---
# <a name="coledatasource-class"></a>Класс COleDataSource
Играет роль кэша, в который приложение помещает данные, которые оно будет предлагать во время операций передачи данных, таких как операции с буфером обмена или операции перетаскивания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|Создает объект `COleDataSource`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDataSource::CacheData](#cachedata)|Предоставляет данные в указанном формате, используя `STGMEDIUM` структуры.|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|Предоставляет данные в указанном формате, используя HGLOBAL.|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|Предоставляет данные в указанном формате, с помощью отложенной подготовки к просмотру.|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|Предоставляет данные в указанном формате в `CFile` указатель.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Вызывается для каждого формата, который поддерживается в `OnSetData`.|  
|[COleDataSource::DoDragDrop](#dodragdrop)|Выполняет операции перетаскивания и вставки с источником данных.|  
|[COleDataSource::Empty](#empty)|Очищает `COleDataSource` объект данных.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Отображает все данные в буфер обмена.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Проверяет, что данные, помещенные в буфер обмена по-прежнему возможна.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Извлекает данные как часть отложенной подготовки к просмотру.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Извлекает данные в `CFile` как часть отложенной подготовки к просмотру.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Извлекает данные в HGLOBAL как часть отложенной подготовки к просмотру.|  
|[COleDataSource::OnSetData](#onsetdata)|Вызывается для замены данных в `COleDataSource` объекта.|  
|[COleDataSource::SetClipboard](#setclipboard)|Окружение `COleDataSource` объект в буфере обмена.|  
  
## <a name="remarks"></a>Примечания  
 Можно создать источники данных OLE напрямую. Кроме того [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md) классы создавать источники данных OLE в ответ на их `CopyToClipboard` и `DoDragDrop` функций-членов. См. в разделе [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) краткое описание. Переопределить `OnGetClipboardData` созданные функции-члена класса клиента элемента или сервера элемента будут добавляться дополнительные форматы буфера обмена данные в источнике данных OLE для `CopyToClipboard` или `DoDragDrop` функция-член.  
  
 Каждый раз, когда вы хотите подготовить данные для передачи, необходимо создать объект этого класса и заполнить его данные с помощью наиболее подходящий метод для ваших данных. Способ вставки в источник данных непосредственно зависит от ли данные, предоставляются немедленно (немедленное отрисовки) или по требованию (отложенная отрисовка). Для каждого формата буфера обмена, в котором данные предоставляются путем передачи формат буфера обмена для использования (и, при необходимости [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры), вызовите [DelayRenderData](#delayrenderdata).  
  
 Дополнительные сведения об источниках данных и передачи данных см. в статье [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Кроме того, статьи [разделы буфер обмена](../../mfc/clipboard.md) Описание механизма буфера обмена OLE.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="cachedata"></a>  COleDataSource::CacheData  
 Вызывайте эту функцию, чтобы указать формат, в котором данные предлагается данных операций передачи.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *cfFormat*  
 Формат буфера обмена, в котором данные является доступным. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *lpStgMedium*  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, содержащую данные в указанном формате.  
  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором данные является доступным. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если это значение NULL, используются значения по умолчанию для других полей в `FORMATETC` структуры.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать данные, так как эта функция предоставляет его с помощью интерпретации отрисовки. Данные кэшируются, пока они не понадобятся.  
  
 Предоставьте данные с помощью [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры. Можно также использовать `CacheGlobalData` настолько мало, будет передаваться эффективно используя HGLOBAL функция-член, если объем данных, вы указали.  
  
 После вызова `CacheData` `ptd` членом `lpFormatEtc` и содержание *lpStgMedium* принадлежат объекту данных, не вызывающим объектом.  
  
 Чтобы использовать отложенной подготовки к просмотру, вызовите [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функция-член. Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структур в пакете Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в пакете Windows SDK.  
  
##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData  
 Вызывайте эту функцию, чтобы указать формат, в котором данные предлагается данных операций передачи.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *cfFormat*  
 Формат буфера обмена, в котором данные является доступным. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *hGlobal*  
 Дескриптор к глобальной памяти блок, содержащий данные в указанном формате.  
  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором данные является доступным. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если это значение NULL, используются значения по умолчанию для других полей в `FORMATETC` структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью интерпретации визуализации, поэтому данные необходимо предоставить при вызове функции; данные кэшируются, пока они не понадобятся. Используйте `CacheData` функция-член, если вы указали большой объем данных или если требуется средний структурированного хранилища.  
  
 Чтобы использовать отложенной подготовки к просмотру, вызовите [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функция-член. Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в пакете Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в пакете Windows SDK.  
  
##  <a name="coledatasource"></a>  COleDataSource::COleDataSource  
 Создает объект `COleDataSource`.  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData  
 Вызывайте эту функцию, чтобы указать формат, в котором данные предлагается данных операций передачи.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *cfFormat*  
 Формат буфера обмена, в котором данные является доступным. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором данные является доступным. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если это значение NULL, используются значения по умолчанию для других полей в `FORMATETC` структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью отложенной обработки, поэтому данные не предоставляются немедленно. [OnRenderData](#onrenderdata) или [OnRenderGlobalData](#onrenderglobaldata) функция-член вызывается для запроса данных.  
  
 Используйте эту функцию, если вы не собираетесь предоставлять данные с помощью `CFile` объекта. Если вы собираетесь предоставить данные через `CFile` , вызовите [DelayRenderFileData](#delayrenderfiledata) функция-член. Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Чтобы использовать немедленное отрисовки, вызовите [CacheData](#cachedata) или [CacheGlobalData](#cacheglobaldata) функция-член.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в пакете Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в пакете Windows SDK.  
  
##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData  
 Вызывайте эту функцию, чтобы указать формат, в котором данные предлагается данных операций передачи.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *cfFormat*  
 Формат буфера обмена, в котором данные является доступным. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором данные является доступным. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если это значение NULL, используются значения по умолчанию для других полей в `FORMATETC` структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью отложенной обработки, поэтому данные не предоставляются немедленно. [OnRenderFileData](#onrenderfiledata) функция-член вызывается для запроса данных.  
  
 Используйте эту функцию, если вы собираетесь использовать `CFile` объект в качестве источника данных. Если вы не собираетесь использовать `CFile` , вызовите [DelayRenderData](#delayrenderdata) функция-член. Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Чтобы использовать немедленное отрисовки, вызовите [CacheData](#cachedata) или [CacheGlobalData](#cacheglobaldata) функция-член.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в пакете Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в пакете Windows SDK.  
  
##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData  
 Вызывайте эту функцию, поддерживающих изменение содержимого источника данных.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *cfFormat*  
 Формат буфера обмена, в котором будет размещаться данные. Этот параметр может принимать одно из стандартных форматов буфера обмена, или значение, возвращенное собственный Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором данные являются заменяемого. Укажите значение для этого параметра, если вы хотите указать дополнительный формат сведений, чем формат буфера обмена, определяемое *cfFormat*. Если это значение NULL, используются значения по умолчанию для других полей в `FORMATETC` структуры.  
  
### <a name="remarks"></a>Примечания  
 [OnSetData](#onsetdata) вызывается платформой, когда это происходит. Это используется, только когда из источника данных, то платформа возвращает [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Если `DelaySetData` не вызывается, ваш `OnSetData` никогда не будет вызвана функция. `DelaySetData` должен вызываться для каждого буфера обмена или `FORMATETC` формата, поддерживаются.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в пакете Windows SDK.  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в пакете Windows SDK.  
  
##  <a name="dodragdrop"></a>  COleDataSource::DoDragDrop  
 Вызовите `DoDragDrop` функцию-член для операции перетаскивания и вставки для этого источника данных, обычно в виде [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) обработчика.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Параметры  
*dwEffects*  
Перетащите-операции, которые разрешены в этом источнике данных. Может иметь одно или несколько из следующих:  
  
 - DROPEFFECT_COPY, операция копирования может быть выполнена.  
      
 - DROPEFFECT_MOVE удалось выполнить операцию перемещения.  
      
 - Может быть установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.  
      
 - DROPEFFECT_SCROLL указывает, что может произойти прокрутки операции перетаскивания.  
  
*lpRectStartDrag*  
Указатель на прямоугольник, который определяет, где фактически начинается перетаскивание. Дополнительные сведения см. в разделе "Примечания".  
  
*pDropSource*  
Указывает источнику перетаскивания. Если значение NULL, затем реализацию по умолчанию [COleDropSource](../../mfc/reference/coledropsource-class.md) будет использоваться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Удаление эффекта, созданный операцией перетаскивания и вставки; в противном случае DROPEFFECT_NONE, если операция никогда не начинается, так как пользователь отпустил кнопку мыши перед выходом из предоставленного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Операции перетаскивания и вставки не начинается немедленно. Он ждет, пока указатель мыши покидает прямоугольник, определяемый *lpRectStartDrag* или пока не прошли указанного числа миллисекунд. Если *lpRectStartDrag* имеет значение NULL, размер прямоугольника равно одному пикселю.  
  
 Время задержки задается параметр раздела реестра. Время задержки можно изменить, вызвав [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если вы не укажете время задержки, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите хранится следующим образом:  
  
-   Перетащите Windows NT задержка времени хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Время задержки перетащите 3.x Windows хранится в WIN. INI-файл, в разделе "[Windows}".  
  
-   Перетащите Windows 95/98 задержка времени хранится в кэшированной версии WIN. INI.  
  
 Для перетащите Дополнительные сведения о том, как задержки сведения хранятся в реестре или. INI-файл, см. в разделе [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) в пакете Windows SDK.  
  
 Дополнительные сведения см. в статье [путем перетаскивания: реализация источника Drop](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="empty"></a>  COleDataSource::Empty  
 Эта функция вызывается для пустой `COleDataSource` объект данных.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Примечания  
 Оба кэшируются и форматов подготовки к просмотру задержки очищаются, поэтому они могут использоваться повторно.  
  
 Дополнительные сведения см. в разделе [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) в пакете Windows SDK.  
  
##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard  
 Выполняет визуализацию данных, который находится в буфере обмена, а затем позволяет вставлять данные из буфера обмена, после завершения работы вашего приложения.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [SetClipboard](#setclipboard) поместить данные в буфер обмена.  
  
##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner  
 Определяет, были изменены ли данные в буфере обмена [SetClipboard](#setclipboard) последнего вызова метода и если да, определяет текущего владельца.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные источника в данный момент в буфере обмена, или значение NULL, если нет ничего в буфере обмена или буфер обмена не является владельцем вызывающего приложения.  
  
##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData  
 Вызывается платформой для извлечения данных в указанном формате.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 *lpStgMedium*  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, в котором они должны быть возвращены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат входит один ранее размещен в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функция-член для отложенной подготовки к просмотру. Реализация по умолчанию эта функция будет вызывать [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData](#onrenderglobaldata) если предоставленный среда хранения представляет собой файл или в памяти, соответственно. Если не указано ни одно из этих форматов, реализация по умолчанию возвращает значение 0 и не выполнять никаких действий. Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Если *lpStgMedium*-> *tymed* является TYMED_NULL, `STGMEDIUM` должен быть выделяется объектом и заполняется в соответствии с *lpFormatEtc "->" tymed*. Если это не TYMED_NULL, `STGMEDIUM` должно быть заполнено на месте с данными.  
  
 Существует расширенная переопределяемый. Переопределите эту функцию для предоставления данных в затребованном формате и средний. В зависимости от данных может потребоваться переопределить один из других версий эта функция вместо этого. Если данные находятся в малых и фиксированный размер, переопределить `OnRenderGlobalData`. Если данные находятся в файле, или имеет переменный размер, переопределить `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) тип перечисления, и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в Windows SDK.  
  
##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData  
 Вызывается платформой для извлечения данных в указанном формате при заданную среду хранения является файлом.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Параметры  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 *pFile*  
 Указывает на [CFile](../../mfc/reference/cfile-class.md) объект, в котором должен быть прорисован данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат входит один ранее размещен в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) функция-член для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает значение FALSE.  
  
 Существует расширенная переопределяемый. Переопределите эту функцию для предоставления данных в затребованном формате и средний. В зависимости от данных может потребоваться переопределить один из других версий эта функция вместо этого. Если вы хотите обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные находятся в файле, или имеет переменный размер, переопределить `OnRenderFileData`. Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в пакете Windows SDK.  
  
##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData  
 Вызывается платформой для извлечения данных в указанном формате, при глобальной памяти, заданную среду хранения.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Параметры  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 *phGlobal*  
 Указывает дескриптор глобальной памяти, в котором они должны быть возвращены. Если один еще не был выделен, этот параметр может иметь значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат входит один ранее размещен в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) функция-член для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает значение FALSE.  
  
 Если *phGlobal* имеет значение NULL, то новый HGLOBAL должен выделить и возвращены в *phGlobal*. В противном случае HGLOBAL определяемое *phGlobal* должно быть заполнено данными. Объем данных, помещаются в HGLOBAL не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен большего размера.  
  
 Существует расширенная переопределяемый. Переопределите эту функцию для предоставления данных в затребованном формате и средний. В зависимости от данных может потребоваться переопределить один из других версий эта функция вместо этого. Если вы хотите обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные находятся в файле, или имеет переменный размер, переопределить [OnRenderFileData](#onrenderfiledata). Дополнительные сведения о отложенной подготовки к просмотру как обработанное в MFC, см. в статье [объекты и источники данных: манипуляции](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в пакете Windows SDK.  
  
##  <a name="onsetdata"></a>  COleDataSource::OnSetData  
 Вызывается платформой для задания или замены данных в `COleDataSource` объекта в указанном формате.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Параметры  
 *lpFormatEtc*  
 Указывает на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором заменяется данных.  
  
 *lpStgMedium*  
 Указывает на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, содержащую данные, который заменяет текущее содержимое `COleDataSource` объекта.  
  
 *bRelease*  
 Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающая сторона решает, кто отвечает за освобождение ресурсов, выделенной среду хранения. Вызывающий объект устанавливается не *bRelease*. Если *bRelease* имеет ненулевое значение, источник данных принимает владение, освободить среду после завершения его использования. Когда *bRelease* равно 0, вызывающий объект сохраняет владение и источника данных можно использовать среду хранения только на протяжении всего вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Источник данных не вступят в владение данных он успешно получил его. То есть он не стать владельцем `OnSetData` возвращает 0. Если источник данных принимает владельца, он освобождает среду хранения, вызвав [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) функции.  
  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для замены данных в указанном формате. Существует расширенная переопределяемый.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структур и [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) функции в пакете Windows SDK.  
  
##  <a name="setclipboard"></a>  COleDataSource::SetClipboard  
 Помещает данные, содержащиеся в `COleDataSource` объект в буфере обмена после вызова одного из следующих функций: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), или [DelayRenderFileData](#delayrenderfiledata).  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDataObject](../../mfc/reference/coledataobject-class.md)
