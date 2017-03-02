---
title: "Класс CBitmapRenderTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CBitmapRenderTarget
- CBitmapRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CBitmapRenderTarget class
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: 16
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 11bea138185df23c9f3cc79491c71d86861a6bdc
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmaprendertarget-class"></a>Класс CBitmapRenderTarget
Программа-оболочка для ID2D1BitmapRenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Создает объект CBitmapRenderTarget.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](#attach)|Присоединяет существующую отображения интерфейса целевой объект|  
|[CBitmapRenderTarget::Detach](#detach)|Отсоединяет визуализации интерфейса целевого объекта|  
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Возвращает битовую карту для этой цели визуализации. Возвращаемый точечный рисунок можно использовать для операций рисования.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Возвращает интерфейс ID2D1BitmapRenderTarget|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Возвращает интерфейс ID2D1BitmapRenderTarget|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Указатель на объект ID2D1BitmapRenderTarget.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 `CBitmapRenderTarget` 
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-nameattacha--cbitmaprendertargetattach"></a><a name="attach"></a>CBitmapRenderTarget::Attach  
 Присоединяет существующую отображения интерфейса целевой объект  
  
```  
void Attach(ID2D1BitmapRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Существующий интерфейс целевой отрисовки. Не может иметь значение NULL  
  
##  <a name="a-namecbitmaprendertargeta--cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a>CBitmapRenderTarget::CBitmapRenderTarget  
 Создает объект CBitmapRenderTarget.  
  
```  
CBitmapRenderTarget();
```  
  
##  <a name="a-namedetacha--cbitmaprendertargetdetach"></a><a name="detach"></a>CBitmapRenderTarget::Detach  
 Отсоединяет визуализации интерфейса целевого объекта  
  
```  
ID2D1BitmapRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенные отображения интерфейса целевой.  
  
##  <a name="a-namegetbitmapa--cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a>CBitmapRenderTarget::GetBitmap  
 Возвращает битовую карту для этой цели визуализации. Возвращаемый точечный рисунок можно использовать для операций рисования.  
  
```  
BOOL GetBitmap(CD2DBitmap& bitmap);
```  
  
### <a name="parameters"></a>Параметры  
 `bitmap`  
 При возвращении данного метода содержит недопустимый точечный рисунок для этой цели визуализации. Этот рисунок может использоваться для операций рисования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="a-namegetbitmaprendertargeta--cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a>CBitmapRenderTarget::GetBitmapRenderTarget  
 Возвращает интерфейс ID2D1BitmapRenderTarget  
  
```  
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namempbitmaprendertargeta--cbitmaprendertargetmpbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a>CBitmapRenderTarget::m_pBitmapRenderTarget  
 Указатель на объект ID2D1BitmapRenderTarget.  
  
```  
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;  
```  
  
##  <a name="a-nameoperatorid2d1bitmaprendertargetstara--cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a>CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *  
 Возвращает интерфейс ID2D1BitmapRenderTarget  
  
```  
operator ID2D1BitmapRenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1BitmapRenderTarget или значение NULL, если объект еще не инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

