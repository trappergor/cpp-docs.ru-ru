---
title: Интерфейс IView | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84ed9bfb8b0c8b5ab30af07d8f0448109161df51
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077768"
---
# <a name="iview-interface"></a>Интерфейс IView

Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений в представление элемента управления.

## <a name="syntax"></a>Синтаксис

```
interface class IView
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Вызывается средой MFC, когда представление активируется или деактивируется.|
|[IView::OnInitialUpdate](#oninitialupdate)|Вызвано структурой после представления впервые присоединяется к документу, но до изначально отображается представление.|
|[IView::OnUpdate](#onupdate)|Вызывается классами MFC, после этого представления документа был изменен; Эта функция позволяет представлению обновления экрана для отражения изменений.|

## <a name="remarks"></a>Примечания

`IView` реализует несколько методов, `CWinFormsView` использует для пересылки общих уведомлений для размещенного элемента управления. Это [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) и [OnActivateView](#onactivateview).

`IView` аналогичен [CView](../../mfc/reference/cview-class.md), но используется только с управляемых представлений и элементов управления.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Требования

Заголовок: afxwinforms.h (определенных в сборке atlmfc\lib\mfcmifc80.dll)

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
