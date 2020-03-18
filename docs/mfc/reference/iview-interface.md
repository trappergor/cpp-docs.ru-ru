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
ms.openlocfilehash: e8afa7a5f5a7692f88ace4da08209b80f902b603
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445666"
---
# <a name="iview-interface"></a>Интерфейс IView

Реализует несколько методов, которые [квинформсвиев](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений представления управляемому элементу управления.

## <a name="syntax"></a>Синтаксис

```
interface class IView
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[IView:: Онактиватевиев](#onactivateview)|Вызывается MFC при активации или отключении представления.|
|[IView:: Онинитиалупдате](#oninitialupdate)|Вызывается структурой после первого присоединения представления к документу, но до первоначального отображения представления.|
|[IView:: OnUpdate](#onupdate)|Вызывается MFC после изменения документа представления; Эта функция позволяет представлению обновлять свое отображение в соответствии с изменениями.|

## <a name="remarks"></a>Remarks

`IView` реализует несколько методов, которые `CWinFormsView` использует для пересылки общих уведомлений представления в управляемый элемент управления. Это [онинитиалупдате](#oninitialupdate), [OnUpdate](#onupdate) и [онактиватевиев](#onactivateview).

`IView` похожа на [CView](../../mfc/reference/cview-class.md), но используется только с управляемыми представлениями и элементами управления.

Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Требования

Заголовок: афксвинформс. h (определен в сборке atlmfc\lib\mfcmifc80.dll)

## <a name="onactivateview"></a>IView:: Онактиватевиев

Вызывается MFC при активации или отключении представления.

```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Параметры

*активация*<br/>
Указывает, активируется ли представление или деактивируется.

## <a name="oninitialupdate"></a>IView:: Онинитиалупдате

Вызывается структурой после первого присоединения представления к документу, но до первоначального отображения представления.

```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView:: OnUpdate

Вызывается MFC после изменения документа представления.

```
void OnUpdate();
```

## <a name="remarks"></a>Remarks

Эта функция позволяет представлению обновлять свое отображение в соответствии с изменениями.

## <a name="see-also"></a>См. также раздел

[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)
