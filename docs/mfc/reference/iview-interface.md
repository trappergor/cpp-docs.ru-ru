---
title: Интерфейс IView
ms.date: 11/04/2016
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
ms.openlocfilehash: 22e08a70ff4cc742406a1489899c0ba1df7eb664
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321953"
---
# <a name="iview-interface"></a>Интерфейс IView

Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений в представление элемента управления.

## <a name="syntax"></a>Синтаксис

```
interface class IView
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Вызывается средой MFC, когда представление активируется или деактивируется.|
|[IView::OnInitialUpdate](#oninitialupdate)|Вызвано структурой после представления впервые присоединяется к документу, но до изначально отображается представление.|
|[IView::OnUpdate](#onupdate)|Вызывается классами MFC, после этого представления документа был изменен; Эта функция позволяет представлению обновления экрана для отражения изменений.|

## <a name="remarks"></a>Примечания

`IView` реализует несколько методов, `CWinFormsView` использует для пересылки общих уведомлений для размещенного элемента управления. Это [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) и [OnActivateView](#onactivateview).

`IView` аналогичен [CView](../../mfc/reference/cview-class.md), но используется только с управляемых представлений и элементов управления.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Требования

Header: afxwinforms.h (defined in assembly atlmfc\lib\mfcmifc80.dll)

## <a name="onactivateview"></a> IView::OnActivateView

Вызывается средой MFC, когда представление активируется или деактивируется.
```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Параметры

*активировать*<br/>
Указывает, является ли представление активируется или деактивируется.

## <a name="oninitialupdate"></a> IView::OnInitialUpdate

Вызвано структурой после представления впервые присоединяется к документу, но до изначально отображается представление.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate

Вызывается средой MFC, после изменения этого представления документа.
```
void OnUpdate();
```

## <a name="remarks"></a>Примечания

Эта функция позволяет представлению обновления экрана для отражения изменений.

## <a name="see-also"></a>См. также

[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)
