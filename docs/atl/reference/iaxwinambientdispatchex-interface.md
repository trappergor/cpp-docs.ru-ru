---
title: "Интерфейс IAxWinAmbientDispatchEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- No header/ATL::IAxWinAmbientDispatchEx
- No header/ATL::SetAmbientDispatch
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 915514a021aa89b751a49a34cb53b693b9fd0c45
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinambientdispatchex-interface"></a>Интерфейс IAxWinAmbientDispatchEx
Этот интерфейс реализует дополнительные свойства окружения для размещенного элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|Этот метод вызывается, чтобы дополнить интерфейс внешнее свойство по умолчанию с помощью интерфейса пользователя.|  
  
## <a name="remarks"></a>Примечания  
 Включайте этот интерфейс в приложениях ATL, статически компонуемые с ATL и узлов элементов управления ActiveX, особенно элементы управления ActiveX, имеющих свойства окружающей среды. Включая этот интерфейс не будет создавать это утверждение: «Вы забыли передать идентификатор LIBID CComModule::Init»  
  
 Этот интерфейс предоставляется элементом управления ActiveX ATL размещение объектов. Производный от [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` добавляет метод, который позволяет расширять внешнее свойство интерфейса, предоставляемые ATL с собственным.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) попытается загрузить тип сведения о `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, содержащий код.  
  
 При связывании ATL90.dll, **AXHost** загружает сведения о типе из библиотеки типов в библиотеке DLL.  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) для получения дополнительных сведений.  
  
## <a name="requirements"></a>Требования  
 Определение этот интерфейс доступен в несколько форм, как показано в следующей таблице.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|atliface.IDL|  
|Библиотека типов|ATL.dll|  
|C++|насколько (также входит в ATLBase.h)|  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Этот метод вызывается, чтобы дополнить интерфейс внешнее свойство по умолчанию с помощью интерфейса пользователя.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 *pDispatch*  
 Указатель на интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Когда `SetAmbientDispatch` вызывается с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любого свойства или методы, которые просили размещенным элементом управления, если эти свойства еще не заданы [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)

