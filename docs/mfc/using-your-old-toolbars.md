---
title: Использование старых панелей инструментов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COldToolBar
dev_langs:
- C++
helpviewer_keywords:
- toolbars [MFC], backward compatibility
- COldToolBar class [MFC]
ms.assetid: 3543257c-8547-43f0-a66a-ee641dc1cf89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab5f743b2584733bc8d2bc1edf4c212ba40210f0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417609"
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

