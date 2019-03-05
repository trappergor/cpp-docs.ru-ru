---
title: Использование старых панелей инструментов
ms.date: 11/04/2016
f1_keywords:
- COldToolBar
helpviewer_keywords:
- toolbars [MFC], backward compatibility
- COldToolBar class [MFC]
ms.assetid: 3543257c-8547-43f0-a66a-ee641dc1cf89
ms.openlocfilehash: bcfa11b2d7d7cd7426d0c75df71a4b0eb2d96ed6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266826"
---
# <a name="using-your-old-toolbars"></a>Использование старых панелей инструментов

При использовании предыдущих версий Visual C++ для создания настраиваемых панелей инструментов, новая реализация класса [CToolBar](../mfc/reference/ctoolbar-class.md) может вызвать проблемы. Таким образом, чтобы у вас нет необходимости освободить старых панелей инструментов, чтобы использовать новые функциональные возможности, старая реализация по-прежнему поддерживается.

Образец DOCKTOOL не использует устаревший панелей инструментов, только новый стиль панели инструментов.

Невозможно изменение панелей инструментов в старом стиле с панели инструментов редактора ресурсов.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Основные сведения о панели инструментов](../mfc/toolbar-fundamentals.md)

- [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)

- [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)

- [Работа с элементом управления панели инструментов](../mfc/working-with-the-toolbar-control.md)

## <a name="see-also"></a>См. также

[Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)
