---
title: Класс CSplitterWndEx | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ae4a24424acc4385927e0f7c99735bd50a6d472
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121654"
---
# <a name="csplitterwndex-class"></a>Класс CSplitterWndEx



Представляет настроенное окно-разделитель.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|Конструктор по умолчанию.|  
|`CSplitterWndEx::~CSplitterWndEx`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Вызывается платформой для отрисовки окна-разделителя. (Переопределяет [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>Примечания  
 Переопределить `OnDrawSplitter` метод для настройки внешнего вида графическими компонентами окна-разделителя.  
  
 `CSplitterWndEx` Класс используется вместе с [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), и [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) методы, представляющие собой реализован диспетчер визуального представления. Чтобы вызвать Диспетчер визуальных для отрисовки в приложении окна-разделителя, вместо объявления `CSplitterWnd` класса `CSplitterWndEx` класса. Для приложений, окно фрейма класс окна разделителя объявляется в CMainFrame-класс, который расположен в mainfrm.h. Пример см. в разделе `OutlookDemo` в каталог образцов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter  
 Вызывается платформой для отрисовки окна-разделителя.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства. Если этот параметр имеет значение NULL, платформа перерисовывает активного окна.  
  
 [in] *nType*  
 Один из `CSplitterWnd::ESplitType` значений перечисления, определяющее элемент окна разделителя для рисования. Допустимые значения: `splitBox`, `splitBar`, `splitIntersection`, и `splitBorder`.  
  
 [in] *rect*  
 Ограничивающий прямоугольник, который указывает размеры и расположение для рисования заданного разделителя элемент-окно.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../hierarchy-chart.md)   
 [Классы](mfc-classes.md)   
 [Класса CSplitterWnd](csplitterwnd-class.md)   
 [Класс CMFCVisualManager](cmfcvisualmanager-class.md)