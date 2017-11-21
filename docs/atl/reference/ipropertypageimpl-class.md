---
title: "Класс IPropertyPageImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
dev_langs: C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 345379de254338fa8d344ee21b022439380d9851
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ipropertypageimpl-class"></a>Класс IPropertyPageImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class IPropertyPageImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPropertyPageImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPropertyPageImpl::Activate](#activate)|Создание диалогового окна для страницы свойств.|  
|[IPropertyPageImpl::Apply](#apply)|Применяется к базовые объекты, заданные с помощью текущих значений свойств страницы `SetObjects`. Возвращает реализацию ATL `S_OK`.|  
|[IPropertyPageImpl::Deactivate](#deactivate)|Уничтожает окно, созданных с помощью **активировать**.|  
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Извлекает сведения о странице свойств.|  
|[IPropertyPageImpl::Help](#help)|Вызывает справку Windows для страницы свойств.|  
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Указывает, изменилось ли на странице свойств, так как он был активирован.|  
|[IPropertyPageImpl::Move](#move)|Размещает и размера страницы диалоговое окно «Свойства».|  
|[IPropertyPageImpl::SetDirty](#setdirty)|Флаги состояния на странице свойств как измененные или без изменений.|  
|[IPropertyPageImpl::SetObjects](#setobjects)|Предоставляет массив **IUnknown** указатели для объектов, связанных со страницей свойств. Эти объекты получают текущие значения свойств страницы путем вызова **применить**.|  
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Содержит страницу свойств с `IPropertyPageSite` указатель, по которому страницы свойств взаимодействует с фрейм свойства.|  
|[IPropertyPageImpl::Show](#show)|Делает диалоговое окно страницы свойств видимым или невидимым.|  
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Обработка указанного нажатие клавиши.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Указывает, изменилось ли состояние страницы свойств.|  
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Сохраняет идентификатор ресурса, связанного со строкой текста описания на странице свойств.|  
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Сохраняет идентификатор контекста для раздела справки, связанный со страницей свойств.|  
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Сохраняет идентификатор ресурса, связанного с именем файл справки с описанием страницы свойств.|  
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Сохраняет идентификатор ресурса, связанного со строкой текста, появляется на вкладке страницы свойств.|  
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Хранит количество объектов, связанных со страницей свойств.|  
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Указывает `IPropertyPageSite` интерфейса, через который на странице свойств взаимодействует с фрейм свойства.|  
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Указывает массив **IUnknown** указатели на объекты, связанные со страницей свойств.|  
|[IPropertyPageImpl::m_size](#m_size)|Сохраняет высоту и ширину в диалоговом окне страницы свойств в пикселях.|  
  
## <a name="remarks"></a>Примечания  
 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) интерфейс позволяет управлять конкретную страницу свойств в окне свойств объекта. Класс `IPropertyPageImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="activate"></a>IPropertyPageImpl::Activate  
 Создание диалогового окна для страницы свойств.  
  
```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию диалоговое окно всегда является немодальным независимо от значения *bModal* параметра.  
  
 В разделе [IPropertyPage::Activate](http://msdn.microsoft.com/library/windows/desktop/ms682250) в Windows SDK.  
  
##  <a name="apply"></a>IPropertyPageImpl::Apply  
 Применяется к базовые объекты, заданные с помощью текущих значений свойств страницы `SetObjects`.  
  
```
HRESULT Apply();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::Apply](http://msdn.microsoft.com/library/windows/desktop/ms691284) в Windows SDK.  
  
##  <a name="deactivate"></a>IPropertyPageImpl::Deactivate  
 Уничтожает созданных с помощью диалогового окна [активировать](#activate).  
  
```
HRESULT Deactivate();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms682504) в Windows SDK.  
  
##  <a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo  
 Заполняет *pPageInfo* структуры, где данные хранятся в элементах данных.  
  
```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Примечания  
 `GetPageInfo`Загружает строковые ресурсы, связанные с [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile), и [m_dwTitle](#m_dwtitle).  
  
 В разделе [IPropertyPage::GetPageInfo](http://msdn.microsoft.com/library/windows/desktop/ms680714) в Windows SDK.  
  
##  <a name="help"></a>IPropertyPageImpl::Help  
 Вызывает справку Windows для страницы свойств.  
  
```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::Help](http://msdn.microsoft.com/library/windows/desktop/ms691504) в Windows SDK.  
  
##  <a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl  
 Конструктор.  
  
```
IPropertyPageImpl();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует все члены данных.  
  
##  <a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty  
 Указывает, изменилось ли на странице свойств, так как он был активирован.  
  
```
HRESULT IsPageDirty(void);
```  
  
### <a name="remarks"></a>Примечания  
 `IsPageDirty`Возвращает `S_OK` Если страница была изменена, так как он был активирован.  
  
##  <a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty  
 Указывает, изменилось ли состояние страницы свойств.  
  
```
BOOL m_bDirty;
```  
  
##  <a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects  
 Хранит количество объектов, связанных со страницей свойств.  
  
```
ULONG m_nObjects;
```  
  
##  <a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext  
 Сохраняет идентификатор контекста для раздела справки, связанный со страницей свойств.  
  
```
DWORD m_dwHelpContext;
```  
  
##  <a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString  
 Сохраняет идентификатор ресурса, связанного со строкой текста описания на странице свойств.  
  
```
UINT m_dwDocString;
```  
  
##  <a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile  
 Сохраняет идентификатор ресурса, связанного с именем файл справки с описанием страницы свойств.  
  
```
UINT m_dwHelpFile;
```  
  
##  <a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle  
 Сохраняет идентификатор ресурса, связанного со строкой текста, появляется на вкладке страницы свойств.  
  
```
UINT m_dwTitle;
```  
  
##  <a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite  
 Указывает на [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) интерфейс, через который на странице свойств взаимодействует с фрейм свойства.  
  
```
IPropertyPageSite* m_pPageSite;
```  
  
##  <a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk  
 Указывает массив **IUnknown** указатели на объекты, связанные со страницей свойств.  
  
```
IUnknown** m_ppUnk;
```  
  
##  <a name="m_size"></a>IPropertyPageImpl::m_size  
 Сохраняет высоту и ширину в диалоговом окне страницы свойств в пикселях.  
  
```
SIZE m_size;
```  
  
##  <a name="move"></a>IPropertyPageImpl::Move  
 Размещает и размера страницы диалоговое окно «Свойства».  
  
```
HRESULT Move(LPCRECT pRect);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::Move](http://msdn.microsoft.com/library/windows/desktop/ms680118) в Windows SDK.  
  
##  <a name="setdirty"></a>IPropertyPageImpl::SetDirty  
 Флаги состояния на странице свойств как измененные или изменяется в зависимости от значения `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Параметры  
 `bDirty`  
 [in] Если **TRUE**, состояние страницы свойство помечается как измененный. В противном случае она помечена как без изменений.  
  
### <a name="remarks"></a>Примечания  
 При необходимости `SetDirty` информирует кадра, который был изменен на странице свойств.  
  
##  <a name="setobjects"></a>IPropertyPageImpl::SetObjects  
 Предоставляет массив **IUnknown** указатели для объектов, связанных со страницей свойств.  
  
```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::SetObjects](http://msdn.microsoft.com/library/windows/desktop/ms678529) в Windows SDK.  
  
##  <a name="setpagesite"></a>IPropertyPageImpl::SetPageSite  
 Содержит страницу свойств с [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) указателя, через который на странице свойств взаимодействует с фрейм свойства.  
  
```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::SetPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690413) в Windows SDK.  
  
##  <a name="show"></a>IPropertyPageImpl::Show  
 Делает диалоговое окно страницы свойств видимым или невидимым.  
  
```
HRESULT Show(UINT nCmdShow);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::Show](http://msdn.microsoft.com/library/windows/desktop/ms694467) в Windows SDK.  
  
##  <a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator  
 Обрабатывает нажатие клавиши, указанный в `pMsg`.  
  
```
HRESULT TranslateAccelerator(MSG* pMsg);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms686603) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)   
 [Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
