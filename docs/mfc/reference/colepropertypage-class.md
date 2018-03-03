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
- AFXCTL/COlePropertyPage::OVERWRITEApply
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
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cac788f0e7f691f28a6751d15971f117d753428c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colepropertypage-class"></a>Класс COlePropertyPage
Используется для отображения свойств пользовательского элемента управления в графическом интерфейсе подобно диалоговому окну.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Создает объект `COlePropertyPage`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Указывает, ли пользователь изменил значение в элементе управления.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Возвращает массив объектов, изменяется на странице свойств.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Возвращает указатель на страницу свойств `IPropertyPageSite` интерфейса.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Определяет, какие элементы управления, не включайте кнопки «Применить».|  
|[COlePropertyPage::IsModified](#ismodified)|Указывает, изменил ли пользователь со страницы свойств.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Вызывается платформой, когда пользователь редактирует свойство.|  
|[COlePropertyPage::OnHelp](#onhelp)|Вызывается платформой, когда пользователь вызывает справку.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Вызывается платформой при инициализации страницы свойств.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Вызывается платформой, когда выбран другой элемент управления OLE с новыми свойствами.|  
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Вызывается платформой, когда фрейм свойства предоставляет страничный сайт.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Задает флаг, указывающий, является ли пользователь изменил значение в элементе управления.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Задает ресурс диалогового окна страницы свойств.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Задает краткое справку на странице свойств, имя его файла справки и его контекст справки.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающий, изменил ли пользователь со страницы свойств.|  
|[COlePropertyPage::SetPageName](#setpagename)|Задает имя страницы свойств (заголовок).|  
  
## <a name="remarks"></a>Примечания  
 Например страницы свойств может включать элемент управления редактирования, пользователь может просматривать и изменять свойство заголовка элемента управления.  
  
 Каждое свойство пользовательских или стандартных элементов управления может иметь управления диалогового окна, который позволяет пользователю элемента управления для просмотра текущего значения свойства и при необходимости измените это значение.  
  
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
 При реализации подкласс `COlePropertyPage`, следует использовать конструктор подкласса в `COlePropertyPage` конструктор для идентификации ресурса шаблона диалогового окна на которых основаны на странице свойств и строкового ресурса, содержащего его заголовок.  
  
##  <a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus  
 Определяет, ли пользователь изменил значение свойства элемента управления страницы с идентификатором указанного ресурса.  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления страницы свойств ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если значение элемента управления был изменен; в противном случае **FALSE**.  
  
##  <a name="getobjectarray"></a>COlePropertyPage::GetObjectArray  
 Возвращает массив объектов, изменяется на странице свойств.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Параметры  
 `pnObjects`  
 Указатель на длинное целое без знака, который получит число объектов, изменяется на странице.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на массив `IDispatch` указатели, которые используются для доступа к свойствам каждого элемента управления на странице свойств. Вызывающий объект не должен освободить эти указатели на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Каждый объект страницы свойств поддерживает массив указателей на `IDispatch` интерфейсы объектов редактируемой страницы. Эта функция задает его `pnObjects` аргумента для числа элементов в этом массиве и возвращает указатель на первый элемент массива.  
  
##  <a name="getpagesite"></a>COlePropertyPage::GetPageSite  
 Возвращает указатель на странице свойств `IPropertyPageSite` интерфейса.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на странице свойств `IPropertyPageSite` интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Элементы управления и контейнеры действуют совместно, чтобы пользователи могут просматривать и изменять свойства элемента управления. Элемент управления содержит страницы свойств, каждый из которых является OLE-объект, позволяющий пользователю изменять набор связанных свойств. Контейнер предоставляет свойства фрейма, отображение страниц свойств. Для каждой страницы фрейм свойства предоставляет страницы сайта, которая поддерживает `IPropertyPageSite` интерфейса.  
  
##  <a name="ignoreapply"></a>COlePropertyPage::IgnoreApply  
 Определяет, какие элементы управления, не включайте кнопки «Применить».  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления пропускаются.  
  
### <a name="remarks"></a>Примечания  
 Кнопки "Применить" на странице свойств включен только в том случае, если значения элементов управления страницы свойств были изменены. Эта функция используется для выбора элементов управления, которые не вызывают кнопки «Применить» будет включена после изменения их значений.  
  
##  <a name="ismodified"></a>COlePropertyPage::IsModified  
 Определяет, изменилось ли все значения на странице свойств.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если был изменен на странице свойств.  
  
##  <a name="oneditproperty"></a>COlePropertyPage::OnEditProperty  
 Платформа вызывает эту функцию при определенное свойство для редактирования.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации редактируемого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает **FALSE**. Переопределения этой функции должны возвращать **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Его можно переопределить, чтобы установить фокус на соответствующий элемент управления на странице. Реализация по умолчанию не выполняет никаких действий и возвращает **FALSE**.  
  
##  <a name="onhelp"></a>COlePropertyPage::OnHelp  
 Платформа вызывает эту функцию, когда пользователь запрашивает справку в Интернете.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszHelpDir*  
 Каталог, содержащий файл справки на странице свойств.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Его необходимо переопределите в том случае, если на странице свойств необходимо выполнить любое специальное действие, когда пользователь обращается к справке. Реализация по умолчанию не выполняет никаких действий и возвращает **FALSE**, который дает платформе вызывать WinHelp.  
  
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
 Вызывается платформой, когда выбран другой элемент управления OLE с новыми свойствами.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Примечания  
 При просмотре свойств элемента управления OLE в среде разработчика, немодальное диалоговое окно используется для отображения страницы его свойств. Если выбран другой элемент управления, другой набор страницы свойств должны отображаться для нового набора свойств. Платформа вызывает эту функцию, чтобы уведомить изменения страницы свойств.  
  
 Переопределите эту функцию для получения уведомлений о это действие и выполнения каких-либо специальных действий.  
  
##  <a name="onsetpagesite"></a>COlePropertyPage::OnSetPageSite  
 Платформа вызывает эту функцию, когда фрейм свойства предоставляет сайта страницы на странице свойств.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию загружает заголовка страницы и пытается определить размер страницы из ресурса диалогового окна. Переопределить эту функцию, если на странице свойств требует никаких дальнейших действий; переопределение должно вызывать реализацию базового класса.  
  
##  <a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus  
 Изменяет состояние элемента управления страницы свойств.  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Содержит идентификатор элемента управления страницы свойств.  
  
 `bDirty`  
 Указывает, был ли изменен поля страницы свойств. Значение **TRUE** Если поле было изменено, **FALSE** , если он не был изменен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,**, если указанный элемент управления установлен; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если состояние элемента управления страницы свойств "грязного" при закрытии страницы свойств или кнопки «Применить» выбран, свойство элемента управления будет обновляться с соответствующим значением.  
  
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
 Строка, содержащая краткие справочные сведения для отображения в строке состояния или в другое место.  
  
 `lpszHelpFile`  
 Имя файла справки на странице свойств.  
  
 *dwHelpContext*  
 Контекст справки для страницы свойств.  
  
##  <a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag  
 Указывает, изменил ли пользователь со страницы свойств.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Указывает новое значение для измененного флага на странице свойств.  
  
##  <a name="setpagename"></a>COlePropertyPage::SetPageName  
 Задает имя страницы свойств, которое фрейм свойства обычно будет отображаться на вкладке этой страницы.  
  
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
 [Класс CDialog](../../mfc/reference/cdialog-class.md)
