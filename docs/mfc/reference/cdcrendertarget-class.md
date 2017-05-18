---
title: "Класс CDCRenderTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CDCRenderTarget class
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2bbd62b06f4287904fce49f8a6ce9900476b07c0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdcrendertarget-class"></a>Класс CDCRenderTarget
Программа-оболочка для ID2D1DCRenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|Создает объект CDCRenderTarget.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDCRenderTarget::Attach](#attach)|Присоединяет существующую отображения интерфейса целевой объект|  
|[CDCRenderTarget::BindDC](#binddc)|Привязывает объект рендеринга контекста устройства, к которому она выдает команд рисования|  
|[CDCRenderTarget::Create](#create)|Создает CDCRenderTarget.|  
|[CDCRenderTarget::Detach](#detach)|Отсоединяет визуализации интерфейса целевого объекта|  
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Возвращает интерфейс ID2D1DCRenderTarget|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Возвращает интерфейс ID2D1DCRenderTarget|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|Указатель на объект ID2D1DCRenderTarget.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="attach"></a>CDCRenderTarget::Attach  
 Присоединяет существующую отображения интерфейса целевой объект  
  
```  
void Attach(ID2D1DCRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Существующий интерфейс целевой отрисовки. Не может иметь значение NULL  
  
##  <a name="binddc"></a>CDCRenderTarget::BindDC  
 Привязывает объект рендеринга контекста устройства, к которому она выдает команд рисования  
  
```  
BOOL BindDC(
    const CDC& dc,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Контекст устройства, в которую целевой объект отрисовки выдает команд рисования  
  
 `rect`  
 Размеры дескриптор контекста устройства (HDC), к которому привязан объект рендеринга  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="cdcrendertarget"></a>CDCRenderTarget::CDCRenderTarget  
 Создает объект CDCRenderTarget.  
  
```  
CDCRenderTarget();
```  
  
##  <a name="create"></a>CDCRenderTarget::Create  
 Создает CDCRenderTarget.  
  
```  
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```  
  
### <a name="parameters"></a>Параметры  
 `props`  
 Режим отрисовки, формат пикселей, параметры удаленного взаимодействия, DPI сведения и Минимальная поддержка DirectX, необходимые для подготовки к просмотру оборудования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="detach"></a>CDCRenderTarget::Detach  
 Отсоединяет визуализации интерфейса целевого объекта  
  
```  
ID2D1DCRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенные отображения интерфейса целевой.  
  
##  <a name="getdcrendertarget"></a>CDCRenderTarget::GetDCRenderTarget  
 Возвращает интерфейс ID2D1DCRenderTarget  
  
```  
ID2D1DCRenderTarget* GetDCRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1DCRenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="m_pdcrendertarget"></a>CDCRenderTarget::m_pDCRenderTarget  
 Указатель на объект ID2D1DCRenderTarget.  
  
```  
ID2D1DCRenderTarget* m_pDCRenderTarget;  
```  
  
##  <a name="operator_id2d1dcrendertarget_star"></a>CDCRenderTarget::operator ID2D1DCRenderTarget *  
 Возвращает интерфейс ID2D1DCRenderTarget  
  
```  
operator ID2D1DCRenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1DCRenderTarget или значение NULL, если объект еще не инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

