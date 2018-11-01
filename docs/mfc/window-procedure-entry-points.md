---
title: Точки входа процедуры окна
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 9e395ff96d27476bc2869e23139cb2d1233f02ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500923"
---
# <a name="window-procedure-entry-points"></a>Точки входа процедуры окна

Для защиты процедуры окна MFC, модуль статической ссылки на реализацию процедуры специальное окно. Связь осуществляется автоматически, когда модуль связано с MFC. В этой процедуре окна используется макрос AFX_MANAGE_STATE правильно установить состояние действующие модуля, а затем он вызывает `AfxWndProc`, который в свою очередь делегирует `WindowProc` функция-член соответствующего `CWnd`-объект, производный от.

## <a name="see-also"></a>См. также

[Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

