---
title: Класс COleDocument
ms.date: 11/04/2016
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
ms.openlocfilehash: d1922c2f2d804c2a93d30dc0708b2d3ae037414d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768709"
---
# <a name="coledocument-class"></a>Класс COleDocument

Базовый класс для документов OLE, которые поддерживают визуальное редактирование.

## <a name="syntax"></a>Синтаксис

```
class COleDocument : public CDocument
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|Создает объект `COleDocument`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|Добавляет элемент в список элементов, поддерживаемых в документе.|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Задает печати целевое устройство для всех клиентских элементов в документе.|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Приводит к документам для сохранения в формате структурированного хранения OLE.|
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Возвращает элемент OLE, который является активным в данный момент на месте.|
|[COleDocument::GetNextClientItem](#getnextclientitem)|Получает следующий элемент клиента для выполнения итерации.|
|[COleDocument::GetNextItem](#getnextitem)|Получает следующий элемент документа для выполнения итерации.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|Получает следующий элемент сервера для выполнения итерации.|
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Возвращает основной выбранный элемент OLE в документе.|
|[COleDocument::GetStartPosition](#getstartposition)|Получает начальное положение для начала итерации.|
|[COleDocument::HasBlankItems](#hasblankitems)|Проверяет наличие пустых ячеек в документе.|
|[COleDocument::OnShowViews](#onshowviews)|Вызывается, когда документ становится видимым или невидимым.|
|[COleDocument::RemoveItem](#removeitem)|Удаляет элемент из списка элементов, поддерживаемых в документе.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Помечает его как измененный, если были изменены какие-либо содержащиеся элементы OLE.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Обрабатывает события в команду меню изменить значок.|
|[COleDocument::OnEditConvert](#oneditconvert)|Выполняет преобразование внедренного или связанного объекта из одного типа в другой.|
|[COleDocument::OnEditLinks](#oneditlinks)|Обрабатывает события в команду «ссылки» в меню "Правка".|
|[COleDocument::OnFileSendMail](#onfilesendmail)|Отправляет сообщение электронной почты с вложенным документом.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Вызывается платформой для обновления пользовательского интерфейса команды пункта меню Edit/Смена значка.|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Вызывается платформой для обновления пользовательского интерфейса команды пункта меню Edit/ссылки.|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Вызывается платформой для обновления командный пользовательский Интерфейс для редактирования / *ObjectName* пункт меню и подменю команду организован и для редактирования / *ObjectName*.|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Вызывается платформой для обновления пользовательского интерфейса команды Специальная вставка пункта меню.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Вызывается платформой для обновления пользовательского интерфейса команды для пункта меню вставки.|

## <a name="remarks"></a>Примечания

`COleDocument` является производным от `CDocument`, который позволяет приложениям OLE для использования архитектуры document/view, предоставляемый библиотекой классов Microsoft Foundation.

`COleDocument` обрабатывает документ как коллекция [CDocItem](../../mfc/reference/cdocitem-class.md) объектов для обработки элементов OLE. Контейнер и серверные приложения требуют такой архитектуры, поскольку документы должны иметь возможность содержать элементы OLE. [COleServerItem](../../mfc/reference/coleserveritem-class.md) и [COleClientItem](../../mfc/reference/coleclientitem-class.md) классы, оба являются производными от `CDocItem`, управление взаимодействий между приложениями и элементы OLE.

При создании приложения-контейнера для простого, являются производными от класса документа `COleDocument`. При создании приложения-контейнера, который поддерживает связывание со встроенными элементами, содержащихся в документы, являются производными от класса документа [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). При создании сервера приложения или сочетания контейнера и сервера, являются производными от класса документа [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc` и `COleServerDoc` являются производными от `COleDocument`, поэтому эти классы наследуют все службы, доступные в `COleDocument` и `CDocument`.

Чтобы использовать `COleDocument`, создать класс, производный от него и расширяют его функциональные возможности управления приложения отличных от OLE данных также внедренных или связанных элементов. При определении `CDocItem`-производные классы для хранения данных для собственного приложения, можно использовать реализацию по умолчанию, определяемый `COleDocument` для хранения данных, отличных от OLE и OLE. Можно также создать свои собственные структуры данных для хранения данных отличных от OLE отдельно от элементов OLE. Дополнительные сведения см. в статье [контейнеров: Составные файлы](../../mfc/containers-compound-files.md)...

`CDocument` Поддержка отправки документа по почте, если имеется поддержка электронной почты (MAPI). `COleDocument` был обновлен [OnFileSendMail](#onfilesendmail) для правильной обработки составных документов. Дополнительные сведения см. в статьях [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md)...

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="additem"></a>  COleDocument::AddItem

Вызывайте эту функцию, чтобы добавить элемент к документу.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа.

### <a name="remarks"></a>Примечания

Необходимо явным образом вызвать эту функцию, когда он вызывается методом `COleClientItem` или `COleServerItem` конструктор, который принимает указатель на документ.

##  <a name="applyprintdevice"></a>  COleDocument::ApplyPrintDevice

Вызывайте эту функцию, чтобы изменить печати целевое устройство для всех внедренных [COleClientItem](../../mfc/reference/coleclientitem-class.md) элементов в документе-контейнере приложения.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Параметры

*ptd*<br/>
Указатель на `DVTARGETDEVICE` структуры данных, который содержит сведения о новых печати целевого устройства. Может иметь значение NULL.

*PPD*<br/>
Указатель на `PRINTDLG` структуры данных, который содержит сведения о новых печати целевого устройства. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обновляет печати целевое устройство для всех элементов, но не обновляет кэш презентации для этих элементов. Чтобы обновить кэш представления для элемента, вызовите [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).

Аргументы для этой функции содержат сведения, использует OLE для идентификации целевого устройства. [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) структура содержит сведения, которые Windows использует для инициализации общее диалоговое окно печати. После пользователь закрывает диалоговое окно, Windows возвращает сведения о выбранных элементов для пользователя в этой структуре. `m_pd` Членом [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объект `PRINTDLG` структуры.

Дополнительные сведения см. в разделе [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) структуры в пакете Windows SDK.

Дополнительные сведения см. в разделе [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) структуры в пакете Windows SDK.

##  <a name="coledocument"></a>  COleDocument::COleDocument

Создает объект `COleDocument`.

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>  COleDocument::EnableCompoundFile

Эта функция вызывается в том случае, если вы хотите сохранить документ, используя формат составного файла.

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, включена ли поддержка составной файл.

### <a name="remarks"></a>Примечания

Это также называется структурированным хранилищем. Обычно эта функция вызывается из конструктора вашей `COleDocument`-производного класса. Дополнительные сведения о составных документов см. в статье [контейнеров: Составные файлы](../../mfc/containers-compound-files.md)...

Если вы не вызываете эту функцию-член, документы будут храниться в виде неструктурированный файл («плоский»).

После поддержки составной файл включен или отключен для документа, этот параметр не должны изменяться во время существования документа.

##  <a name="getinplaceactiveitem"></a>  COleDocument::GetInPlaceActiveItem

Вызов, эту функцию для получения OLE элемент, который в настоящее время активации на месте в фрейм окна, содержащего представление, идентифицируемый *pWnd*.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, где отображается документе-контейнере.

### <a name="return-value"></a>Возвращаемое значение

Указатель на одном месте, в active объекта OLE; Значение NULL, если нет элемента OLE в настоящее время в состоянии «на месте активен».

##  <a name="getnextclientitem"></a>  COleDocument::GetNextClientItem

Вызывайте эту функцию несколько раз, чтобы получать доступ к каждому клиентских элементов в документе.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Ссылка на место задано значение предыдущим вызовом к `GetNextClientItem`; возвращается начальное значение `GetStartPosition` функция-член.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий клиент элемента в документе, или значение NULL, если больше нет элементов клиента.

### <a name="remarks"></a>Примечания

После каждого вызова, а значение *pos* имеет значение для следующего элемента в документ, который может или не может являться элементом клиента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>  COleDocument::GetNextItem

Вызывайте эту функцию несколько раз, чтобы получать доступ к каждому из элементов в документе.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Ссылка на место задано значение предыдущим вызовом к `GetNextItem`; возвращается начальное значение `GetStartPosition` функция-член.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент документа в указанной позиции.

### <a name="remarks"></a>Примечания

После каждого вызова, а значение *pos* присваивается значение положение следующего элемента в документе. Если полученного элемента является последним элементом в документе, новое значение *pos* имеет значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>  COleDocument::GetNextServerItem

Вызывайте эту функцию несколько раз, чтобы получать доступ к каждому элементов сервера в документе.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Ссылка на место задано значение предыдущим вызовом к `GetNextServerItem`; возвращается начальное значение `GetStartPosition` функция-член.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий сервер элементов в документе, или значение NULL, если больше нет элементов сервера.

### <a name="remarks"></a>Примечания

После каждого вызова, а значение *pos* имеет значение для следующего элемента в документе, который может или не может быть серверным элементом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>  COleDocument::GetPrimarySelectedItem

Вызывается платформой для извлечения текущего выбранного элемента OLE в указанном представлении.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указатель на объект активное представление, отображение документа.

### <a name="return-value"></a>Возвращаемое значение

Указатель на один выбранный элемент OLE; Значение NULL, если элементы OLE не выбраны или если более чем один выбран.

### <a name="remarks"></a>Примечания

Реализация по умолчанию выполняет поиск в списке автономной OLE элементов для одного выбранного элемента и возвращает указатель на него. Если отсутствует элемент выбран, или имеется более одного элемента, выбранного, функция возвращает значение NULL. Необходимо переопределить `CView::IsSelected` функции-члена в классе представления, для этой функции для работы. Переопределите эту функцию, если у вас есть собственный метод хранения вложенных элементов OLE.

##  <a name="getstartposition"></a>  COleDocument::GetStartPosition

Вызывайте эту функцию, чтобы получить позицию первого элемента в документе.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для начала прохода элементов документа; Имеет значение NULL, если документ не содержит элементов.

### <a name="remarks"></a>Примечания

Передайте значение, возвращаемое `GetNextItem`, `GetNextClientItem`, или `GetNextServerItem`.

##  <a name="hasblankitems"></a>  COleDocument::HasBlankItems

Вызывайте эту функцию для определения, содержит ли документ все пустые элементы.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ содержит пустые элементы; в противном случае 0.

### <a name="remarks"></a>Примечания

Пустой элемент является одним которого прямоугольник пуст.

##  <a name="oneditchangeicon"></a>  COleDocument::OnEditChangeIcon

Отображение диалогового окна OLE Смена значка и изменяет значок, представляющий текущий выбранный элемент OLE на значок, выбранного пользователем в диалоговом окне.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Примечания

`OnEditChangeIcon` Создает и запускает `COleChangeIconDialog` Смена значка диалоговое окно.

##  <a name="oneditconvert"></a>  COleDocument::OnEditConvert

Отображает диалоговое окно преобразования OLE и преобразует или активирует текущего выбранного объекта OLE в соответствии с выбора пользователя в диалоговом окне.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Примечания

`OnEditConvert` Создает и запускает `COleConvertDialog` диалоговое окно «Convert».

Пример преобразования преобразует документ Microsoft Word в документ WordPad.

##  <a name="oneditlinks"></a>  COleDocument::OnEditLinks

Отображает диалоговое окно Edit/каналов OLE.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Примечания

`OnEditLinks` Создает и запускает `COleLinksDialog` ссылки диалоговое окно, которое позволяет пользователю изменять связанные объекты.

##  <a name="onfilesendmail"></a>  COleDocument::OnFileSendMail

Отправляет сообщение через обслуживания резидентного почты (если таковые имеются) в документе как вложение.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Примечания

`OnFileSendMail` вызовы `OnSaveDocument` для сериализации (без названия и измененных документов во временный файл, который затем отправляется по электронной почте Сохранить). Если документ не был изменен, временный файл не требуется. отправляется исходный. `OnFileSendMail` Загружает MAPI32. Библиотека DLL, если он еще не загружена.

В отличие от реализации `OnFileSendMail` для `CDocument`, эта функция правильно обрабатывает составные файлы.

Дополнительные сведения см. в разделе [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md) статьи...

##  <a name="onshowviews"></a>  COleDocument::OnShowViews

Платформа вызывает эту функцию после документа видимости изменений состояния.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Параметры

*bVisible*<br/>
Указывает, является ли документ становится видимым или невидимым.

### <a name="remarks"></a>Примечания

По умолчанию версия этой функции не выполняет никаких действий. Его необходимо переопределите в том случае, если какой-либо специальные обработки при изменении видимости документа должно выполнять приложение.

##  <a name="onupdateeditchangeicon"></a>  COleDocument::OnUpdateEditChangeIcon

Вызывается платформой для обновления команда Смена значка в меню "Правка".

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызовы обработчика обновления `Enable` функцию-член `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

`OnUpdateEditChangeIcon` обновляет команды пользовательского интерфейса в зависимости от того, является ли допустимым значком существует в документе. Переопределите эту функцию, чтобы изменить поведение.

##  <a name="onupdateeditlinksmenu"></a>  COleDocument::OnUpdateEditLinksMenu

Вызывается платформой для обновления команду «ссылки» в меню "Правка".

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызовы обработчика обновления `Enable` функцию-член `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

Начиная с первого элемента OLE в документе, `OnUpdateEditLinksMenu` обращается к каждого элемента, проверяет, является ли элемент является ссылкой и если это ссылка, включает команды связи. Переопределите эту функцию, чтобы изменить поведение.

##  <a name="onupdateobjectverbmenu"></a>  COleDocument::OnUpdateObjectVerbMenu

Вызывается платформой для обновления *ObjectName* команды меню "Правка" и команда подменю, получить доступ из *ObjectName* команду, где *ObjectName* имя OLE-объекта, внедренные в документ.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызовы обработчика обновления `Enable` функцию-член `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

`OnUpdateObjectVerbMenu` обновления *ObjectName* команды пользовательского интерфейса в зависимости от того, является ли допустимый объект существует в документе. Если объект существует, *ObjectName* включена команда в меню "Правка". При выборе этого пункта меню отображается в подменю команду. В подменю команду содержит всех команд, доступных для объекта, например изменить, свойства и т. д. Переопределите эту функцию, чтобы изменить поведение.

##  <a name="onupdatepastelinkmenu"></a>  COleDocument::OnUpdatePasteLinkMenu

Вызывается платформой для определения, является ли связанный элемент OLE можно вставить из буфера обмена.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызовы обработчика обновления `Enable` функцию-член `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

Специальная команда меню включена или отключена в зависимости от того, является ли элемент, можно вставить в документ или нет.

##  <a name="onupdatepastemenu"></a>  COleDocument::OnUpdatePasteMenu

Вызывается платформой для определения того, можно ли вставить из буфера обмена встроенного элемента OLE.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызовы обработчика обновления `Enable` функцию-член `CCmdUI` структуры через *pCmdUI* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Примечания

Вставьте команду меню и кнопки включены или отключены в зависимости от того, является ли элемент, можно вставить в документ или нет.

##  <a name="removeitem"></a>  COleDocument::RemoveItem

Вызывайте эту функцию, чтобы удалить элемент из документа.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на элемент документа, который необходимо удалить.

### <a name="remarks"></a>Примечания

Обычно не нужно вызвать эту функцию, явным образом; его вызывает деструкторы для `COleClientItem` и `COleServerItem`.

##  <a name="updatemodifiedflag"></a>  COleDocument::UpdateModifiedFlag

Вызывайте эту функцию, чтобы пометить документ как измененный, если были изменены какие-либо содержащиеся элементы OLE.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Примечания

Благодаря этому платформа для запроса пользователя, чтобы сохранить документ перед закрытием, даже если не был изменен собственных данных в документе.

## <a name="see-also"></a>См. также

[Пример MFC КОНТЕЙНЕРА](../../overview/visual-cpp-samples.md)<br/>
[Пример MFC MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
