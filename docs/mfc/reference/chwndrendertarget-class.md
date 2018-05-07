---
title: Класс CHwndRenderTarget | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d83765309f6df860b190d3ea2114e7e0fd35724
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="chwndrendertarget-class"></a>Класс CHwndRenderTarget
Программа-оболочка для ID2D1HwndRenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Создает объект CHwndRenderTarget из HWND.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|Присоединяет существующую отрисовки интерфейса целевой объект|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Указывает, является ли перекрыто HWND, связанная с этой целью отрисовки.|  
|[CHwndRenderTarget::Create](#create)|Создает целевой объект отрисовки, связанный с окном|  
|[CHwndRenderTarget::Detach](#detach)|Отсоединяет интерфейса отрисовки целевого объекта|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Возвращает HWND, связанный с этим целевым объектом прорисовки.|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Возвращает интерфейс ID2D1HwndRenderTarget.|  
|[CHwndRenderTarget::ReCreate](#recreate)|Повторно создает целевой объект отрисовки, связанный с окном|  
|[CHwndRenderTarget::Resize](#resize)|Изменяет размер целевого объекта отрисовки на размер указанного пикселей|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Возвращает интерфейс ID2D1HwndRenderTarget.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Указатель на объект ID2D1HwndRenderTarget.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="attach"></a>  CHwndRenderTarget::Attach  
 Присоединяет существующую отрисовки интерфейса целевой объект  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Существующий интерфейс цели отрисовки. Не может иметь значение NULL  
  
##  <a name="checkwindowstate"></a>  CHwndRenderTarget::CheckWindowState  
 Указывает, является ли перекрыто HWND, связанная с этой целью отрисовки.  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее HWND, связанный с этим целевым объектом прорисовки перекрыто.  
  
##  <a name="chwndrendertarget"></a>  CHwndRenderTarget::CHwndRenderTarget  
 Создает объект CHwndRenderTarget из HWND.  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hwnd`  
 HWND, связанный с этим целевым объектом прорисовки  
  
##  <a name="create"></a>  CHwndRenderTarget::Create  
 Создает целевой объект отрисовки, связанный с окном  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 HWND, связанный с этим целевым объектом прорисовки  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE  
  
##  <a name="detach"></a>  CHwndRenderTarget::Detach  
 Отсоединяет интерфейса отрисовки целевого объекта  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенной отрисовки интерфейс целевого объекта.  
  
##  <a name="gethwnd"></a>  CHwndRenderTarget::GetHwnd  
 Возвращает HWND, связанный с этим целевым объектом прорисовки.  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 HWND, связанный с этим целевым объектом прорисовки.  
  
##  <a name="gethwndrendertarget"></a>  CHwndRenderTarget::GetHwndRenderTarget  
 Возвращает интерфейс ID2D1HwndRenderTarget.  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1HwndRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="m_phwndrendertarget"></a>  CHwndRenderTarget::m_pHwndRenderTarget  
 Указатель на объект ID2D1HwndRenderTarget.  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="operator_id2d1hwndrendertarget_star"></a>  CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 Возвращает интерфейс ID2D1HwndRenderTarget.  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1HwndRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="recreate"></a>  CHwndRenderTarget::ReCreate  
 Повторно создает целевой объект отрисовки, связанный с окном  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 HWND, связанный с этим целевым объектом прорисовки  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="resize"></a>  CHwndRenderTarget::Resize  
 Изменяет размер целевого объекта отрисовки на размер указанного пикселей  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Новый размер целевого объекта отрисовки в пикселях устройства  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
