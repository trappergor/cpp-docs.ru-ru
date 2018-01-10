---
title: "Класс CBitmapRenderTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
dev_langs: C++
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f07e3783de7efe4e279a4f8d69563349cb72a362
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cbitmaprendertarget-class"></a>Класс CBitmapRenderTarget
Программа-оболочка для ID2D1BitmapRenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Создает объект CBitmapRenderTarget.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](#attach)|Присоединяет существующую отрисовки интерфейса целевой объект|  
|[CBitmapRenderTarget::Detach](#detach)|Отсоединяет интерфейса отрисовки целевого объекта|  
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Получает растровое изображение для этой цели отрисовки. Возвращаемый точечный рисунок может использоваться для операций рисования.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Возвращает интерфейс ID2D1BitmapRenderTarget|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Возвращает интерфейс ID2D1BitmapRenderTarget|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Указатель на объект ID2D1BitmapRenderTarget.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 `CBitmapRenderTarget` 
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="attach"></a>CBitmapRenderTarget::Attach  
 Присоединяет существующую отрисовки интерфейса целевой объект  
  
```  
void Attach(ID2D1BitmapRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Существующий интерфейс цели отрисовки. Не может иметь значение NULL  
  
##  <a name="cbitmaprendertarget"></a>CBitmapRenderTarget::CBitmapRenderTarget  
 Создает объект CBitmapRenderTarget.  
  
```  
CBitmapRenderTarget();
```  
  
##  <a name="detach"></a>CBitmapRenderTarget::Detach  
 Отсоединяет интерфейса отрисовки целевого объекта  
  
```  
ID2D1BitmapRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенной отрисовки интерфейс целевого объекта.  
  
##  <a name="getbitmap"></a>CBitmapRenderTarget::GetBitmap  
 Получает растровое изображение для этой цели отрисовки. Возвращаемый точечный рисунок может использоваться для операций рисования.  
  
```  
BOOL GetBitmap(CD2DBitmap& bitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `bitmap`  
 По возвращении из этого метода содержит недопустимый точечный рисунок для этой цели отрисовки. Этот рисунок может использоваться для операций рисования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="getbitmaprendertarget"></a>CBitmapRenderTarget::GetBitmapRenderTarget  
 Возвращает интерфейс ID2D1BitmapRenderTarget  
  
```  
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="m_pbitmaprendertarget"></a>CBitmapRenderTarget::m_pBitmapRenderTarget  
 Указатель на объект ID2D1BitmapRenderTarget.  
  
```  
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;  
```  
  
##  <a name="operator_id2d1bitmaprendertarget_star"></a>CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *  
 Возвращает интерфейс ID2D1BitmapRenderTarget  
  
```  
operator ID2D1BitmapRenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapRenderTarget или значение NULL, если объект еще не инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
