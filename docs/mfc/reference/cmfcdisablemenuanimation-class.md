---
title: CMFCDisableMenuAnimation Класс
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: c6d81f253016d3a292dd50b16c19f76a05e75e56
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752422"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation Класс

Отпугивает всплывающее меню анимации.

## <a name="syntax"></a>Синтаксис

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Формирует объект `CMFCDisableMenuAnimation`.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCDisableMenuAnimation::Восстановление](#restore)|Восстанавливает предыдущую анимацию, используемую в фрейм-меню.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|Имя|Описание|
|`CMFCDisableMenuAnimation::m_animType`|Хранит предыдущий тип анимации всплывающих меню.|

### <a name="remarks"></a>Remarks

Используйте этот класс помощников, чтобы временно отключить всплывающее меню анимации (например, при обработке команд мыши или клавиатуры).

Объект `CMFCDisableMenuAnimation` отсутживает всплывающее меню анимации в течение своего срока службы. Конструктор хранит текущий тип анимации всплывающих `m_animType` меню в поле и `CMFCPopupMenu::NO_ANIMATION`устанавливает текущий тип анимации. Деструктор восстанавливает предыдущий тип анимации.

Можно создать `CMFCDisableMenuAnimation` объект в стеке, чтобы отключить анимацию всплывающее меню на протяжении всей одной функции. Если вы хотите отключить анимацию всплывающее меню `CMFCDisableMenuAnimation` между функциями, создайте объект на куче, а затем удалите его, когда вы хотите восстановить всплывающее меню анимации.

## <a name="example"></a>Пример

В следующем примере показано, как использовать стек для временного отключить анимацию меню.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpopupmenu.h

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a>CMFCDisableMenuAnimation::Восстановление

Восстанавливает предыдущую анимацию, используемую в фрейм-меню.

```cpp
void Restore ();
```

### <a name="remarks"></a>Remarks

Этот метод вызывается `CMFCDisableMenuAnimation` деструктором для восстановления предыдущей анимации, используемой для отображения всплывающих меню.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
