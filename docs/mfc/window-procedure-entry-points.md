---
title: Точки входа процедуры окна | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3226df51d2a83484de78d0d76c9af67e150e8eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403192"
---
# <a name="window-procedure-entry-points"></a>Точки входа процедуры окна

Для защиты процедуры окна MFC, модуль статической ссылки на реализацию процедуры специальное окно. Связь осуществляется автоматически, когда модуль связано с MFC. В этой процедуре окна используется макрос AFX_MANAGE_STATE правильно установить состояние действующие модуля, а затем он вызывает `AfxWndProc`, который в свою очередь делегирует `WindowProc` функция-член соответствующего `CWnd`-объект, производный от.

## <a name="see-also"></a>См. также

[Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

