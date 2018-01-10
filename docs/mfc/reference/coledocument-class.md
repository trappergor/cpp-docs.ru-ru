---
title: "Класс COleDocument | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 147a3bca2f4ad91aeaa2c74ac7a356d9404943fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coledocument-class"></a>Класс COleDocument
Базовый класс для документов OLE, которые поддерживают визуальное редактирование.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|Создает объект `COleDocument`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|Добавляет элемент в список элементов, сохраняется в документе.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Задает печати целевого устройства для всех клиентских элементов в документе.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|В результате документы должны храниться в формате структурированного хранения OLE.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Возвращает элемент OLE, который является активным в данный момент на месте.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|Переходит к следующему элементу клиента для выполнения итерации.|  
|[COleDocument::GetNextItem](#getnextitem)|Переходит к следующему элементу документа для выполнения итерации.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|Переходит к следующему элементу сервера для выполнения итерации.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Возвращает основной выбранного элемента OLE в документе.|  
|[COleDocument::GetStartPosition](#getstartposition)|Возвращает начальное положение для начала итерации.|  
|[COleDocument::HasBlankItems](#hasblankitems)|Проверяет наличие пустых ячеек в документе.|  
|[COleDocument::OnShowViews](#onshowviews)|Вызывается, когда документ становится видимым или невидимым.|  
|[COleDocument::RemoveItem](#removeitem)|Удаляет элемент из списка элементов, сохраняется в документе.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Пометка его как измененный, если были изменены какие-либо содержащиеся элементы OLE.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Обрабатывает события в команде меню изменить значок.|  
|[COleDocument::OnEditConvert](#oneditconvert)|Выполняет преобразование внедренного или связанного объекта из одного типа в другой.|  
|[COleDocument::OnEditLinks](#oneditlinks)|Обработка событий в команде ссылки в меню "Правка".|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|Отправляет сообщение электронной почты с присоединенным документом.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Вызывается платформой для обновления команды пользовательского интерфейса для пункта меню значок редактирования/изменить.|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Вызывается платформой для обновления команды пользовательского интерфейса для пункта меню Правка и связей.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Вызывается платформой для обновления команды пользовательского интерфейса для изменения или *ObjectName* пункт меню и подменю команды, доступном редактирования / *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Вызывается платформой для обновления пользовательского интерфейса команда Специальная вставка пункта меню.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Вызывается платформой для обновления пользовательского интерфейса команды меню «Вставить».|  
  
## <a name="remarks"></a>Примечания  
 `COleDocument`является производным от **CDocument**, который позволяет использовать архитектуры document/view, предоставляемые библиотекой классов Microsoft Foundation приложениями OLE.  
  
 `COleDocument`обрабатывает документа как коллекцию [CDocItem](../../mfc/reference/cdocitem-class.md) объектов для обработки элементов OLE. Контейнер и сервер приложений требуют такой архитектуры, так как их документы должен иметь возможность содержать OLE-элементы. [COleServerItem](../../mfc/reference/coleserveritem-class.md) и [COleClientItem](../../mfc/reference/coleclientitem-class.md) классы как производные от `CDocItem`, взаимодействие между приложениями и OLE-элементы управления.  
  
 При написании приложения простой контейнер вашего документа создайте класс, производный от `COleDocument`. При написании приложения-контейнера, который поддерживает связывание со встроенными элементами, содержащиеся в ней документы являются производными класса документа из [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). При создании сервера приложения или сочетания контейнера и сервера, являются производными класса документа из [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc`и `COleServerDoc` являются производными от `COleDocument`, поэтому эти классы наследуют все службы, доступные в `COleDocument` и **CDocument**.  
  
 Чтобы использовать `COleDocument`, создайте класс, производный от него и добавить функциональные возможности для управления приложением данных, отличных от OLE, а также внедренные и связанные элементы. Если определить `CDocItem`-производных классов для хранения данных в собственном приложении, можно использовать реализацию по умолчанию, определяемый `COleDocument` для хранения данных, отличных от OLE и OLE. Можно также создать свои собственные структуры данных для хранения данных не OLE отдельно от элементов OLE. Дополнительные сведения см. в статье [контейнеры: составных файлов](../../mfc/containers-compound-files.md)...  
  
 **CDocument** поддерживает отправку документа по почте, если присутствует почтовых служб (MAPI). `COleDocument`обновил [OnFileSendMail](#onfilesendmail) для правильной обработки составных документов. Дополнительные сведения см. в статьях [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="additem"></a>COleDocument::AddItem  
 Вызывайте эту функцию, чтобы добавить элемент в документ.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на добавленный элемент документа.  
  
### <a name="remarks"></a>Примечания  
 Необходимо явным образом вызвать эту функцию при ее вызове `COleClientItem` или `COleServerItem` конструктор, который принимает указатель на документ.  
  
##  <a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 Вызывайте эту функцию, чтобы изменить печати целевого устройства для всех внедренных [COleClientItem](../../mfc/reference/coleclientitem-class.md) элементов в документе-контейнере приложения.  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Параметры  
 `ptd`  
 Указатель на **DVTARGETDEVICE** структуру данных, которая содержит сведения о новых печати целевого устройства. Может быть **NULL**.  
  
 `ppd`  
 Указатель на **PRINTDLG** структуру данных, которая содержит сведения о новых печати целевого устройства. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обновляет печати целевого устройства для всех элементов, но не обновляет кэш презентации для этих элементов. Чтобы обновить кэш презентации для элемента, следует вызвать [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).  
  
 Аргументы для этой функции содержат сведения, который OLE использует для обнаружения целевого устройства. [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) структура содержит данные, используемые для инициализации общее диалоговое окно печати. После закрытия пользователем окно Windows возвращает сведения о выбора пользователя в этой структуре. `m_pd` Членом [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объект **PRINTDLG** структуры.  
  
 Дополнительные сведения см. в разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуры в Windows SDK.  
  
##  <a name="coledocument"></a>COleDocument::COleDocument  
 Создает объект `COleDocument`.  
  
```  
COleDocument();
```  
  
##  <a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 Эта функция вызывается в том случае, если вы хотите сохранить документ с помощью составного файл формата.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, включена ли поддержка составных файлов.  
  
### <a name="remarks"></a>Примечания  
 Это также называется структурированным хранилищем. Обычно эта функция вызывается из конструктора вашей `COleDocument`-производного класса. Дополнительные сведения о составных документов см. в статье [контейнеры: составные файлы](../../mfc/containers-compound-files.md)...  
  
 Если не вызывается эта функция-член, документы будут храниться в формате файла nonstructured («плоский»).  
  
 После поддержка составных файлов включена или отключена для документа, параметр не должны изменяться во время существования документа.  
  
##  <a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 Вызов эту функцию для получения OLE элементом, к которому в настоящее время активации на месте в окне фрейма, содержащего представление, обозначенную `pWnd`.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, отображающее документе-контейнере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на одном месте, в активной объекта OLE; **NULL** при отсутствии OLE элемента в настоящее время в состоянии «активен на месте».  
  
##  <a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 Эта функция вызывается несколько раз для каждого элемента в документе клиента доступа.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** заданным значением с предыдущим вызовом `GetNextClientItem`; начального значения возвращаемый `GetStartPosition` функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий элемент клиента в документе, или **NULL** Если больше нет элементов клиента.  
  
### <a name="remarks"></a>Примечания  
 После каждого вызова значение `pos` задано для следующего элемента в документ, который может или не может быть элементом клиента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="getnextitem"></a>COleDocument::GetNextItem  
 Эта функция вызывается несколько раз для каждого элемента в документе доступ.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** заданным значением с предыдущим вызовом `GetNextItem`; начального значения возвращаемый `GetStartPosition` функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент документа в указанной позиции.  
  
### <a name="remarks"></a>Примечания  
 После каждого вызова значение `pos` равно **ПОЗИЦИИ** значение следующего элемента в документе. Если полученный элемент является последним элементом в документе, новое значение `pos` — **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 Эта функция вызывается несколько раз для каждого элемента в документе сервера доступа.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** заданным значением с предыдущим вызовом `GetNextServerItem`; начального значения возвращаемый `GetStartPosition` функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий элемент сервера в документе, или **NULL** Если больше нет элементов сервера.  
  
### <a name="remarks"></a>Примечания  
 После каждого вызова значение `pos` задано для следующего элемента в документе, который может или не может быть серверным элементом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 Вызывается платформой для извлечения текущего выбранного элемента OLE в указанном представлении.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>Параметры  
 `pView`  
 Указатель на объект активное представление Отображение документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на один выбранный элемент OLE; **NULL** Если элементы OLE не выбраны или если более чем один выбран.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию выполняет автономной OLE список элементов для один выбранный элемент и возвращает указатель на него. Если элементы не выбраны или если имеется более одного элемента, выбранного, функция возвращает **NULL**. Необходимо переопределить `CView::IsSelected` функции-члена в классе представления для этой функции для работы. Переопределите эту функцию, если у вас есть собственный метод хранения вложенных элементов OLE.  
  
##  <a name="getstartposition"></a>COleDocument::GetStartPosition  
 Эта функция вызывается для получения позиции первого элемента в документе.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться в начале итерации по элементам документа; **NULL** Если документ не содержит элементов.  
  
### <a name="remarks"></a>Примечания  
 Передайте значение, возвращаемое `GetNextItem`, `GetNextClientItem`, или `GetNextServerItem`.  
  
##  <a name="hasblankitems"></a>COleDocument::HasBlankItems  
 Эта функция вызывается для определения, содержит ли документ какие-либо пустые элементы.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ содержит пустые элементы; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Пустой элемент является одним которой прямоугольник является пустым.  
  
##  <a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 Открытие диалогового окна OLE изменить значок и изменяет значок, представляющий текущий выбранный элемент OLE на значок, выбранного пользователем в диалоговом окне.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>Примечания  
 `OnEditChangeIcon`Создает и запускает `COleChangeIconDialog` диалоговое окно "Изменить значок".  
  
##  <a name="oneditconvert"></a>COleDocument::OnEditConvert  
 Отображает диалоговое окно преобразования OLE и преобразует или активирует текущего выделенного элемента OLE в зависимости от выбора пользователя в диалоговом окне.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>Примечания  
 `OnEditConvert`Создает и запускает `COleConvertDialog` преобразование-диалоговое окно.  
  
 Пример преобразования является преобразование документа Microsoft Word в документ WordPad.  
  
##  <a name="oneditlinks"></a>COleDocument::OnEditLinks  
 Отображение диалогового окна OLE редактирования и связей.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>Примечания  
 `OnEditLinks`Создает и запускает `COleLinksDialog` ссылки диалоговым окном, которое позволяет пользователю изменять связанные объекты.  
  
##  <a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 Отправляет сообщение через узел резидентного почтового (если таковые имеются) в документе как вложение.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>Примечания  
 `OnFileSendMail`вызовы `OnSaveDocument` для сериализации (Сохранить) без имени и измененные документы во временный файл, который затем отправляется по электронной почте. Если документ не был изменен, временный файл не требуется; отправляется исходный. `OnFileSendMail`Загружает MAPI32. Библиотеки DLL, если он еще не загружена.  
  
 В отличие от реализации `OnFileSendMail` для **CDocument**, эта функция правильно обрабатывает составных файлов.  
  
 Дополнительные сведения см. в разделе [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md) статьи...  
  
##  <a name="onshowviews"></a>COleDocument::OnShowViews  
 Платформа вызывает эту функцию после документа видимости изменений состояния.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>Параметры  
 `bVisible`  
 Указывает, стала ли документ видимым или невидимым.  
  
### <a name="remarks"></a>Примечания  
 Версия этой функции по умолчанию не выполняет никаких действий. Его необходимо переопределите в том случае, если какой-либо специальные обработки при изменении режима видимости документа должно выполнять приложение.  
  
##  <a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 Вызывается платформой для обновления команда Изменить значок в меню "Правка".  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, вызвавшего команду update. Обработчик вызывает метод обновления **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 `OnUpdateEditChangeIcon`обновляет пользовательский интерфейс команды, в зависимости от того, является ли допустимым значок существует в документе. Переопределите эту функцию для изменения поведения.  
  
##  <a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 Вызывается платформой для обновления команды связи в меню Правка.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, вызвавшего команду update. Обработчик вызывает метод обновления **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Начиная с первого элемента OLE в документе, `OnUpdateEditLinksMenu` обращается к каждому элементу, проверяет, является ли элемент ссылки и, если это ссылка, включает команду связи. Переопределите эту функцию для изменения поведения.  
  
##  <a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 Вызывается платформой для обновления *ObjectName* команду в меню "Правка" и в подменю команду обращаться из *ObjectName* команду, где *ObjectName* имя OLE-объекта, внедренного в документ.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, вызвавшего команду update. Обработчик вызывает метод обновления **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 `OnUpdateObjectVerbMenu`обновления *ObjectName* команды пользовательского интерфейса в зависимости от того, является ли допустимым объект существует в документе. Если объект существует, *ObjectName* команды в меню "Правка" включен. При выборе этого пункта меню отображается в подменю команду. В подменю команду содержит всех команд, доступных для объекта, например изменить свойства и т. д. Переопределите эту функцию для изменения поведения.  
  
##  <a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 Вызывается платформой для определения, является ли связанный элемент OLE можно вставить из буфера обмена.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, вызвавшего команду update. Обработчик вызывает метод обновления **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Специальная команда меню включен или отключен в зависимости от того, является ли элемент, можно вставить в документ или нет.  
  
##  <a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 Вызывается платформой, чтобы определить, можно ли вставить из буфера обмена встроенного элемента OLE.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, вызвавшего команду update. Обработчик вызывает метод обновления **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Вставить команду меню и кнопки включены или отключены в зависимости от того, является ли элемент, можно вставить в документ или нет.  
  
##  <a name="removeitem"></a>COleDocument::RemoveItem  
 Эта функция вызывается для удаления элемента из документа.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель удаляемого элемента документа.  
  
### <a name="remarks"></a>Примечания  
 Обычно не требуется эта функция вызывается явным образом; его вызывает деструкторы для `COleClientItem` и `COleServerItem`.  
  
##  <a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 Вызывайте эту функцию, чтобы пометить документ как измененный, если были изменены какие-либо содержащиеся элементы OLE.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>Примечания  
 Благодаря этому платформа предложить пользователю сохранить документ перед закрытием, даже если собственные данные в документе не был изменен.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC КОНТЕЙНЕРА](../../visual-cpp-samples.md)   
 [Пример MFC MFCBIND](../../visual-cpp-samples.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



