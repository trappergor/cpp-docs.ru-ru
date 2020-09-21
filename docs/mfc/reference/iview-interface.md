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
ms.openlocfilehash: 9233ee5a8330c4b2c79ebc7b79e0616612c00204
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743429"
---
# <a name="iview-interface"></a>Интерфейс IView

Реализует несколько методов, которые [квинформсвиев](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений представления управляемому элементу управления.

## <a name="syntax"></a>Синтаксис

```
interface class IView
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IView:: Онактиватевиев](#onactivateview)|Вызывается MFC при активации или отключении представления.|
|[IView:: Онинитиалупдате](#oninitialupdate)|Вызывается структурой после первого присоединения представления к документу, но до первоначального отображения представления.|
|[IView:: OnUpdate](#onupdate)|Вызывается MFC после изменения документа представления; Эта функция позволяет представлению обновлять свое отображение в соответствии с изменениями.|

### <a name="remarks"></a>Remarks

`IView` реализует несколько методов, которые `CWinFormsView` используются для пересылки общих уведомлений о представлении в размещенный управляемый элемент управления. Это [онинитиалупдате](#oninitialupdate), [OnUpdate](#onupdate) и [онактиватевиев](#onactivateview).

`IView` аналогичен [CView](../../mfc/reference/cview-class.md), но используется только с управляемыми представлениями и элементами управления.

Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Требования

Заголовок: афксвинформс. h (определяется в atlmfc\lib\mfcmifc80.dll сборки)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a> IView:: Онактиватевиев

Вызывается MFC при активации или отключении представления.

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Параметры

*активация*<br/>
Указывает, активируется ли представление или деактивируется.

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a> IView:: Онинитиалупдате

Вызывается структурой после первого присоединения представления к документу, но до первоначального отображения представления.

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a> IView:: OnUpdate

Вызывается MFC после изменения документа представления.

```cpp
void OnUpdate();
```

### <a name="remarks"></a>Remarks

Эта функция позволяет представлению обновлять свое отображение в соответствии с изменениями.

## <a name="see-also"></a>См. также

[Класс Квинформсвиев](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)
