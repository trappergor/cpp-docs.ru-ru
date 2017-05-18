---
title: "Интерфейс IAxWinHostWindowLic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- No header/ATL::IAxWinHostWindowLic
- No header/ATL::CreateControlLic
- No header/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 01ff8a7205418583606cbfdb1c028d7097501e00
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindowlic-interface"></a>Интерфейс IAxWinHostWindowLic
Этот интерфейс предоставляет методы для управления лицензированный элемент управления и его объект узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления и присоединяет его к объекту главного приложения.|  
|[CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления, присоединяет его к объекту главного приложения и при необходимости устанавливает обработчик события.|  
  
## <a name="remarks"></a>Примечания  
 `IAxWinHostWindowLic`наследует от [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, поддерживающие создание Лицензированные элементы управления.  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, использующего члены этого интерфейса.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Насколько (также входит в ATLBase.h)|  
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 Создает лицензированный элемент управления, инициализирует его и размещает в окне, идентифицируемый `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrLic`  
 [in] BSTR, содержащее ключ лицензии для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) описание оставшиеся параметры и возвращаемые значения.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx  
 Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне аналогично [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrLic`  
 [in] BSTR, содержащее ключ лицензии для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) описание оставшиеся параметры и возвращаемые значения.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементы управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLicEx`.










