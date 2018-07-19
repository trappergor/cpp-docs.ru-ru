---
title: Класс COleIPFrameWnd | Документация Майкрософт
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
ms.openlocfilehash: ee4a9d3156a4d5efecd74406b92a1a7bcec48d1f
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849150"
---
# <a name="coleipframewnd-class"></a>Класс COleIPFrameWnd
Основа для окна редактирования приложения "на месте".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Создает объект `COleIPFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Вызывается платформой при активации элемента для редактирования на месте.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Вызывается платформой для изменения положения окна редактирования на месте.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс создает и позиций контроль линии в окне документа приложения-контейнера. Он также обрабатывает уведомления, созданные встроенный [COleResizeBar](../../mfc/reference/coleresizebar-class.md) объекта при изменении размера окна редактирования на месте.  
  
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
 Создает `COleIPFrameWnd` объекта и инициализирует его сведения о состоянии на месте, которое хранится в структуре типа oleinplaceframeinfo, КОТОРУЮ.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [oleinplaceframeinfo, КОТОРУЮ](http://msdn.microsoft.com/library/windows/desktop/ms693737) в пакете Windows SDK.  
  
##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars  
 Платформа вызывает `OnCreateControlBars` функционировать, когда элемент активируется для редактирования на месте.  
  
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
  
 *принимает pWndDoc*  
 Указатель на окна документа контейнера. Может иметь значение NULL, если контейнер является приложением SDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успешного выполнения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию для выполнения специальной обработки при создании панелей элементов управления.  
  
##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame  
 Платформа вызывает `RepositionFrame` функцию-член для размещения панелей элементов управления и изменить положение окна редактирования на месте, поэтому все из них является видимым.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Параметры  
 *lpPosRect*  
 Указатель на `RECT` структуры или `CRect` объект, содержащий на месте кадров координаты текущего положения окна, в пикселях, относительно клиентской области.  
  
 *lpClipRect*  
 Указатель на `RECT` структуры или `CRect` объект, содержащий на месте фрейма окна текущий прямоугольник отсечения координатами в пикселях, относительно клиентской области.  
  
### <a name="remarks"></a>Примечания  
 Макет панели элементов управления в окне контейнера отличается от, проведенных окна фрейма, отличных от OLE. Окна фрейма, отличных от OLE вычисляет положение панелей элементов управления и другим объектам размер заданного окна фрейма, как и в вызов [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Клиентская область — останется после вычитания пространства для панелей элементов управления и других объектов. Объект `COleIPFrameWnd` окно, с другой стороны, помещает панелей инструментов в соответствии с заданной клиентской области. Другими словами `CFrameWnd::RecalcLayout` работает «извне,», в то время как `COleIPFrameWnd::RepositionFrame` работает «наизнанку.»  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
