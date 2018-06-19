---
title: Интерфейс IAxWinHostWindowLic | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41b4d7891d1bb00f4ee689477d1056dbf2bf28cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362844"
---
# <a name="iaxwinhostwindowlic-interface"></a>Интерфейс IAxWinHostWindowLic
Этот интерфейс предоставляет методы для управления лицензированный элемент управления и его объект узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления и прикрепляет его к объекту узла.|  
|[CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления и прикрепляет его к объекту узла при необходимости устанавливает обработчик события.|  
  
## <a name="remarks"></a>Примечания  
 `IAxWinHostWindowLic` наследует от [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, поддерживающие создание Лицензированные элементы управления.  
  
 В разделе [размещение AXHost с использованием ATL ActiveX элементов управления](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий члены этого интерфейса.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|См (также входит в состав ATLBase.h)|  
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
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
  
##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx  
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









