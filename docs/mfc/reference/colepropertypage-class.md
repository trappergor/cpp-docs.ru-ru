---
title: "Класс COlePropertyPage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::IgnoreApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
dev_langs:
- C++
helpviewer_keywords:
- OLE property pages
- custom controls [MFC], properties
- COlePropertyPage class
- properties [C++], displaying
- displaying properties
- property pages, OLE
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 20d70cc25305fc5d17860314d9cfbe927df65c70
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertypage-class"></a>Класс COlePropertyPage
Используется для отображения свойств пользовательского элемента управления в графическом интерфейсе подобно диалоговому окну.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Создает объект `COlePropertyPage`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Указывает, изменил ли пользователь значение в элементе управления.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Возвращает массив объектов, изменяется на странице свойств.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Возвращает указатель на страницу свойств `IPropertyPageSite` интерфейса.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Определяет, какие элементы управления, не включайте кнопки "Применить".|  
|[COlePropertyPage::IsModified](#ismodified)|Указывает, изменил ли пользователь на странице свойств.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Вызывается платформой, когда пользователь редактирует свойство.|  
|[COlePropertyPage::OnHelp](#onhelp)|Вызывается платформой, когда пользователь вызывает справку.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Вызывается платформой после инициализации страницы свойств.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Вызывается инфраструктурой при выборе другого элемента управления OLE, с помощью новых свойств.|  
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Вызывается платформой, когда рамка свойства предоставляет страничный сайт.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Задает флаг, указывающий, является ли пользователь изменил значение в элементе управления.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Задает ресурс диалогового окна страницы свойств.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Задает страницу свойств краткая справка, имя его файла справки и его контекста справки.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающий, изменил ли пользователь на странице свойств.|  
|[COlePropertyPage::SetPageName](#setpagename)|Задает имя страницы свойств (заголовок).|  
  
## <a name="remarks"></a>Примечания  
 Например страница свойств может включать элемент управления редактирования, пользователь может просматривать и изменять свойства caption элемента управления.  
  
 Каждого свойства элемента управления пользовательские или акций может иметь управления диалогового окна, который позволяет пользователю просматривать текущее значение свойства и при необходимости измените это значение элемента управления.  
  
 Дополнительные сведения об использовании `COlePropertyPage`, см. в статье [элементы управления ActiveX: страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="colepropertypage"></a>COlePropertyPage::COlePropertyPage  
 Создает объект `COlePropertyPage`.  
  
```  
COlePropertyPage(
    UINT idDlg,  
    UINT idCaption);
```  
  
### <a name="parameters"></a>Параметры  
 *idDlg*  
 Идентификатор ресурса шаблона диалогового окна.  
  
 *idCaption*  
 Идентификатор ресурса для заголовка страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 При реализации подкласс `COlePropertyPage`, следует использовать конструктор ваш подкласс `COlePropertyPage` конструктор для идентификации ресурса шаблона диалогового окна на основанную на странице свойств и строковый ресурс, содержащий его заголовок.  
  
##  <a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus  
 Определяет, является ли пользователь изменил значение свойства элемента управления страницы с идентификатором указанного ресурса.  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор ресурса для элемента управления страниц свойств.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если значение элемента управления был изменен; в противном случае **FALSE**.  
  
##  <a name="getobjectarray"></a>COlePropertyPage::GetObjectArray  
 Возвращает массив объектов, изменяется на странице свойств.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Параметры  
 `pnObjects`  
 Указатель на длинное целое без знака, который получит количество объектов, изменяется на странице.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на массив `IDispatch` указатели, которые используются для доступа к свойствам каждого элемента управления на странице свойств. Вызывающий объект не должен освободить эти указатели на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Каждый объект страницы свойств содержит массив указателей на `IDispatch` интерфейсов объектов изменяется на странице. Эта функция задает его `pnObjects` аргумента для числа элементов в этом массиве и возвращает указатель на первый элемент массива.  
  
##  <a name="getpagesite"></a>COlePropertyPage::GetPageSite  
 Возвращает указатель на странице свойств `IPropertyPageSite` интерфейса.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на странице свойств `IPropertyPageSite` интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Элементы управления и контейнеры работают совместно, так что пользователи могут просматривать и редактировать свойства элемента управления. Элемент управления содержит страницы свойств, каждый из которых является OLE-объект, позволяющий пользователю изменять набор связанных свойств. Контейнер предоставляет свойства кадра, который отображает страницы свойств. Для каждой страницы рамка свойства предоставляет страницу сайта, которая поддерживает `IPropertyPageSite` интерфейса.  
  
##  <a name="ignoreapply"></a>COlePropertyPage::IgnoreApply  
 Определяет, какие элементы управления, не включайте кнопки "Применить".  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления пропускаются.  
  
### <a name="remarks"></a>Примечания  
 Только в том случае, если были изменены значения свойств элементов управления страницы, становится доступной кнопка Применить страницу свойств. Эту функцию можно используйте для выбора элементов управления, которые не вызывают кнопки "Применить" включен, при изменении их значений.  
  
##  <a name="ismodified"></a>COlePropertyPage::IsModified  
 Определяет, изменилось ли все значения на странице свойств.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если был изменен на странице свойств.  
  
##  <a name="oneditproperty"></a>COlePropertyPage::OnEditProperty  
 Платформа вызывает эту функцию при определенных свойств для редактирования.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации редактируемого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает **FALSE**. Переопределения этой функции должны возвращать **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Его можно переопределить, чтобы перевести фокус на соответствующий элемент управления на странице. Реализация по умолчанию не выполняет никаких действий и возвращает **FALSE**.  
  
##  <a name="onhelp"></a>COlePropertyPage::OnHelp  
 Платформа вызывает эту функцию при запросе справки в Интернете.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszHelpDir*  
 Каталог, содержащий файл справки на странице свойств.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Его необходимо переопределите в том случае, если страницы свойств необходимо выполнить любое специальное действие, когда пользователь обращается к справке. Реализация по умолчанию не выполняет никаких действий и возвращает **FALSE**, которое указывает платформе вызывать WinHelp.  
  
##  <a name="oninitdialog"></a>COlePropertyPage::OnInitDialog  
 Платформа вызывает эту функцию при инициализации диалогового окна страницы свойств.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Его необходимо переопределите в том случае, если любое специальное действие является обязательным при инициализации диалогового окна. Реализация по умолчанию вызывает `CDialog::OnInitDialog` и возвращает **FALSE**.  
  
##  <a name="onobjectschanged"></a>COlePropertyPage::OnObjectsChanged  
 Вызывается инфраструктурой при выборе другого элемента управления OLE, с помощью новых свойств.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Примечания  
 При просмотре свойств элемента управления OLE, в среде разработчика, немодальное диалоговое окно используется для отображения страницы свойств. Если выбран другой элемент управления, другой набор страниц свойств должны отображаться новый набор свойств. Платформа вызывает эту функцию для уведомления на странице изменения.  
  
 Переопределите эту функцию для получения уведомлений данного действия и выполнить специальные действия.  
  
##  <a name="onsetpagesite"></a>COlePropertyPage::OnSetPageSite  
 Платформа вызывает эту функцию, когда рамка свойства предоставляет страницу свойств страницы сайта.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию загружает заголовок страницы и пытается определить размер страницы из ресурса диалогового окна. Переопределить эту функцию, если на странице свойств требует никаких дальнейших действий; переопределение должно вызывать реализацию базового класса.  
  
##  <a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus  
 Изменяет состояние элемента управления страниц свойств.  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Содержит идентификатор элемента управления страниц свойств.  
  
 `bDirty`  
 Указывает, был ли изменен поля страницы свойств. Значение **TRUE** Если поля были изменены, **FALSE** , если он не был изменен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,**, если указанный элемент управления установлен; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если состояние элемента управления страницы свойств «грязные» при закрытии страницы свойств или выбирается «применить», будет обновлено свойство элемента управления с соответствующим значением.  
  
##  <a name="setdialogresource"></a>COlePropertyPage::SetDialogResource  
 Задает ресурс диалогового окна страницы свойств.  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>Параметры  
 *hDialog*  
 Дескриптор ресурса диалогового окна страницы свойств.  
  
##  <a name="sethelpinfo"></a>COlePropertyPage::SetHelpInfo  
 Задает подсказку, имя файла справки и контекст справки для страницы свойств.  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszDocString*  
 Строка, содержащая краткие справочные сведения для отображения в строке состояния или в другом месте.  
  
 `lpszHelpFile`  
 Имя файла справки на странице свойств.  
  
 *dwHelpContext*  
 Контекст справки для страницы свойств.  
  
##  <a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag  
 Указывает, изменил ли пользователь на странице свойств.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Задает новое значение измененного флага страницы свойств.  
  
##  <a name="setpagename"></a>COlePropertyPage::SetPageName  
 Задает имя страницы свойств, которое фрейм свойства обычно будет отображаться на вкладке страницы.  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPageName*  
 Указатель на строку, содержащую имя страницы свойств.  
  
## <a name="see-also"></a>См. также  
 [Образец CIRC3 MFC](../../visual-cpp-samples.md)   
 [Пример MFC TESTHELP](../../visual-cpp-samples.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

