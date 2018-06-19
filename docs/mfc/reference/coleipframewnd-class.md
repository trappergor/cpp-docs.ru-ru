---
title: Класс COleIPFrameWnd | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 466948653a5464a940a027e473e79c00dbf9a6ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370384"
---
# <a name="coleipframewnd-class"></a>Класс COleIPFrameWnd
Основа для окна редактирования приложения "на месте".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Создает объект `COleIPFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Вызывается платформой, когда элемент активируется для встроенного редактирования.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Вызывается платформой для изменения положения окна редактирования по месту.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс создает и позиций контроль линии в окне документа приложения-контейнера. Он также обрабатывает уведомления, созданные встроенный [COleResizeBar](../../mfc/reference/coleresizebar-class.md) объекта при изменении размера окна редактирования по месту.  
  
 Дополнительные сведения об использовании `COleIPFrameWnd`, см. в статье [активации](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd  
 Создает `COleIPFrameWnd` объекта и инициализирует его сведения о состоянии на месте, которое хранится в структуре типа **OLEINPLACEFRAMEINFO**.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) в Windows SDK.  
  
##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars  
 Платформа вызывает `OnCreateControlBars` работать, когда элемент активируется для встроенного редактирования.  
  
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
 Указатель на фрейм окна приложения-контейнера.  
  
 *pWndDoc*  
 Указатель на окно уровня документа контейнера. Может быть **NULL** Если контейнер является приложением SDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для выполнения специальной обработки при создании панелей элементов управления.  
  
##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame  
 Платформа вызывает `RepositionFrame` функции-члена для размещения панелей элементов управления и изменить положение окна редактирования по месту, все его видимым.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPosRect`  
 Указатель на `RECT` структуры или `CRect` объект, содержащий на месте фрейма окна текущей координаты, в пикселях, относительно клиентской области.  
  
 `lpClipRect`  
 Указатель на `RECT` структуры или `CRect` объект, содержащий на месте фрейма окна текущий прямоугольник отсечения координатами в пикселях относительно клиентской области.  
  
### <a name="remarks"></a>Примечания  
 Макет панели элементов управления в окне контейнера отличается от, выполняемые классом окно фрейма, отличных от OLE. Окна фрейма, отличных от OLE вычисляет положение панелей элементов управления и других объектов из данного окна фрейма размера, как и вызов [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Клиентская область — что остается после вычитания место для панелей элементов управления и других объектов. Объект `COleIPFrameWnd` окна, с другой стороны, помещает панели инструментов в соответствии с заданной клиентской области. Другими словами `CFrameWnd::RecalcLayout` работает «извне,», в то время как `COleIPFrameWnd::RepositionFrame` работает «изнутри.»  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
