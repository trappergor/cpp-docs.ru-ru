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
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 6d0e8c0a8ec941c7a7980b81fcd95df08298ea28
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
|[CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления и прикрепляет его к объекту узла.|  
|[CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления и прикрепляет его к объекту узла при необходимости устанавливает обработчик события.|  
  
## <a name="remarks"></a>Примечания  
 `IAxWinHostWindowLic`наследует от [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, поддерживающие создание Лицензированные элементы управления.  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий члены этого интерфейса.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|См (также входит в состав ATLBase.h)|  
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 Создает лицензированный элемент управления, инициализирует его и размещает в окна, обозначенную `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrLic`  
 [in] BSTR, содержащий ключ лицензии для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) описание оставшиеся параметры и возвращаемые значения.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLic`.  
  
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
 [in] BSTR, содержащий ключ лицензии для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) описание оставшиеся параметры и возвращаемые значения.  
  
### <a name="example"></a>Пример  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLicEx`.










