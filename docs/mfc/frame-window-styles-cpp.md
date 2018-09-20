---
title: Стили окна фрейма (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f0e4bde874fc563535b661108cb68edefd8d977
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385018"
---
# <a name="frame-window-styles-c"></a>Стили окна фрейма (C++)

Окна фрейма, вы получаете с помощью платформы подходят для большинства программ, но вы получаете дополнительную гибкость при помощи дополнительных функций [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) и глобальные функции MFC [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` функция-член из `CWnd`.

Если применить **WS_HSCROLL** и **WS_VSCROLL** стили для фрейма главного окна, вместо этого применяются к **MDICLIENT** окно, поэтому пользователи смогут прокручивать **MDICLIENT** области.

Если окна **FWS_ADDTOTITLE** бит стиля имеет значение (который по умолчанию он разрешен), представление окна фрейма сообщает, какой заголовок, отображаемый в заголовке окна на основе имени представления документа.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Управление дочерними окнами MDI (MDICLIENT)](../mfc/managing-mdi-child-windows.md), окна внутри фрейма MDI, содержащий дочерние окна MDI

- [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [Стили окна](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>См. также

[Окна фрейма](../mfc/frame-windows.md)

