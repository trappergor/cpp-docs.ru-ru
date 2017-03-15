---
title: "Класс COleDataSource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDataSource
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject, MFC encapsulation
- data transfer [C++], OLE
- COleDataSource class
- OLE data transfer [C++]
- uniform data transfer, OLE
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd8f30c3edd7d26b254e7f4a6f153ab0b2fc96da
ms.lasthandoff: 02/24/2017

---
# <a name="coledatasource-class"></a>COleDataSource-класс
Играет роль кэша, в который приложение помещает данные, которые оно будет предлагать во время операций передачи данных, таких как операции с буфером обмена или операции перетаскивания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|Создает объект `COleDataSource`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDataSource::CacheData](#cachedata)|Предоставляет данные в указанном формате с помощью **STGMEDIUM** структуры.|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|Предоставляет данные в указанном формате с помощью `HGLOBAL`.|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|Предоставляет данные в указанном формате, с помощью отложенной подготовки к просмотру.|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|Предоставляет данные в указанном формате в `CFile` указателя.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Вызывается для каждого формата, который поддерживается в `OnSetData`.|  
|[COleDataSource::DoDragDrop](#dodragdrop)|Выполняет операции и перетащите с источником данных.|  
|[COleDataSource::Empty](#empty)|Очищает `COleDataSource` объект данных.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Отображает все данные в буфер обмена.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Проверяет, что данные, помещенные в буфер обмена по-прежнему.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Извлекает данные как часть отложенной подготовки к просмотру.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Получает данные в `CFile` в рамках отложенной подготовки к просмотру.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Получает данные в `HGLOBAL` в рамках отложенной подготовки к просмотру.|  
|[COleDataSource::OnSetData](#onsetdata)|Вызывается для замены данных в `COleDataSource` объекта.|  
|[COleDataSource::SetClipboard](#setclipboard)|Окружение `COleDataSource` объекта в буфер обмена.|  
  
## <a name="remarks"></a>Примечания  
 Можно создавать источники данных OLE напрямую. Кроме того [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [производного от COleServerItem](../../mfc/reference/coleserveritem-class.md) классы создавать источники данных OLE в ответ на их `CopyToClipboard` и `DoDragDrop` функции-члены. В разделе [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) краткое описание. Переопределение `OnGetClipboardData` созданные функции-члена класса клиентского элемента или сервера элемента будут добавляться дополнительные форматы буфера обмена данные в источнике данных OLE для `CopyToClipboard` или `DoDragDrop` функции-члена.  
  
 Каждый раз, когда требуется подготовить для передачи данных, необходимо создать объект этого класса и заполнить его данные с помощью наиболее подходящий метод для ваших данных. Способ вставки в источник данных непосредственно зависит от ли немедленно передать данные (немедленного визуализации) или по требованию (отложенная отрисовка). Для каждого формат буфера обмена, в котором данные предоставляются путем передачи формат буфера обмена для использования (необязательный [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры), вызовите [DelayRenderData](#delayrenderdata).  
  
 Дополнительные сведения об источниках данных и передачи данных см. в статье [объектов данных и источников данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Кроме того, статьи [разделы буфер обмена](../../mfc/clipboard.md) Описание механизма буфера обмена OLE.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-namecachedataa--coledatasourcecachedata"></a><a name="cachedata"></a>COleDataSource::CacheData  
 Эта функция позволяет задать формат, в котором данные предлагается данных операций передачи.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpStgMedium`  
 Указывает [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структура, содержащая данные в указанный формат.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) описания формата, в котором будет предлагаться данные структуры. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать данные, поскольку эта функция обеспечивает его с помощью интерпретации подготовки к просмотру. Данные кэшируются, пока не требуется.  
  
 Введите данные с помощью [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры. Можно также использовать `CacheGlobalData` функция-член, если объем данных, указав достаточно мал, чтобы передать эффективно использует `HGLOBAL`.  
  
 После вызова `CacheData` **ptd** членом `lpFormatEtc` и содержимое `lpStgMedium` принадлежат объекту данных, не вызывающим объектом.  
  
 Использование отложенной подготовки к просмотру, вызовите [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функции-члена. Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecacheglobaldataa--coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>COleDataSource::CacheGlobalData  
 Эта функция позволяет задать формат, в котором данные предлагается данных операций передачи.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 *hGlobal*  
 Дескриптор блока глобальной памяти, содержащего данные в указанный формат.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) описания формата, в котором будет предлагаться данные структуры. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью немедленно модуль подготовки отчетов, поэтому данные необходимо предоставить при вызове функции; данные кэшируются, пока не требуется. Используйте `CacheData` функции-члена Если указываются большой объем данных или если требуется средний структурированного хранилища.  
  
 Использование отложенной подготовки к просмотру, вызовите [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функции-члена. Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecoledatasourcea--coledatasourcecoledatasource"></a><a name="coledatasource"></a>COleDataSource::COleDataSource  
 Создает объект `COleDataSource`.  
  
```  
COleDataSource();
```  
  
##  <a name="a-namedelayrenderdataa--coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>COleDataSource::DelayRenderData  
 Эта функция позволяет задать формат, в котором данные предлагается данных операций передачи.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) описания формата, в котором будет предлагаться данные структуры. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью отложенной подготовки к просмотру, поэтому данные не предоставляются непосредственно. [OnRenderData](#onrenderdata) или [OnRenderGlobalData](#onrenderglobaldata) функция-член вызывается для запроса данных.  
  
 Используйте эту функцию, если вы не собираетесь предоставить данные с помощью `CFile` объекта. Если необходимо передать данные через `CFile` , вызовите [DelayRenderFileData](#delayrenderfiledata) функции-члена. Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Чтобы использовать немедленное отрисовки, вызовите [CacheData](#cachedata) или [CacheGlobalData](#cacheglobaldata) функции-члена.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedelayrenderfiledataa--coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>COleDataSource::DelayRenderFileData  
 Эта функция позволяет задать формат, в котором данные предлагается данных операций передачи.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет предлагаться данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) описания формата, в котором будет предлагаться данные структуры. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляет данные с помощью отложенной подготовки к просмотру, поэтому данные не предоставляются непосредственно. [OnRenderFileData](#onrenderfiledata) функция-член вызывается для запроса данных.  
  
 Используйте эту функцию, если вы собираетесь использовать `CFile` объект в качестве источника данных. Если вы не собираетесь использовать `CFile` , вызовите [DelayRenderData](#delayrenderdata) функции-члена. Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Чтобы использовать немедленное отрисовки, вызовите [CacheData](#cachedata) или [CacheGlobalData](#cacheglobaldata) функции-члена.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedelaysetdataa--coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>COleDataSource::DelaySetData  
 Эта функция поддерживает изменение содержимого источника данных.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cfFormat`  
 Формат буфера обмена, в котором будет размещаться данные. Этот параметр может иметь один из стандартных форматов буфера обмена или значение, возвращенное собственного Windows [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) функции.  
  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, описывающие формат, в котором для замены данных. Укажите значение для этого параметра, если требуется указать дополнительный формат сведений, чем буфер обмена формата, заданного в `cfFormat`. Если это **NULL**, используются значения по умолчанию для других полей в **FORMATETC** структуры.  
  
### <a name="remarks"></a>Примечания  
 [OnSetData](#onsetdata) вызывается платформой, в этом случае. Это используется, только когда платформа возвращает источника данных из [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Если `DelaySetData` не вызывается, ваш `OnSetData` никогда не будет вызвана функция. `DelaySetData`должен вызываться для каждого буфера обмена или **FORMATETC** требуется поддержка формата.  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Дополнительные сведения см. в разделе [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedodragdropa--coledatasourcedodragdrop"></a><a name="dodragdrop"></a>COleDataSource::DoDragDrop  
 Вызов `DoDragDrop` функции-члена для выполнения операции и перетащите для этого источника данных, обычно в [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) обработчика.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwEffects`  
 И перетащите операции, разрешенные для этого источника данных. Может иметь одно или несколько из следующих:  
  
- `DROPEFFECT_COPY`Операция копирования может быть выполнена.  
  
- `DROPEFFECT_MOVE`Операция перемещения может быть выполнена.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными может быть установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что может произойти прокрутки операции перетаскивания.  
  
 `lpRectStartDrag`  
 Указатель на прямоугольник, определяющий, где фактически начинает перетаскивание. Дополнительные сведения см. в разделе "Примечания".  
  
 *pDropSource*  
 Указывает источник перетаскивания. Если **NULL** затем стандартную реализацию [COleDropSource](../../mfc/reference/coledropsource-class.md) будет использоваться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Удалить эффект, созданный операцией и перетаскивания; в противном случае `DROPEFFECT_NONE` Если операция никогда не начинается, поскольку пользователь отпустил кнопку мыши перед выходом из предоставленного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Операции и перетащите начать немедленно. Он ждет, пока указатель мыши выходит за пределы прямоугольника, определяемого `lpRectStartDrag` или пока не прошли указанного числа миллисекунд. Если `lpRectStartDrag` — **NULL**, размер прямоугольника равно одному пикселю.  
  
 Время задержки задается параметр раздела реестра. Время задержки можно изменить с помощью [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если время задержки не указан, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите сохраняются следующим образом:  
  
-   Время задержки Windows NT перетащите хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.  
  
-   Время задержки Windows 3.x перетащите хранится в WIN. INI-файл, в разделе [Windows}.  
  
-   Время задержки Windows 95/98 перетащите хранится в кэшированную версию WIN. INI.  
  
 Для перетащите Дополнительные сведения о том, как задержка сведения хранятся в реестре или. INI-файл, в разделе [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в статье [перетаскивание: реализация источника Drop](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="a-nameemptya--coledatasourceempty"></a><a name="empty"></a>COleDataSource::Empty  
 Эта функция вызывается для пустой `COleDataSource` объект данных.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Примечания  
 Оба кэшируются и форматов подготовки к просмотру задержки очищаются, поэтому они могут использоваться повторно.  
  
 Дополнительные сведения см. в разделе [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameflushclipboarda--coledatasourceflushclipboard"></a><a name="flushclipboard"></a>COleDataSource::FlushClipboard  
 Готовится к просмотру данных в буфере обмена, а затем позволяет вставлять данные из буфера обмена после завершения работы вашего приложения.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [SetClipboard](#setclipboard) для помещения данных в буфер обмена.  
  
##  <a name="a-namegetclipboardownera--coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>COleDataSource::GetClipboardOwner  
 Определяет, является ли данные в буфере обмена была изменена с момента [SetClipboard](#setclipboard) последнего вызова и если да, определяет текущий владелец.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Источник данных, в данный момент в буфере обмена или **NULL** Если нет ничего в буфер обмена или буфер обмена не является владельцем вызывающего приложения.  
  
##  <a name="a-nameonrenderdataa--coledatasourceonrenderdata"></a><a name="onrenderdata"></a>COleDataSource::OnRenderData  
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
 Указанный формат, помещенный в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция будет вызывать [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData](#onrenderglobaldata) Если указанный носитель файла или памяти, соответственно. Если не указано ни одно из этих форматов, реализация по умолчанию возвращает значение 0 и не выполняют никаких действий. Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Если `lpStgMedium` ->  *tymed* — **TYMED_NULL**, **STGMEDIUM** следует выделить и заполняются в соответствии с *lpFormatEtc-> tymed*. Если это не **TYMED_NULL**, **STGMEDIUM** должно быть заполнено месте с данными.  
  
 Существует расширенная переопределяемыми. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если данные фиксированного размера и небольшой, переопределите `OnRenderGlobalData`. Если данные в файле или имеет переменный размер, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры, [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) тип перечисления, и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-nameonrenderfiledataa--coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>COleDataSource::OnRenderFileData  
 Вызывается платформой для получения данных в указанном формате, если указанный носитель является файл.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `pFile`  
 Указывает [CFile](../../mfc/reference/cfile-class.md) объект, в котором для визуализации данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Существует расширенная переопределяемыми. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если вы хотите обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные в файле или имеет переменный размер, переопределите `OnRenderFileData`. Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-nameonrenderglobaldataa--coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleDataSource::OnRenderGlobalData  
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
 Указывает дескриптор глобальной памяти, в котором не возвращаются данные. Если один еще не выделен, этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в `COleDataSource` с помощью [DelayRenderData](#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Если `phGlobal` — **NULL**, затем новый `HGLOBAL` следует выделить и возвращается в `phGlobal`. В противном случае — `HGLOBAL` определяется `phGlobal` должен быть заполнен данными. Объем данных, помещаются в `HGLOBAL` не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен до большего размера.  
  
 Существует расширенная переопределяемыми. Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если вы хотите обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные в файле или является переменного размера, переопределить [OnRenderFileData](#onrenderfiledata). Дополнительные сведения об отложенной подготовки к просмотру как обработанные MFC, см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-nameonsetdataa--coledatasourceonsetdata"></a><a name="onsetdata"></a>COleDataSource::OnSetData  
 Вызывается платформой для установки или замены данных в `COleDataSource` объекта в указанном формате.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат замены данных.  
  
 `lpStgMedium`  
 Указывает [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуру, содержащую данные, который заменяет текущее содержимое `COleDataSource` объекта.  
  
 `bRelease`  
 Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающая сторона определяет, кто несет ответственность за освобождение ресурсов, выделенной среду хранения. Вызывающий объект устанавливается не `bRelease`. Если `bRelease` имеет ненулевое значение, источник данных становится владельцем, освобождение носителя после завершения его использования. Когда `bRelease` равно 0, вызывающий объект сохраняет владение и источника данных можно использовать среду хранения только в течение всего вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Источника данных не распоряжаться данных пока он успешно получил его. То есть, он не стать владельцем, если `OnSetData` возвращает 0. Если источник данных становится владельцем, он освобождает среду хранения путем вызова [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) функции.  
  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для замены данных в указанном формате. Существует расширенная переопределяемыми.  
  
 Дополнительные сведения см. в разделе [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры и [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) и [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) функции в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
##  <a name="a-namesetclipboarda--coledatasourcesetclipboard"></a><a name="setclipboard"></a>COleDataSource::SetClipboard  
 Помещает данные, содержащиеся в `COleDataSource` объектов в буфере обмена после вызова одного из следующих функций: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), или [DelayRenderFileData](#delayrenderfiledata).  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDataObject](../../mfc/reference/coledataobject-class.md)

