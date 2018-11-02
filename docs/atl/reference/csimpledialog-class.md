---
title: Класс CSimpleDialog
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 8662a1bc17f84c8a2513a1126b28d676d0939b31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474078"
---
# <a name="csimpledialog-class"></a>Класс CSimpleDialog

Этот класс реализует базовый модальное диалоговое окно.

## <a name="syntax"></a>Синтаксис

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>Параметры

*t_wDlgTemplateID*

Идентификатор ресурса ресурс шаблона диалоговых окон.

*t_bCenter*<br/>
Значение TRUE, если объект диалогового окна должен быть отцентрован в окно-владелец; в противном случае — значение FALSE.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|Создает модальное диалоговое окно.|

## <a name="remarks"></a>Примечания

Реализует модальное диалоговое окно с базовыми функциями. `CSimpleDialog` обеспечивает поддержку элементах управления Windows только. Для создания и отображения модального диалогового окна, создайте экземпляр этого класса, указав имя существующего ресурса шаблона диалогового окна "". Объект диалогового окна закрывается при нажатии любой элемент управления с помощью предварительно определенного значения (например, IDOK и IDCANCEL).

`CSimpleDialog` можно создавать только модальные диалоговые окна. `CSimpleDialog` предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений соответствующих обработчиков.

См. в разделе [реализация диалогового окна](../../atl/implementing-a-dialog-box.md) Дополнительные сведения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="domodal"></a>  CSimpleDialog::DoModal

Вызывает модальное диалоговое окно и возвращает результат диалогового окна по завершении.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Дескриптор родительского окна. Если значение не указано, родительский присваивается текущее активное окно.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращается идентификатор ресурса элемента управления, закрыть диалоговое окно.

Если функция завершается с ошибкой, возвращается значение-1. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

Этот метод обрабатывает все взаимодействие с пользователем при активном окне. Именно это и делает окно модальным; то есть пользователь не может взаимодействовать с другими окнами, пока не будет закрыто диалоговое окно.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
