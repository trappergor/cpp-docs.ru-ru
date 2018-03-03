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
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fd212417a00335bfc02699cf5e38eeacc6451ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iaxwinambientdispatchex-interface"></a>Интерфейс IAxWinAmbientDispatchEx
Этот интерфейс реализует дополнительные свойства окружения для размещенного элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|Этот метод вызывается для дополнения интерфейс внешнее свойство по умолчанию с интерфейсом, определяемой пользователем.|  
  
## <a name="remarks"></a>Примечания  
 Включите этот интерфейс в приложениях ATL, статически компонуемые с ATL и узла элементы управления ActiveX, особенно элементы управления ActiveX, имеют свойства окружения. Включая этот интерфейс не создаст это утверждение: «Возможно, следует передать идентификатор LIBID CComModule::Init»  
  
 Этот интерфейс предоставляется элементом управления ActiveX ATL размещение объектов. Производное от [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` добавляет метод, который позволяет расширять внешнее свойство интерфейса, предоставляемые ATL с собственным.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) будет пытаться загрузить сведения о типе о `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, который содержит код.  
  
 При связывании ATL90.dll, **AXHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) для получения дополнительных сведений.  
  
## <a name="requirements"></a>Требования  
 Определение этот интерфейс доступен в несколько форм, как показано в следующей таблице.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|atliface.IDL|  
|Библиотеки типов|ATL.dll|  
|C++|см (также входит в состав ATLBase.h)|  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Этот метод вызывается для дополнения интерфейс внешнее свойство по умолчанию с интерфейсом, определяемой пользователем.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 *pDispatch*  
 Указатель на новый интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Когда `SetAmbientDispatch` вызывается с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любого свойства или методы, запрос для размещенным элементом управления, если эти свойства еще не заданы [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)
