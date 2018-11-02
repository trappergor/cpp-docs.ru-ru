---
title: Класс CMFCDisableMenuAnimation
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: 0b0df30d48b2f77d620b00f67d40743445981b66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665040"
---
# <a name="cmfcdisablemenuanimation-class"></a>Класс CMFCDisableMenuAnimation

Отключает анимацию всплывающего меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Создает объект `CMFCDisableMenuAnimation`.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCDisableMenuAnimation::Restore](#restore)|Восстановление предыдущей анимацией, используемый платформой для отображения всплывающего меню.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|name|Описание|
|`CMFCDisableMenuAnimation::m_animType`|Сохраняет предыдущий тип анимации всплывающего меню.|

### <a name="remarks"></a>Примечания

Используйте этот вспомогательный класс для временного отключения анимации всплывающего меню (например, при обработке команды мыши или клавиатуры).

Объект `CMFCDisableMenuAnimation` объект отключает анимацию всплывающего меню во время его существования. Конструктор сохраняет текущий тип анимации всплывающего меню в `m_animType` поле и введите текущей анимации для наборов `CMFCPopupMenu::NO_ANIMATION`. Деструктор восстанавливает предыдущий тип анимации.

Можно создать `CMFCDisableMenuAnimation` объект в стеке для отключения анимации всплывающего меню на протяжении всего одну функцию. Если вы хотите отключить всплывающего меню анимации между функциями, создайте `CMFCDisableMenuAnimation` объекта в куче и затем удалите его, если вы хотите восстановить анимации всплывающего меню.

## <a name="example"></a>Пример

Приведенный ниже показано, как использовать стек будет временно отключить анимация меню.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpopupmenu.h

##  <a name="restore"></a>  CMFCDisableMenuAnimation::Restore

Восстановление предыдущей анимацией, используемый платформой для отображения всплывающего меню.

```
void Restore ();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается `CMFCDisableMenuAnimation` деструктор для восстановления предыдущей анимацией, используемый платформой для отображения всплывающего меню.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
