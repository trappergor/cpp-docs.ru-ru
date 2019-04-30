---
title: Точки входа процедуры окна
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 6d91e2c432588afc5a84f7189fa87a7fc2531b1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372016"
---
# <a name="window-procedure-entry-points"></a>Точки входа процедуры окна

Для защиты процедуры окна MFC, модуль статической ссылки на реализацию процедуры специальное окно. Связь осуществляется автоматически, когда модуль связано с MFC. В этой процедуре окна используется макрос AFX_MANAGE_STATE правильно установить состояние действующие модуля, а затем он вызывает `AfxWndProc`, который в свою очередь делегирует `WindowProc` функция-член соответствующего `CWnd`-объект, производный от.

## <a name="see-also"></a>См. также

[Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)
