---
title: Введение в классы окон ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbd433eb024e7715c065a005ce06d38a086a5072
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765499"
---
# <a name="introduction-to-atl-window-classes"></a>Введение в классы окон ATL

Следующие классы ATL предназначены для реализации и управления окнами.

- [CWindow](../atl/reference/cwindow-class.md) позволяет присоединять дескриптор окна для `CWindow` объекта. Затем можно вызвать `CWindow` методы для управления окном.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) позволяет реализовать новое окно и обрабатывать сообщения с виртуальной схемы сообщений. Можно создавать окна на основе нового класса Windows, суперкласса существующий класс или подкласс существующему окну.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) позволяет реализовать модального или немодального диалогового окна и обработать сообщения со схемой сообщений.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) — это предварительно созданные класс, реализующий окна, в схеме содержится в другом классе. С помощью `CContainedWindowT` позволяет централизовать обработку сообщений в одном классе.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) позволяет реализовать диалоговое окно (модальное или немодальное), на котором размещены элементы управления ActiveX.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) позволяет реализовать модальное диалоговое окно с базовыми функциями.

- [CAxWindow](../atl/reference/caxwindow-class.md) позволяет реализовать окна, на котором размещается элемент управления ActiveX.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) позволяет реализовать окна, на котором размещена лицензированный элемент управления ActiveX.

Помимо классов конкретное окно библиотека ATL предоставляет несколько классов, предназначенных для упрощения реализации объекта ATL окна. Они приведены ниже:

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) управляет данными нового класса окна.

- [CWinTraits](../atl/reference/cwintraits-class.md) и [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) дает простого способа стандартизации признаки объекта ATL окна.

## <a name="see-also"></a>См. также

[Классы окон](../atl/atl-window-classes.md)

