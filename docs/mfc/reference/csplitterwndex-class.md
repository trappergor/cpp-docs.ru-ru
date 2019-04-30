---
title: Класс CSplitterWndEx
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 8dedad4e99a37b13dc618859c8e6d8a83a65ea76
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339606"
---
# <a name="csplitterwndex-class"></a>Класс CSplitterWndEx

Представляет настроенное окно-разделитель.

## <a name="syntax"></a>Синтаксис

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|Конструктор по умолчанию.|
|`CSplitterWndEx::~CSplitterWndEx`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Вызывается платформой для отрисовки окна разделителя. (Переопределяет [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>Примечания

Переопределить `OnDrawSplitter` метод для настройки внешнего вида графические компоненты окна-разделителя.

`CSplitterWndEx` Класс используется вместе с [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), и [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) методов, используемых реализуется наглядный диспетчер. Чтобы вызвать диспетчер визуального для рисования в приложении окна разделителя, замените объявления `CSplitterWnd` класса `CSplitterWndEx` класса. Для приложений окна фрейма класс окна разделителя объявляется в CMainFrame-класс, который находится в mainfrm.h. Например, см. в разделе `OutlookDemo` образца в каталог образцов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxsplitterwndex.h

##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter

Вызывается платформой для отрисовки окна разделителя.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства. Если этот параметр имеет значение NULL, платформа перерисовывает активного окна.

*nType*<br/>
[in] Один из `CSplitterWnd::ESplitType` значений перечисления, задающее элемент окна разделителя для рисования. Допустимые значения: `splitBox`, `splitBar`, `splitIntersection` и `splitBorder`.

*rect*<br/>
[in] Ограничивающий прямоугольник, который указывает размеры и расположение, чтобы нарисовать элемент window указанного разделителя.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../hierarchy-chart.md)<br/>
[Классы](mfc-classes.md)<br/>
[Класс CSplitterWnd](csplitterwnd-class.md)<br/>
[Класс CMFCVisualManager](cmfcvisualmanager-class.md)
