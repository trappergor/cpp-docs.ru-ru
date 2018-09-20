---
title: 'Элементы ActiveX в MFC: Возврат кодов ошибок из метода | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9daaa86f6f57d28b56a7374ff64b0fcbca2a3d98
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383601"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>Элементы управления ActiveX в MFC. Возврат кодов ошибок из метода

В этой статье описывается, как возвращать коды ошибок из метода, элемент управления ActiveX.

Чтобы указать, что произошла ошибка в методе, следует использовать [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) функцией-членом, которая принимает SCODE (код состояния) как параметр. Можно использовать предопределенные SCODE или определить один из ваших собственных.

> [!NOTE]
>  `ThrowError` предназначен для использования только с точки зрения сообщение об ошибке из внутри свойства Get или Set функция или метод автоматизации. Это только те представления времени, которые будут соответствующему обработчику исключений в стеке.

Вспомогательные функции существуют для самых распространенных стандартными SCODEs, такими как [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), и [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

Список предварительно определенных SCODEs и инструкции по определению пользовательских SCODEs, см. в разделе [обработка ошибок в ваш элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX: Дополнительные разделы.

Дополнительные сведения о reporting исключения в других областях кода, см. в разделе [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) и разделе [обработка ошибок в ваш элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX: Дополнительные разделы.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

