---
title: Стили элемента управления панели инструментов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 882111e400b613c830bb45cafd03ace99c09a0c2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054948"
---
# <a name="toolbar-control-styles"></a>Стили элемента управления панели инструментов

[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) имеет набор флагов стилей, которые определяют внешний вид и поведение кнопки. Сочетание этих флагов можно задать путем вызова [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). В этом разделе представлены значения флагов стилей и их описания.

## <a name="property-values"></a>Значения свойств

Следующие значения определяют тип, представляющий элемент управления кнопки:

|||
|-|-|
|TBBS_BUTTON|Стандартный pushbutton (по умолчанию).  |
|TBBS_CHECKBOX|Флажок.  |
|TBBS_CHECKGROUP|Начало у группы флажков.  |
|TBBS_GROUP|Начало группе кнопок.  |
|TBBS_SEPARATOR|Разделитель.  |

Следующие значения представляют текущее состояние элемента управления:

|||
|-|-|
|TBBS_CHECKED|Будет установлен флажок.  |
|TBBS_DISABLED|Элемент управления отключен.  |
|TBBS_INDETERMINATE|Флажок находится в неопределенном состоянии.  |
|TBBS_PRESSED|Нажата кнопка.  |

Следующее значение изменяет макет кнопок в панели инструментов:

|||
|-|-|
|TBBS_BREAK|Помещает элемент без разделения столбцов в новой строке или в новом столбце.  |

## <a name="remarks"></a>Примечания

Текущий стиль хранится в [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Не задано новое значение `m_nStyle` напрямую, поскольку несколько классов, производных дополнительной обработки при вызове `SetStyles`.

Наглядный диспетчер определяет внешний вид кнопок в каждом из состояний. См. в разделе [диспетчер визуализации](../../mfc/visualization-manager.md) Дополнительные сведения.

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbarbutton.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Диспетчер визуализации](../../mfc/visualization-manager.md)

