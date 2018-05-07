---
title: Точки входа процедуры окна | Документы Microsoft
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
ms.openlocfilehash: 1095061cce8ff8f189984aca99a06eb741a46e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="window-procedure-entry-points"></a>Точки входа процедуры окна
Чтобы защитить процедуры окна MFC, статические ссылки модуля с помощью реализации процедуры специальное окно. Связь происходит автоматически, когда модуль связывается с MFC. В этой процедуре окна используется `AFX_MANAGE_STATE` макрос правильно устанавливать состояние действующие модуля, а затем она вызывает **AfxWndProc**, который в свою очередь делегирует `WindowProc` функция-член соответствующего `CWnd`-производный объект.  
  
## <a name="see-also"></a>См. также  
 [Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

