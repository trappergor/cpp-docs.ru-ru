---
title: Класс Коледокумент
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
ms.openlocfilehash: b92c796fdaa972966dcbfa85b1e34f267b6c629c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426495"
---
# <a name="coledocument-class"></a>Класс Коледокумент

Базовый класс для документов OLE, которые поддерживают визуальное редактирование.

## <a name="syntax"></a>Синтаксис

```
class COleDocument : public CDocument
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Коледокумент:: Коледокумент](#coledocument)|Формирует объект `COleDocument`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Коледокумент:: AddItem](#additem)|Добавляет элемент в список элементов, поддерживаемых документом.|
|[Коледокумент:: Апплипринтдевице](#applyprintdevice)|Задает целевое устройство печати для всех клиентских элементов в документе.|
|[Коледокумент:: Енаблекомпаундфиле](#enablecompoundfile)|Приводит к сохранению документов с использованием формата структурированного файла хранилища OLE.|
|[Коледокумент:: Жетинплацеактивеитем](#getinplaceactiveitem)|Возвращает элемент OLE, который в данный момент находится в активном месте.|
|[Коледокумент:: Жетнекстклиентитем](#getnextclientitem)|Возвращает следующий клиентский элемент для итерации.|
|[Коледокумент:: Жетнекститем](#getnextitem)|Возвращает следующий элемент документа для итерации.|
|[Коледокумент:: Жетнекстсерверитем](#getnextserveritem)|Возвращает следующий серверный элемент для итерации.|
|[Коледокумент:: Жетпримариселектедитем](#getprimaryselecteditem)|Возвращает основной выбранный элемент OLE в документе.|
|[Коледокумент:: Жетстартпоситион](#getstartposition)|Возвращает начальную точку для начала итерации.|
|[Коледокумент:: Хасбланкитемс](#hasblankitems)|Проверяет наличие пустых элементов в документе.|
|[Коледокумент:: Оншоввиевс](#onshowviews)|Вызывается, когда документ станет видимым или невидимым.|
|[Коледокумент:: RemoveItem](#removeitem)|Удаляет элемент из списка элементов, поддерживаемых документом.|
|[Коледокумент:: Упдатемодифиедфлаг](#updatemodifiedflag)|Помечает документ как измененный, если любой из содержащихся в нем элементов OLE был изменен.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[Коледокумент:: Онедитчанжеикон](#oneditchangeicon)|Обрабатывает события в команде меню "изменить значок".|
|[Коледокумент:: Онедитконверт](#oneditconvert)|Обрабатывает преобразование внедренного или связанного объекта из одного типа в другой.|
|[Коледокумент:: Онедитлинкс](#oneditlinks)|Обрабатывает события в команде ссылки в меню Правка.|
|[Коледокумент:: Онфилесендмаил](#onfilesendmail)|Отправляет почтовое сообщение с прикрепленным документом.|
|[Коледокумент:: Онупдатидитчанжеикон](#onupdateeditchangeicon)|Вызывается платформой для обновления пользовательского интерфейса команды меню "изменить/изменить значок".|
|[Коледокумент:: Онупдатидитлинксмену](#onupdateeditlinksmenu)|Вызывается платформой для обновления пользовательского интерфейса команды меню "изменить/связать".|
|[Коледокумент:: Онупдатеобжектвербмену](#onupdateobjectverbmenu)|Вызывается платформой для обновления пользовательского интерфейса команды меню "изменить/ *ИмяОбъекта* " и доступного к меню "команда" из Edit/ *objectname*.|
|[Коледокумент:: Онупдатепастелинкмену](#onupdatepastelinkmenu)|Вызывается платформой для обновления пользовательского интерфейса команды меню "Специальная вставка".|
|[Коледокумент:: Онупдатепастемену](#onupdatepastemenu)|Вызывается платформой для обновления пользовательского интерфейса команды меню "вставить".|

## <a name="remarks"></a>Remarks

`COleDocument` является производным от `CDocument`, который позволяет приложениям OLE использовать архитектуру документов и представлений, предоставляемую библиотека Microsoft Foundation Class.

`COleDocument` обрабатывает документ как коллекцию объектов [кдоЦитем](../../mfc/reference/cdocitem-class.md) для обработки элементов OLE. Как для контейнеров, так и для серверных приложений требуется такая архитектура, поскольку их документы должны иметь возможность содержать элементы OLE. Классы [COleServerItem](../../mfc/reference/coleserveritem-class.md) и [COleClientItem](../../mfc/reference/coleclientitem-class.md) , которые являются производными от `CDocItem`, управляют взаимодействием между приложениями и элементами OLE.

Если вы создаете простое приложение-контейнер, создайте производный класс документа от `COleDocument`. Если вы создаете приложение-контейнер, которое поддерживает связывание с внедренными элементами, содержащимися в его документах, производятся наследование класса документа от [колелинкингдок](../../mfc/reference/colelinkingdoc-class.md). Если вы создаете серверное приложение или сочетание контейнера или сервера, создайте производный класс документа от [колесервердок](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc` и `COleServerDoc` являются производными от `COleDocument`, поэтому эти классы наследуют все службы, доступные в `COleDocument` и `CDocument`.

Чтобы использовать `COleDocument`, создайте производный от него класс и добавьте функции для управления данными, отличными от OLE, а также внедренными или связанными элементами приложения. При определении классов, производных от `CDocItem`, для хранения собственных данных приложения можно использовать реализацию по умолчанию, определенную `COleDocument` для хранения данных OLE и не OLE. Вы также можете проектировать собственные структуры данных для хранения данных, отличных от OLE, отдельно от элементов OLE. Дополнительные сведения см. в разделе [контейнеры статьи: составные файлы](../../mfc/containers-compound-files.md).

`CDocument` поддерживает отправку документа по электронной почте, если имеется поддержка почты (MAPI). `COleDocument` обновил [онфилесендмаил](#onfilesendmail) для правильной работы с составными документами. Дополнительные сведения см. в статьях поддержка [MAPI](../../mfc/mapi.md) и [MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="additem"></a>Коледокумент:: AddItem

Вызовите эту функцию, чтобы добавить элемент в документ.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указатель на добавляемый элемент документа.

### <a name="remarks"></a>Remarks

Вам не нужно вызывать эту функцию явно, если она вызывается конструктором `COleClientItem` или `COleServerItem`, который принимает указатель на документ.

##  <a name="applyprintdevice"></a>Коледокумент:: Апплипринтдевице

Вызовите эту функцию, чтобы изменить целевое устройство печати для всех внедренных элементов [COleClientItem](../../mfc/reference/coleclientitem-class.md) в документе контейнера приложения.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Параметры

*ptd*<br/>
Указатель на `DVTARGETDEVICE` структуру данных, которая содержит сведения о новом устройстве печати. Может иметь значение NULL.

*PPD*<br/>
Указатель на `PRINTDLG` структуру данных, которая содержит сведения о новом устройстве печати. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция обновляет целевое устройство печати для всех элементов, но не обновляет кэш презентации для этих элементов. Чтобы обновить кэш презентации для элемента, вызовите [COleClientItem:: упдателинк](../../mfc/reference/coleclientitem-class.md#updatelink).

Аргументы этой функции содержат сведения, используемые OLE для определения целевого устройства. Структура [принтдлг](/windows/win32/api/commdlg/ns-commdlg-printdlga) содержит сведения, используемые Windows для инициализации стандартного диалогового окна печати. Когда пользователь закрывает диалоговое окно, Windows возвращает сведения о выборе пользователя в этой структуре. Элемент `m_pd` объекта [кпринтдиалог](../../mfc/reference/cprintdialog-class.md) является структурой `PRINTDLG`.

Дополнительные сведения см. в описании структуры [принтдлг](/windows/win32/api/commdlg/ns-commdlg-printdlga) в Windows SDK.

Дополнительные сведения см. в описании структуры [двтаржетдевице](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) в Windows SDK.

##  <a name="coledocument"></a>Коледокумент:: Коледокумент

Формирует объект `COleDocument`.

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>Коледокумент:: Енаблекомпаундфиле

Вызывайте эту функцию, если требуется сохранить документ в формате составного файла.

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, включена или отключена поддержка составных файлов.

### <a name="remarks"></a>Remarks

Это также называется структурированным хранилищем. Обычно эта функция вызывается из конструктора класса, производного от `COleDocument`. Дополнительные сведения о составных документах см. в разделе [контейнеры статей: составные файлы](../../mfc/containers-compound-files.md).

Если не вызвать эту функцию-член, документы будут храниться в неструктурированном ("неструктурированном") формате файла.

После включения или отключения поддержки составных файлов для документа этот параметр не должен изменяться в течение времени существования документа.

##  <a name="getinplaceactiveitem"></a>Коледокумент:: Жетинплацеактивеитем

Вызовите эту функцию, чтобы получить элемент OLE, который в настоящее время активирован в окне фрейма, содержащего представление, определяемое *приводится*.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, в котором отображается документ контейнера.

### <a name="return-value"></a>Возвращаемое значение

Указатель на единичный активный элемент OLE на месте; Значение NULL, если в настоящее время нет объекта OLE в состоянии "на месте".

##  <a name="getnextclientitem"></a>Коледокумент:: Жетнекстклиентитем

Вызывайте эту функцию несколько раз для доступа к каждому из клиентских элементов в документе.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение координаты, заданное предыдущим вызовом `GetNextClientItem`; начальное значение возвращается функцией-членом `GetStartPosition`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий клиентский элемент в документе или значение NULL, если больше нет элементов клиента.

### <a name="remarks"></a>Remarks

После каждого вызова значение *POS* задается для следующего элемента в документе, который может быть или не быть клиентским элементом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>Коледокумент:: Жетнекститем

Вызывайте эту функцию несколько раз для доступа к каждому элементу в документе.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение координаты, заданное предыдущим вызовом `GetNextItem`; начальное значение возвращается функцией-членом `GetStartPosition`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент документа в указанной позиции.

### <a name="remarks"></a>Remarks

После каждого вызова значение *POS* устанавливается равным значению позиции следующего элемента в документе. Если извлеченный элемент является последним элементом в документе, новое значение *POS* равно null.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>Коледокумент:: Жетнекстсерверитем

Вызывайте эту функцию несколько раз, чтобы получить доступ к каждому элементу сервера в документе.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение координаты, заданное предыдущим вызовом `GetNextServerItem`; начальное значение возвращается функцией-членом `GetStartPosition`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий серверный элемент в документе или значение NULL, если больше нет элементов сервера.

### <a name="remarks"></a>Remarks

После каждого вызова значение *POS* задается для следующего элемента в документе, который может или не быть элементом сервера.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>Коледокумент:: Жетпримариселектедитем

Вызвано структурой для получения выбранного в данный момент элемента OLE в указанном представлении.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указатель на объект активного представления, в котором отображается документ.

### <a name="return-value"></a>Возвращаемое значение

Указатель на единичный выбранный элемент OLE; Значение NULL, если не выбран ни один элемент OLE или если выбрано несколько элементов.

### <a name="remarks"></a>Remarks

Реализация по умолчанию выполняет поиск в списке содержащихся элементов OLE для одного выбранного элемента и возвращает указатель на него. Если элемент не выбран или выбрано более одного элемента, функция возвращает значение NULL. Чтобы эта функция работала, необходимо переопределить функцию члена `CView::IsSelected` в классе представления. Переопределите эту функцию, если у вас есть собственный метод хранения содержащихся элементов OLE.

##  <a name="getstartposition"></a>Коледокумент:: Жетстартпоситион

Вызовите эту функцию, чтобы получить позицию первого элемента в документе.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое можно использовать для начала итерации элементов документа; Значение NULL, если документ не содержит элементов.

### <a name="remarks"></a>Remarks

Передайте значение, возвращаемое в `GetNextItem`, `GetNextClientItem`или `GetNextServerItem`.

##  <a name="hasblankitems"></a>Коледокумент:: Хасбланкитемс

Вызовите эту функцию, чтобы определить, содержит ли документ пустые элементы.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ содержит пустые элементы; в противном случае — 0.

### <a name="remarks"></a>Remarks

Пустой элемент — это тот, прямоугольник которого пуст.

##  <a name="oneditchangeicon"></a>Коледокумент:: Онедитчанжеикон

Отображает диалоговое окно значок изменения OLE и изменяет значок, представляющий выбранный в данный момент элемент OLE, на значок, который пользователь выбирает в диалоговом окне.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Remarks

`OnEditChangeIcon` создает и запускает диалоговое окно «Изменение значка `COleChangeIconDialog`».

##  <a name="oneditconvert"></a>Коледокумент:: Онедитконверт

Отображает диалоговое окно OLE Convert и преобразует или активирует выбранный в данный момент элемент OLE в соответствии с выбором пользователем в диалоговом окне.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Remarks

`OnEditConvert` создает и запускает диалоговое окно Преобразование `COleConvertDialog`.

Пример преобразования заключается в преобразовании документа Microsoft Word в документ WordPad.

##  <a name="oneditlinks"></a>Коледокумент:: Онедитлинкс

Отображает диалоговое окно OLE Edit/Links.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Remarks

`OnEditLinks` создает и запускает диалоговое окно ссылки `COleLinksDialog`, позволяющее пользователю изменять связанные объекты.

##  <a name="onfilesendmail"></a>Коледокумент:: Онфилесендмаил

Отправляет сообщение через узел резидентной почты (если есть) с документом в качестве вложения.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Remarks

`OnFileSendMail` вызывает `OnSaveDocument` для сериализации (сохранения) безымянных и измененных документов во временный файл, который затем отправляется через электронную почту. Если документ не был изменен, то временный файл не требуется. будет отправлен исходный объект. `OnFileSendMail` загружает библиотека MAPI32. DLL, если она еще не загружена.

В отличие от реализации `OnFileSendMail` для `CDocument`, эта функция правильно обрабатывает составные файлы.

Дополнительные сведения см. в [разделах о MAPI](../../mfc/mapi.md) и [поддержка MAPI в](../../mfc/mapi-support-in-mfc.md) статьях MFC.

##  <a name="onshowviews"></a>Коледокумент:: Оншоввиевс

Платформа вызывает эту функцию после изменения состояния видимости документа.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Параметры

*бвисибле*<br/>
Указывает, стал ли документ видимым или невидимым.

### <a name="remarks"></a>Remarks

Версия по умолчанию этой функции не выполняет никаких действий. Переопределите его, если приложение должно выполнить специальную обработку при изменении видимости документа.

##  <a name="onupdateeditchangeicon"></a>Коледокумент:: Онупдатидитчанжеикон

Вызывается платформой для обновления команды "изменить значок" в меню "Правка".

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на структуру `CCmdUI`, которая представляет меню, вызвавшее команду обновления. Обработчик обновлений вызывает `Enable` функцию-член структуры `CCmdUI` с помощью *пкмдуи* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Remarks

`OnUpdateEditChangeIcon` обновляет пользовательский интерфейс команды в зависимости от того, существует ли в документе допустимый значок. Переопределите эту функцию, чтобы изменить поведение.

##  <a name="onupdateeditlinksmenu"></a>Коледокумент:: Онупдатидитлинксмену

Вызывается платформой для обновления команды Links в меню Правка.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на структуру `CCmdUI`, которая представляет меню, вызвавшее команду обновления. Обработчик обновлений вызывает `Enable` функцию-член структуры `CCmdUI` с помощью *пкмдуи* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Remarks

Начиная с первого элемента OLE в документе `OnUpdateEditLinksMenu` обращается к каждому элементу, проверяет, является ли элемент ссылкой, и, если это ссылка, включает команду Links. Переопределите эту функцию, чтобы изменить поведение.

##  <a name="onupdateobjectverbmenu"></a>Коледокумент:: Онупдатеобжектвербмену

Вызывается платформой для обновления команды *objectname* в меню "Правка" и меню "команда", доступ к которому осуществляется из команды *objectname* , где *OBJECTNAME* — это имя объекта OLE, внедренного в документ.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на структуру `CCmdUI`, которая представляет меню, вызвавшее команду обновления. Обработчик обновлений вызывает `Enable` функцию-член структуры `CCmdUI` с помощью *пкмдуи* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Remarks

`OnUpdateObjectVerbMenu` обновляет пользовательский интерфейс команды *objectname* в зависимости от того, существует ли в документе допустимый объект. Если объект существует, команда *objectname* в меню Правка становится доступной. При выборе этой команды меню отображается подменю команда. Подменю verb содержит все команды команд, доступные для объекта, такие как Правка, свойства и т. д. Переопределите эту функцию, чтобы изменить поведение.

##  <a name="onupdatepastelinkmenu"></a>Коледокумент:: Онупдатепастелинкмену

Вызывается платформой, чтобы определить, можно ли вставлять связанный OLE-элемент из буфера обмена.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на структуру `CCmdUI`, которая представляет меню, вызвавшее команду обновления. Обработчик обновлений вызывает `Enable` функцию-член структуры `CCmdUI` с помощью *пкмдуи* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Remarks

Команда Специальная вставка меню включена или отключена в зависимости от того, можно ли вставить элемент в документ.

##  <a name="onupdatepastemenu"></a>Коледокумент:: Онупдатепастемену

Вызывается платформой, чтобы определить, можно ли вставлять внедренный объект OLE из буфера обмена.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на структуру `CCmdUI`, которая представляет меню, вызвавшее команду обновления. Обработчик обновлений вызывает `Enable` функцию-член структуры `CCmdUI` с помощью *пкмдуи* для обновления пользовательского интерфейса.

### <a name="remarks"></a>Remarks

Команда меню и кнопка «Вставить» включены или отключены в зависимости от того, можно ли вставить элемент в документ или нет.

##  <a name="removeitem"></a>Коледокумент:: RemoveItem

Вызовите эту функцию, чтобы удалить элемент из документа.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Параметры

*питем*<br/>
Указатель на удаляемый элемент документа.

### <a name="remarks"></a>Remarks

Обычно вызывать эту функцию явно не требуется; Он вызывается деструкторами для `COleClientItem` и `COleServerItem`.

##  <a name="updatemodifiedflag"></a>Коледокумент:: Упдатемодифиедфлаг

Вызовите эту функцию, чтобы пометить документ как измененный, если любой из содержащихся в нем элементов OLE был изменен.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Remarks

Это позволяет платформе предлагать пользователю сохранить документ перед закрытием, даже если собственные данные в документе не были изменены.

## <a name="see-also"></a>См. также раздел

[Образец контейнера MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример МФКБИНД для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
