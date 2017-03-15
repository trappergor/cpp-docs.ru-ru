---
title: "Класс COleDocument | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocument
dev_langs:
- C++
helpviewer_keywords:
- COleDocument class
- OLE documents, base class
- OLE containers, client items
- visual editing, OLE document base class
- OLE documents
- documents, OLE
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
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
ms.openlocfilehash: 73bd1bc5c2c93e180b42a79cf23ab98360887c31
ms.lasthandoff: 02/24/2017

---
# <a name="coledocument-class"></a>Класс COleDocument
Базовый класс для документов OLE, которые поддерживают визуальное редактирование.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|Создает объект `COleDocument`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|Добавляет элемент в список элементов, сохраняется в документе.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Задает печати целевое устройство для всех клиентских элементов в документе.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|В результате документы должны храниться в формате структурированного хранилища OLE.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Возвращает элемент OLE, который является активным в данный момент на месте.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|Получает следующий элемент клиента для итерации.|  
|[COleDocument::GetNextItem](#getnextitem)|Получает следующий элемент документа для итерации.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|Переходит к следующему элементу сервера для выполнения итерации.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Возвращает основной выделенного объекта OLE в документ.|  
|[COleDocument::GetStartPosition](#getstartposition)|Возвращает начальное положение для начала итерации.|  
|[COleDocument::HasBlankItems](#hasblankitems)|Проверяет наличие пустых ячеек в документе.|  
|[COleDocument::OnShowViews](#onshowviews)|Вызывается, когда документ становится видимым или невидимым.|  
|[COleDocument::RemoveItem](#removeitem)|Удаляет элемент из списка элементов, сохраняется в документе.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Помечает документ как измененный, если были изменены какие-либо содержащиеся элементы OLE.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Обрабатывает события в команде меню изменить значок.|  
|[COleDocument::OnEditConvert](#oneditconvert)|Выполняет преобразование внедренного или связанного объекта из одного типа в другой.|  
|[COleDocument::OnEditLinks](#oneditlinks)|Обрабатывает события, в меню Правка команду связи.|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|Отправляет сообщение электронной почты с вложенным документом.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Вызывается платформой для обновления пользовательского интерфейса команды пункта меню Правка/изменение значка.|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Вызывается платформой для обновления команде пользовательского интерфейса для пункта меню Правка и ссылок.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Вызывается платформой для обновления командный пользовательский Интерфейс для редактирования и *ObjectName* пункт меню и подменю команды доступны из редактирования или *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Вызывается платформой для обновления пользовательского интерфейса команды Специальная вставка пункта меню.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Вызывается платформой для обновления команде пользовательского интерфейса для меню «Вставка».|  
  
## <a name="remarks"></a>Примечания  
 `COleDocument`является производным от **CDocument**, который позволяет приложениям OLE используется архитектура документов и представлений, предоставляемых библиотеки Microsoft Foundation Class.  
  
 `COleDocument`обрабатывает документ как совокупность [CDocItem](../../mfc/reference/cdocitem-class.md) объектов для обработки элементов OLE. Контейнер и серверные приложения требуют такой архитектуры, так как их документы должны иметь возможность содержать OLE-элементы. [Производного от COleServerItem](../../mfc/reference/coleserveritem-class.md) и [COleClientItem](../../mfc/reference/coleclientitem-class.md) классы, оба являются производными от `CDocItem`, взаимодействие между приложениями и OLE-элементы управления.  
  
 При написании приложения простой контейнер вашего документа создайте класс, производный от `COleDocument`. При написании приложения-контейнера, который поддерживает связывание внедренных элементов, содержащихся в свои документы, сформируйте класс документа из [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). При создании сервера приложения или сочетания контейнера и сервера, сформируйте класс документа из [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc`и `COleServerDoc` являются производными от `COleDocument`, поэтому эти классы наследуют все службы, доступные в `COleDocument` и **CDocument**.  
  
 Для использования `COleDocument`, создайте класс, производный от него и добавлять функциональные возможности для управления приложением данных, отличных от OLE, а также внедренные и связанные элементы. Если определить `CDocItem`-производные классы для хранения данных собственного приложения, можно использовать реализацию по умолчанию, определяется `COleDocument` для хранения данных, отличных от OLE и OLE. Также можно создавать собственные структуры данных для хранения данных не OLE отдельно от элементов OLE. Дополнительные сведения см. в статье [контейнеров: составные файлы](../../mfc/containers-compound-files.md)...  
  
 **CDocument** поддерживает отправку документа электронной почте при наличии поддержки электронной почты (MAPI). `COleDocument`обновлен [OnFileSendMail](#onfilesendmail) для правильной обработки составных документов. Дополнительные сведения см. в статьях [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-nameadditema--coledocumentadditem"></a><a name="additem"></a>COleDocument::AddItem  
 Эта функция вызывается для добавления элемента в документе.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на добавленный элемент документа.  
  
### <a name="remarks"></a>Примечания  
 Необходимо явно вызвать эту функцию, когда она вызвана `COleClientItem` или `COleServerItem` конструктор, который принимает указатель на документ.  
  
##  <a name="a-nameapplyprintdevicea--coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 Эта функция вызывается для печати целевое устройство можно изменить для всех внедренных [COleClientItem](../../mfc/reference/coleclientitem-class.md) элементов в документе-контейнере приложения.  
  
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
 Эта функция обновляет печати целевое устройство для всех элементов, но не обновляет кэш презентации для этих элементов. Чтобы обновить кэш презентации для элемента, вызовите [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).  
  
 Аргументов для этой функции содержат сведения, который OLE использует для определения целевого устройства. [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) структура содержит данные, используемые для инициализации общее диалоговое окно печати. После пользователь закроет диалоговое окно, Windows возвращает сведения о выбранных пользователем в этой структуре. `m_pd` Членом [CPrintDialog](../../mfc/reference/cprintdialog-class.md) объект **PRINTDLG** структуры.  
  
 Дополнительные сведения см. в разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecoledocumenta--coledocumentcoledocument"></a><a name="coledocument"></a>COleDocument::COleDocument  
 Создает объект `COleDocument`.  
  
```  
COleDocument();
```  
  
##  <a name="a-nameenablecompoundfilea--coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 Эта функция вызывается в том случае, если вы хотите сохранить документ в формате составной файл.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, включена ли поддержка составной файл.  
  
### <a name="remarks"></a>Примечания  
 Это также называется структурированным хранилищем. Эта функция обычно вызывается из конструктора вашей `COleDocument`-производного класса. Дополнительные сведения о составных документов см. в статье [контейнеров: составные файлы](../../mfc/containers-compound-files.md)...  
  
 Если не вызвать эту функцию-член, документы будут храниться в формате файла nonstructured («плоский»).  
  
 После поддержка составных файлов включено или отключено для документа, параметр не должны изменяться во время существования документа.  
  
##  <a name="a-namegetinplaceactiveitema--coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 Вызов эту функцию для получения OLE элементом, к которому в настоящее время активации на месте в рамка окна, содержащего представление, определяется `pWnd`.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, в котором отображается документе-контейнере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на одном месте, в активного объекта OLE; **NULL** при отсутствии OLE элемента в настоящее время в состоянии «активным на месте».  
  
##  <a name="a-namegetnextclientitema--coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 Эта функция вызывается несколько раз для доступа к каждой клиентские элементы в документе.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** заданным значением с предыдущим вызовом `GetNextClientItem`; начального значения возвращаемый `GetStartPosition` функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий клиентский элемент в документе, или **NULL** Если нет дополнительных элементов клиента.  
  
### <a name="remarks"></a>Примечания  
 После каждого вызова значение `pos` задается для следующего элемента в документ, который может быть или не быть клиентский элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#1;](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="a-namegetnextitema--coledocumentgetnextitem"></a><a name="getnextitem"></a>COleDocument::GetNextItem  
 Эта функция вызывается несколько раз для доступа к каждый из элементов в документе.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** заданным значением с предыдущим вызовом `GetNextItem`; начального значения возвращаемый `GetStartPosition` функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент документа в указанной позиции.  
  
### <a name="remarks"></a>Примечания  
 После каждого вызова значение `pos` равен **ПОЗИЦИИ** значение следующего элемента в документе. Если полученный элемент является последним элементом в документе, новое значение `pos` — **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#2;](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="a-namegetnextserveritema--coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 Эта функция вызывается несколько раз для каждого элемента в документе сервера доступа.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** заданным значением с предыдущим вызовом `GetNextServerItem`; начального значения возвращаемый `GetStartPosition` функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий серверный элемент в документе, или **NULL** Если нет дополнительных элементов сервера.  
  
### <a name="remarks"></a>Примечания  
 После каждого вызова значение `pos` задается для следующего элемента в документ, который может быть или не быть элемента сервера.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleServer&#2;](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="a-namegetprimaryselecteditema--coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 Вызывается платформой для получения текущего выделенного элемента OLE в указанном представлении.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>Параметры  
 `pView`  
 Указатель на объект активное представление, отображение документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на один выбранный элемент OLE; **NULL** Если элементы OLE не выбраны или если более чем один выбран.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию выполняет поиск в списке автономной OLE элементов для одного выбранного элемента и возвращает указатель на него. Если нет выбранного элемента, или если выбрать более одного элемента, функция возвращает **NULL**. Необходимо переопределить `CView::IsSelected` функции-члена в классе представления для работы этой функции. Переопределите эту функцию, если у вас есть собственный метод хранения элементов OLE.  
  
##  <a name="a-namegetstartpositiona--coledocumentgetstartposition"></a><a name="getstartposition"></a>COleDocument::GetStartPosition  
 Эта функция вызывается для получения позиции первого элемента в документе.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое можно использовать для начала итерации по элементам документа; **NULL** Если документ не имеет элементов.  
  
### <a name="remarks"></a>Примечания  
 Передайте значение, возвращаемое `GetNextItem`, `GetNextClientItem`, или `GetNextServerItem`.  
  
##  <a name="a-namehasblankitemsa--coledocumenthasblankitems"></a><a name="hasblankitems"></a>COleDocument::HasBlankItems  
 Эта функция вызывается для определения, содержит ли документ все пустые элементы.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ содержит пустые элементы; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Пустой элемент, которого прямоугольник пуст.  
  
##  <a name="a-nameoneditchangeicona--coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 Открытие диалогового окна OLE сменить значок и изменяет значок, представляющий выделенный элемент OLE значка, выбранного пользователем в диалоговом окне.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>Примечания  
 `OnEditChangeIcon`Создает и запускает `COleChangeIconDialog` диалоговое окно Изменить значок.  
  
##  <a name="a-nameoneditconverta--coledocumentoneditconvert"></a><a name="oneditconvert"></a>COleDocument::OnEditConvert  
 Отображает диалоговое окно преобразования OLE и преобразование или активизация текущего выделенного объекта OLE в соответствии с выбором пользователя в диалоговом окне.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>Примечания  
 `OnEditConvert`Создает и запускает `COleConvertDialog` диалоговое окно «Convert».  
  
 Пример преобразования является преобразование документа Microsoft Word в документ WordPad.  
  
##  <a name="a-nameoneditlinksa--coledocumentoneditlinks"></a><a name="oneditlinks"></a>COleDocument::OnEditLinks  
 Отображение диалогового окна OLE изменения и ссылок.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>Примечания  
 `OnEditLinks`Создает и запускает `COleLinksDialog` ссылки диалоговым окном, которое позволяет пользователю изменять связанные объекты.  
  
##  <a name="a-nameonfilesendmaila--coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 Отправляет сообщение через узел резидентных почтового (если таковые имеются) в документе как вложение.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>Примечания  
 `OnFileSendMail`вызывает `OnSaveDocument` для сериализации (безымянный и измененных документов во временный файл, который затем отправляется по электронной почте Сохранить). Если документ не был изменен, временный файл не требуется; Исходное отправленное. `OnFileSendMail`Загружает MAPI32. Библиотека DLL, если он еще не загружена.  
  
 В отличие от реализации `OnFileSendMail` для **CDocument**, эта функция правильно обрабатывает составные файлы.  
  
 Дополнительные сведения см. в разделе [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md) статьи...  
  
##  <a name="a-nameonshowviewsa--coledocumentonshowviews"></a><a name="onshowviews"></a>COleDocument::OnShowViews  
 Платформа вызывает эту функцию после документа видимости изменений состояния.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>Параметры  
 `bVisible`  
 Указывает, стала ли документ видимым или невидимым.  
  
### <a name="remarks"></a>Примечания  
 Версия по умолчанию эта функция не выполняет никаких действий. Его необходимо переопределите в том случае, если приложение необходимо выполнить все команды обработки при изменении режима видимости документа.  
  
##  <a name="a-nameonupdateeditchangeicona--coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 Вызывается платформой для обновления в меню Правка выберите команду Изменить значок.  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызывает обработчик обновление **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 `OnUpdateEditChangeIcon`Обновляет командный пользовательский интерфейс в зависимости от того, является ли допустимым значок существует в документе. Переопределите эту функцию, чтобы изменить поведение.  
  
##  <a name="a-nameonupdateeditlinksmenua--coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 Вызывается платформой для обновления команду связи в меню Правка.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызывает обработчик обновление **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Начиная с первого элемента в документе OLE `OnUpdateEditLinksMenu` обращается к каждого элемента, проверяет, является ли элемент ссылки и, если это ссылка, включает команды связи. Переопределите эту функцию, чтобы изменить поведение.  
  
##  <a name="a-nameonupdateobjectverbmenua--coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 Вызывается платформой для обновления *ObjectName* команды в меню "Правка" и доступны из подменю команду *ObjectName* команду, где *ObjectName* является имя объекта OLE, внедренные в документ.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызывает обработчик обновление **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 `OnUpdateObjectVerbMenu`обновления *ObjectName* команды пользовательского интерфейса в зависимости от того, является ли допустимым объект существует в документе. Если объект существует, *ObjectName* команды в меню «Правка» включена. При выборе этого пункта меню отображается в подменю команду. Команда подменю содержит всех команд, доступных для этого объекта, например изменение, свойства и т. д. Переопределите эту функцию, чтобы изменить поведение.  
  
##  <a name="a-nameonupdatepastelinkmenua--coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 Вызывается средой, чтобы определить, является ли связанный элемент OLE можно вставить из буфера обмена.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызывает обработчик обновление **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Специальная команда меню включен или отключен в зависимости от того, является ли элемент, можно вставить в документ или нет.  
  
##  <a name="a-nameonupdatepastemenua--coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 Вызывается средой, чтобы определить, можно ли вставить из буфера обмена встроенного элемента OLE.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на `CCmdUI` структуру, которая представляет меню, которое создается команда обновления. Вызывает обработчик обновление **включить** функцию-член `CCmdUI` структуры через `pCmdUI` для обновления пользовательского интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Вставьте команду меню и кнопки включены или отключены в зависимости от того, является ли элемент, можно вставить в документ или нет.  
  
##  <a name="a-nameremoveitema--coledocumentremoveitem"></a><a name="removeitem"></a>COleDocument::RemoveItem  
 Эта функция вызывается для удаления элемента из документа.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель удаляемого элемента документа.  
  
### <a name="remarks"></a>Примечания  
 Обычно не требуется эта функция вызывается явным образом; она вызвана деструкторы для `COleClientItem` и `COleServerItem`.  
  
##  <a name="a-nameupdatemodifiedflaga--coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 Эта функция вызывается для пометить документ как измененный, если были изменены какие-либо содержащиеся элементы OLE.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>Примечания  
 Благодаря этому платформа предложить пользователю сохранить документ перед закрытием, даже если собственные данные в документ не был изменен.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC КОНТЕЙНЕРА](../../visual-cpp-samples.md)   
 [Пример MFC MFCBIND](../../visual-cpp-samples.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




