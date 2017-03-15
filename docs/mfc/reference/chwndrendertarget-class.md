---
title: "Класс CHwndRenderTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- afxrendertarget/CHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget class
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1af6795e89c995ba6b5a7b094f06b0aea776f561
ms.lasthandoff: 02/24/2017

---
# <a name="chwndrendertarget-class"></a>Класс CHwndRenderTarget
Программа-оболочка для ID2D1HwndRenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Создает объект CHwndRenderTarget от HWND.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|Присоединяет существующую отображения интерфейса целевой объект|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Указывает, является ли перекрыто HWND, связанную с этой целью визуализации.|  
|[CHwndRenderTarget::Create](#create)|Создает целевой объект отрисовки, связанные с окном|  
|[CHwndRenderTarget::Detach](#detach)|Отсоединяет визуализации интерфейса целевого объекта|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Возвращает HWND, связанный с данным объектом рендеринга.|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Возвращает интерфейс ID2D1HwndRenderTarget.|  
|[CHwndRenderTarget::ReCreate](#recreate)|Повторно создает целевой объект отрисовки, связанные с окном|  
|[CHwndRenderTarget::Resize](#resize)|Изменяет размер целевого объекта отрисовки размер указанного пиксела|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Возвращает интерфейс ID2D1HwndRenderTarget.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Указатель на объект ID2D1HwndRenderTarget.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-nameattacha--chwndrendertargetattach"></a><a name="attach"></a>CHwndRenderTarget::Attach  
 Присоединяет существующую отображения интерфейса целевой объект  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Существующий интерфейс целевой отрисовки. Не может иметь значение NULL  
  
##  <a name="a-namecheckwindowstatea--chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState  
 Указывает, является ли перекрыто HWND, связанную с этой целью визуализации.  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее HWND, связанный с данным объектом рендеринга перекрыто.  
  
##  <a name="a-namechwndrendertargeta--chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget  
 Создает объект CHwndRenderTarget от HWND.  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hwnd`  
 HWND, связанный с данным объектом рендеринга  
  
##  <a name="a-namecreatea--chwndrendertargetcreate"></a><a name="create"></a>CHwndRenderTarget::Create  
 Создает целевой объект отрисовки, связанные с окном  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 HWND, связанный с данным объектом рендеринга  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае она возвращает значение FALSE  
  
##  <a name="a-namedetacha--chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderTarget::Detach  
 Отсоединяет визуализации интерфейса целевого объекта  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенные отображения интерфейса целевой.  
  
##  <a name="a-namegethwnda--chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndRenderTarget::GetHwnd  
 Возвращает HWND, связанный с данным объектом рендеринга.  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 HWND, связанный с данным объектом рендеринга.  
  
##  <a name="a-namegethwndrendertargeta--chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget  
 Возвращает интерфейс ID2D1HwndRenderTarget.  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1HwndRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namemphwndrendertargeta--chwndrendertargetmphwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget  
 Указатель на объект ID2D1HwndRenderTarget.  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="a-nameoperatorid2d1hwndrendertargetstara--chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 Возвращает интерфейс ID2D1HwndRenderTarget.  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1HwndRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namerecreatea--chwndrendertargetrecreate"></a><a name="recreate"></a>CHwndRenderTarget::ReCreate  
 Повторно создает целевой объект отрисовки, связанные с окном  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `hWnd`  
 HWND, связанный с данным объектом рендеринга  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-nameresizea--chwndrendertargetresize"></a><a name="resize"></a>CHwndRenderTarget::Resize  
 Изменяет размер целевого объекта отрисовки размер указанного пиксела  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Новый размер целевого объекта отрисовки в пикселях устройства  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

