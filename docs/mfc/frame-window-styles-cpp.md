---
title: Стили окна фрейма (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: 3c22944537370a44aee1af1cf71281264ed4969b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626457"
---
# <a name="frame-window-styles-c"></a>Стили окна фрейма (C++)

Окна фрейма, получаемые с помощью платформы, подходят для большинства программ, но вы можете получить дополнительную гибкость, используя расширенные функции [PreCreateWindow](reference/cwnd-class.md#precreatewindow) и глобальную функцию MFC [афксрегистервндкласс](reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow`является функцией-членом `CWnd` .

Если применить стили **WS_HSCROLL** и **WS_VSCROLL** к главному окну фрейма, они будут применены к окну **мдиклиент** , чтобы пользователи могли прокручивать область **мдиклиент** .

Если установлен бит стиля **FWS_ADDTOTITLE** окна (который по умолчанию имеет значение), представление сообщает окну фрейма, какое название будет отображаться в строке заголовка окна на основе имени документа представления.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Управление дочерними ОКНАМИ MDI (мдиклиент)](managing-mdi-child-windows.md), окно в фрейме MDI, которое содержит дочерние окна MDI

- [Изменение стилей окна, созданного MFC](changing-the-styles-of-a-window-created-by-mfc.md)

- [Стили окна](reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>См. также раздел

[Окна фрейма](frame-windows.md)
