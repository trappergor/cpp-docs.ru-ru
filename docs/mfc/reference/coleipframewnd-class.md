---
title: "Класс COleIPFrameWnd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd class
- OLE, editing
- OLE, in-place activation
- in-place editing
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
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
ms.openlocfilehash: 85ce028bb5d72c06a0e228abba1bd08a7f6526cb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewnd-class"></a>Класс COleIPFrameWnd
Основа для окна редактирования приложения "на месте".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Создает объект `COleIPFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Вызывается инфраструктурой при активизации элемента для редактирования на месте.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Вызывается средой, чтобы изменить положение окна редактирования на месте.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс создает и позиций контроля линии в окне документа приложения-контейнера. Он также обрабатывает уведомления, созданные встроенный [COleResizeBar](../../mfc/reference/coleresizebar-class.md) объекта, когда пользователь изменяет размер окна редактирования на месте.  
  
 Дополнительные сведения об использовании `COleIPFrameWnd`, см. в статье [активации](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 Создает `COleIPFrameWnd` объекта и инициализирует информацию о своем состоянии на месте, которое хранится в структуре типа **OLEINPLACEFRAMEINFO**.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 Платформа вызывает функцию `OnCreateControlBars` работать при активизации элемента для редактирования на месте.  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndFrame*  
 Указатель фрейма окна приложения-контейнера.  
  
 *pWndDoc*  
 Указатель на окно документа уровня контейнера. Может быть **NULL** Если контейнер является приложении SDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для выполнения специальной обработки при создании панелей элементов управления.  
  
##  <a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 Платформа вызывает функцию `RepositionFrame` функции-члена для размещения элементов управления и изменить положение окна редактирования на месте, все из них является видимым.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPosRect`  
 Указатель на `RECT` структуры или `CRect` объект, содержащий месте в кадр координат текущего положения окна, в пикселях, относительно клиентской области.  
  
 `lpClipRect`  
 Указатель на `RECT` структуры или `CRect` объект, содержащий месте фрейма окна текущий прямоугольник отсечения координат, в пикселях, относительно клиентской области.  
  
### <a name="remarks"></a>Примечания  
 Макет панели элементов управления в окне контейнера отличается от, выполненных в окне фрейма отличных от OLE. Окна фрейма, отличных от OLE вычисляет положение панелей элементов управления и других объектов из данного окна фрейма размер, как и вызов [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Клиентская область — что остается после вычитания место для панелей элементов управления и других объектов. A `COleIPFrameWnd` окно, с другой стороны, помещает панели инструментов в соответствии с заданной клиентской области. Другими словами `CFrameWnd::RecalcLayout` работает «из-за пределов,», тогда как `COleIPFrameWnd::RepositionFrame` работает «наизнанку.»  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)

