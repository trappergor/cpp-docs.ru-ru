---
title: Использование диалоговой панели с элементом управления "Главная панель" | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9d4155fec333061c65f148f29e849dc4717f0d2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073765"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Использование диалоговой панели с элементом управления главной панели

Как упоминалось в [главной панели элементов управления и зоны](../mfc/rebar-controls-and-bands.md), каждой зоны может содержать только один дочерний окна (или элемента управления). Это может быть ограничением, если вы хотите иметь более одного дочернего окна для аппаратного контроллера управления. Удобный обходной путь — Создание ресурса панели диалогового окна с помощью нескольких элементов управления и затем добавить зону главной панели (содержащий диалоговая панель) к элементу управления "Главная панель".

Как правило при желании аппаратного контроллера управления панели диалогового окна с прозрачным, как задать WS_EX_TRANSPARENT расширенный стиль для объекта панели диалогового окна. Тем не менее поскольку WS_EX_TRANSPARENT есть некоторые проблемы с правильно заливку фона контейнера диалоговой панели, необходимо будет сделать немного усилий для достижения желаемого эффекта.

Ниже процедуре подробно описываются действия, необходимые для достижения прозрачности без использования WS_EX_TRANSPARENT расширенный стиль.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Для реализации прозрачного диалоговой панели в зону главной панели

1. С помощью [диалоговое окно добавления класса](../mfc/reference/adding-an-mfc-class.md), добавьте новый класс (например, `CMyDlgBar`), реализующий объект панели диалогового окна.

1. Добавьте обработчик для сообщения WM_ERASEBKGND.

1. В новый обработчик измените существующий код в соответствии со следующим примером:

   [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. Добавьте обработчик для сообщения WM_MOVE.

1. В новый обработчик измените существующий код в соответствии со следующим примером:

   [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Новые обработчики смоделировать прозрачность диалоговой панели, пересылки сообщения WM_ERASEBKGND родительского окна и принудительно перекрашивает каждый раз при перемещении объекта панели диалогового окна.

## <a name="see-also"></a>См. также

[Использование CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

