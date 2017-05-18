---
title: "Интерфейс IAxWinAmbientDispatch | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatch
- No header/ATL::IAxWinAmbientDispatch
- No header/ATL::get_AllowContextMenu
- No header/ATL::get_AllowShowUI
- No header/ATL::get_AllowWindowlessActivation
- No header/ATL::get_BackColor
- No header/ATL::get_DisplayAsDefault
- No header/ATL::get_DocHostDoubleClickFlags
- No header/ATL::get_DocHostFlags
- No header/ATL::get_Font
- No header/ATL::get_ForeColor
- No header/ATL::get_LocaleID
- No header/ATL::get_MessageReflect
- No header/ATL::get_OptionKeyPath
- No header/ATL::get_ShowGrabHandles
- No header/ATL::get_ShowHatching
- No header/ATL::get_UserMode
- No header/ATL::put_AllowContextMenu
- No header/ATL::put_AllowShowUI
- No header/ATL::put_AllowWindowlessActivation
- No header/ATL::put_BackColor
- No header/ATL::put_DisplayAsDefault
- No header/ATL::put_DocHostDoubleClickFlags
- No header/ATL::put_DocHostFlags
- No header/ATL::put_Font
- No header/ATL::put_ForeColor
- No header/ATL::put_LocaleID
- No header/ATL::put_MessageReflect
- No header/ATL::put_OptionKeyPath
- No header/ATL::put_UserMode
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 3dd34ffec68e4503aebe7b8d0e72ec1f711dca03
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="iaxwinambientdispatch-interface"></a>Интерфейс IAxWinAmbientDispatch
Этот интерфейс предоставляет методы для указания характеристики размещенного элемента управления или контейнера.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|**Контекстное меню** свойство указывает, разрешены ли размещенный элемент управления для отображения контекстного меню.|  
|[get_AllowShowUI](#get_allowshowui)|**AllowShowUI** свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|**AllowWindowlessActivation** свойство указывает, будет ли контейнер давать активации без окна.|  
|[get_BackColor](#get_backcolor)|`BackColor` Свойство определяет цвет фона окружения контейнера.|  
|[get_DisplayAsDefault](#get_displayasdefault)|**DisplayAsDefault** — это внешнее свойство, которое позволяет элементу управления проверить, является ли элемент управления по умолчанию.|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|**DocHostDoubleClickFlags** свойство указывает операции, которое должно быть выполнено в ответ на двойным щелчком.|  
|[get_DocHostFlags](#get_dochostflags)|**DocHostFlags** свойство указывает возможностями интерфейса объекта узла.|  
|[get_Font](#get_font)|**Шрифта** свойство указывает шрифт окружения контейнера.|  
|[get_ForeColor](#get_forecolor)|`ForeColor` Свойство определяет цвет переднего плана окружения контейнера.|  
|[get_LocaleID](#get_localeid)|**LocaleID** свойство задает идентификатор языкового стандарта окружения контейнера.|  
|[get_MessageReflect](#get_messagereflect)|**MessageReflect** внешнее свойство указывает ли контейнер будет отражать сообщений для размещенного элемента управления.|  
|[get_OptionKeyPath](#get_optionkeypath)|**OptionKeyPath** свойство указывает путь к разделу реестра для параметров пользователя.|  
|[get_ShowGrabHandles](#get_showgrabhandles)|**ShowGrabHandles** внешнее свойство позволяет элементу управления узнать, если он должен рисования самого себя с ручки.|  
|[get_ShowHatching](#get_showhatching)|**ShowHatching** внешнее свойство позволяет узнать, если его следует нарисовать сам hatched элементу управления.|  
|[get_UserMode](#get_usermode)|**UserMode** свойство определяет режим окружения пользователя контейнера.|  
|[put_AllowContextMenu](#put_allowcontextmenu)|**Контекстное меню** свойство указывает, разрешены ли размещенный элемент управления для отображения контекстного меню.|  
|[put_AllowShowUI](#put_allowshowui)|**AllowShowUI** свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|**AllowWindowlessActivation** свойство указывает, будет ли контейнер давать активации без окна.|  
|[put_BackColor](#put_backcolor)|`BackColor` Свойство определяет цвет фона окружения контейнера.|  
|[put_DisplayAsDefault](#put_displayasdefault)|**DisplayAsDefault** — это внешнее свойство, которое позволяет элементу управления проверить, является ли элемент управления по умолчанию.|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|**DocHostDoubleClickFlags** свойство указывает операции, которое должно быть выполнено в ответ на двойным щелчком.|  
|[put_DocHostFlags](#put_dochostflags)|**DocHostFlags** свойство указывает возможностями интерфейса объекта узла.|  
|[put_Font](#put_font)|**Шрифта** свойство указывает шрифт окружения контейнера.|  
|[put_ForeColor](#put_forecolor)|`ForeColor` Свойство определяет цвет переднего плана окружения контейнера.|  
|[put_LocaleID](#put_localeid)|**LocaleID** свойство задает идентификатор языкового стандарта окружения контейнера.|  
|[put_MessageReflect](#put_messagereflect)|**MessageReflect** внешнее свойство указывает ли контейнер будет отражать сообщений для размещенного элемента управления.|  
|[put_OptionKeyPath](#put_optionkeypath)|**OptionKeyPath** свойство указывает путь к разделу реестра для параметров пользователя.|  
|[put_UserMode](#put_usermode)|**UserMode** свойство определяет режим окружения пользователя контейнера.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляется элементом управления ActiveX ATL размещение объектов. Вызовите методы для этого интерфейса для задания свойства окружения для размещенного элемента управления или укажите другие аспекты поведения контейнера. Чтобы дополнить свойств, предоставляемых `IAxWinAmbientDispatch`, используйте [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) будет пытаться загрузить сведения о типе о `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, который содержит код.  
  
 При связывании ATL90.dll, **AXHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) для получения дополнительных сведений.  
  
## <a name="requirements"></a>Требования  
 Определение этот интерфейс доступен в несколько форм, как показано в следующей таблице.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|atliface.IDL|  
|Библиотека типов|ATL.dll|  
|C++|см (также входит в состав ATLBase.h)|  
  
##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu  
 **Контекстное меню** свойство указывает, разрешены ли размещенный элемент управления для отображения контекстного меню.  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>Параметры  
 *pbAllowContextMenu*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI  
 **AllowShowUI** свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>Параметры  
 *pbAllowShowUI*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **VARIANT_FALSE** как значение по умолчанию этого свойства.  
  
##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 **AllowWindowlessActivation** свойство указывает, будет ли контейнер давать активации без окна.  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>Параметры  
 *pbAllowWindowless*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor  
 `BackColor` Свойство определяет цвет фона окружения контейнера.  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>Параметры  
 *pclrBackground*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **COLOR_BTNFACE** или **COLOR_WINDOW** как значение по умолчанию этого свойства (в зависимости от родительского элемента главного окна является ли диалоговое окно или нет).  
  
##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault** — это внешнее свойство, которое позволяет элементу управления проверить, является ли элемент управления по умолчанию.  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *pbDisplayAsDefault*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **VARIANT_FALSE** как значение по умолчанию этого свойства.  
  
##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags** свойство указывает операции, которое должно быть выполнено в ответ на двойным щелчком.  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwDocHostDoubleClickFlags*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **DOCHOSTUIDBLCLK_DEFAULT** как значение по умолчанию этого свойства.  
  
##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags  
 **DocHostFlags** свойство указывает возможностями интерфейса объекта узла.  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwDocHostFlags*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **DOCHOSTUIFLAG_NO3DBORDER** как значение по умолчанию этого свойства.  
  
##  <a name="get_font"></a>IAxWinAmbientDispatch::get_Font  
 **Шрифта** свойство указывает шрифт окружения контейнера.  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>Параметры  
 `pFont`  
 [out] Адрес **IFontDisp** указатель на интерфейс, используемый для получения текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт как значение по умолчанию этого свойства.  
  
##  <a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor` Свойство определяет цвет переднего плана окружения контейнера.  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>Параметры  
 *pclrForeground*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует системный цвет окон как значение по умолчанию этого свойства.  
  
##  <a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID  
 **LocaleID** свойство задает идентификатор языкового стандарта окружения контейнера.  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>Параметры  
 *plcidLocaleID*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует языковой стандарт пользователя по умолчанию как значение по умолчанию этого свойства.  
  
 С помощью этого метода можно обнаружить внешнюю локальный идентификатор, то есть LocaleID программы управления используется в. Если известно значение идентификатора языка, можно вызвать код для загрузки заголовков языковому стандарту, текст сообщения об ошибке, и т. д из файла ресурсов или вспомогательной библиотеки DLL.  
  
##  <a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect  
 **MessageReflect** внешнее свойство указывает ли контейнер будет отражать сообщений для размещенного элемента управления.  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>Параметры  
 *pbMessageReflect*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath  
 **OptionKeyPath** свойство указывает путь к разделу реестра для параметров пользователя.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Параметры  
 *pbstrOptionKeyPath*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles  
 **ShowGrabHandles** внешнее свойство позволяет элементу управления узнать, если он должен рисования самого себя с ручки.  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>Параметры  
 *pbShowGrabHandles*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 ATL узла объекта реализация всегда возвращает **VARIANT_FALSE** в качестве значения этого свойства.  
  
##  <a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching  
 **ShowHatching** внешнее свойство позволяет узнать, если его следует нарисовать сам hatched элементу управления.  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>Параметры  
 *pbShowHatching*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 ATL узла объекта реализация всегда возвращает **VARIANT_FALSE** в качестве значения этого свойства.  
  
##  <a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode  
 **UserMode** свойство определяет режим окружения пользователя контейнера.  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>Параметры  
 *pbUserMode*  
 [out] Адрес переменной, чтобы получить текущее значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu  
 **Контекстное меню** свойство указывает, разрешены ли размещенный элемент управления для отображения контекстного меню.  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>Параметры  
 *bAllowContextMenu*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI  
 **AllowShowUI** свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>Параметры  
 *bAllowShowUI*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **VARIANT_FALSE** как значение по умолчанию этого свойства.  
  
##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 **AllowWindowlessActivation** свойство указывает, будет ли контейнер давать активации без окна.  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>Параметры  
 *bAllowWindowless*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor  
 `BackColor` Свойство определяет цвет фона окружения контейнера.  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>Параметры  
 *clrBackground*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **COLOR_BTNFACE** или **COLOR_WINDOW** как значение по умолчанию этого свойства (в зависимости от родительского элемента главного окна является ли диалоговое окно или нет).  
  
##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault** — это внешнее свойство, которое позволяет элементу управления проверить, является ли элемент управления по умолчанию.  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `bDisplayAsDefault`  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **VARIANT_FALSE** как значение по умолчанию этого свойства.  
  
##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags** свойство указывает операции, которое должно быть выполнено в ответ на двойным щелчком.  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDocHostDoubleClickFlags*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **DOCHOSTUIDBLCLK_DEFAULT** как значение по умолчанию этого свойства.  
  
##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags  
 **DocHostFlags** свойство указывает возможностями интерфейса объекта узла.  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDocHostFlags*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует **DOCHOSTUIFLAG_NO3DBORDER** как значение по умолчанию этого свойства.  
  
##  <a name="put_font"></a>IAxWinAmbientDispatch::put_Font  
 **Шрифта** свойство указывает шрифт окружения контейнера.  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 `pFont`  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт как значение по умолчанию этого свойства.  
  
##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor` Свойство определяет цвет переднего плана окружения контейнера.  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>Параметры  
 *clrForeground*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует системный цвет окон как значение по умолчанию этого свойства.  
  
##  <a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID  
 **LocaleID** свойство задает идентификатор языкового стандарта окружения контейнера.  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>Параметры  
 *lcidLocaleID*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует языковой стандарт пользователя по умолчанию как значение по умолчанию этого свойства.  
  
##  <a name="put_messagereflect"></a>IAxWinAmbientDispatch::put_MessageReflect  
 **MessageReflect** внешнее свойство указывает ли контейнер будет отражать сообщений для размещенного элемента управления.  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>Параметры  
 `bMessageReflect`  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath  
 **OptionKeyPath** свойство указывает путь к разделу реестра для параметров пользователя.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrOptionKeyPath*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode  
 **UserMode** свойство определяет режим окружения пользователя контейнера.  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>Параметры  
 `bUserMode`  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Реализация узла объекта ATL использует `VARIANT_TRUE` как значение по умолчанию этого свойства.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [Интерфейс IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)










