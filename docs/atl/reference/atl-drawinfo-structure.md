---
title: "Структура ATL_DRAWINFO | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: bc124de97acf85d6e706605afb55b0747a327ade
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="atldrawinfo-structure"></a>Структура ATL_DRAWINFO
Содержит сведения, используемые для отрисовки для различных целей, например принтер, метафайла или элемент управления ActiveX.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```  
  
## <a name="members"></a>Члены  
 `cbSize`  
 Размер структуры в байтах.  
  
 **dwDrawAspect**  
 Указывает, как целевой объект будет присутствовать. Представления могут включать содержимое, значок, эскиз или печати документа. Список возможных значений см. в разделе [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) и [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **Индекс**  
 Часть объекта, требуемая для операции рисования. Его интерпретация зависит от значения в **dwDrawAspect** член.  
  
 **ptd**  
 Указатель на [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуру, которая включает оптимизацию рисования, в зависимости от заданных пропорций. Обратите внимание, что новые объекты и контейнеры, поддерживающие оптимизированного графических интерфейсов поддерживают также этот член. Более старые объекты и контейнеры, которые не поддерживают оптимизированного графических интерфейсов всегда указывать **NULL** для этого элемента.  
  
 **hicTargetDev**  
 Информационный контекст для целевого устройства, на который указывает **ptd** из которого объект может извлечь метрики устройства и тестирования возможности устройства. Если **ptd** — **NULL**, объект должен игнорировать значение в **hicTargetDev** член.  
  
 **hdcDraw**  
 Контекст устройства, на котором выполняется отрисовка. Для объекта без окон **hdcDraw** элемент находится в `MM_TEXT` режим сопоставления в логических координатах сопоставления клиентских координат окна. Кроме того, контекст устройства должны быть в том же состоянии, что обычно передается по `WM_PAINT` сообщение.  
  
 **prcBounds**  
 Указатель на [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) структура прямоугольника на **hdcDraw** и в котором должен быть нарисован объект. Этот элемент управляет размещением и Растягивание объекта. Этот элемент должен быть **NULL** для рисования без окон активного объекта на месте. В любой другой ситуации **NULL** не является допустимым значением и должно привести к `E_INVALIDARG` код ошибки. Если контейнер передает значение, отличное от**NULL** значение в объект безоконный объект запрошенный аспект подготавливаться к просмотру в заданном контексте устройства и прямоугольник. Контейнер может запросить эти данные из объекта без окон для отображения представления объекта, во-вторых, неактивная или печати объекта.  
  
 **prcWBounds**  
 Если **hdcDraw** является контекст устройства метафайла (см. [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]), это указатель на **RECTL** структура ограничивающий прямоугольник в базовом метафайле. Структура прямоугольник содержит область окна и окна источника. Эти значения можно использовать для рисования метафайлы. Указывает прямоугольник **prcBounds** вложен в это **prcWBounds** прямоугольником; они находятся в том же пространстве координат.  
  
 **bOptimize**  
 Ненулевое значение, если рисование элемента управления является быть оптимизировано, в противном случае — 0. Если рисунок оптимизирован, состояние контекста устройства автоматически восстанавливается при завершении подготовки к просмотру.  
  
 **bZoomed**  
 Ненулевое значение, если целевой имеет значение масштаба, в противном случае — 0. Коэффициент масштабирования хранится в **ZoomNum**.  
  
 **bRectInHimetric**  
 Ненулевое значение, если размеры **prcBounds** в **HIMETRIC**, в противном случае — 0.  
  
 **ZoomNum**  
 Ширина и высота прямоугольника, в котором отображается объект. Коэффициент масштабирования по оси x (долю естественный размер объекта в его текущем степени) целевого объекта — это значение **ZoomNum.cx** делится значение **ZoomDen.cx**. Аналогичным образом достигается коэффициент масштабирования по оси y.  
  
 **ZoomDen**  
 Фактические ширина и высота целевого объекта.  
  
## <a name="remarks"></a>Примечания  
 Типичное использование этой структуры будет извлечения данных во время отрисовки данного целевого объекта. Например, можно извлечь значения из `ATL_DRAWINFO` внутри своей перегрузку [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).  
  
 Эта структура сохраняет нужные сведения, используемые для отображения внешнего вида объекта для целевого устройства. Можно использовать сведения, приведенные в рисования на экране, принтер или даже метафайл.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)






