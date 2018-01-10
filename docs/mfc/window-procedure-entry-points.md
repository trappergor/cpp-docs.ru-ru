---
title: "Точки входа процедуры окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f4e99ce38bd5ae472d688dc779bdd4ccf9fd4c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="window-procedure-entry-points"></a>Точки входа процедуры окна
Чтобы защитить процедуры окна MFC, статические ссылки модуля с помощью реализации процедуры специальное окно. Связь происходит автоматически, когда модуль связывается с MFC. В этой процедуре окна используется `AFX_MANAGE_STATE` макрос правильно устанавливать состояние действующие модуля, а затем она вызывает **AfxWndProc**, который в свою очередь делегирует `WindowProc` функция-член соответствующего `CWnd`-производный объект.  
  
## <a name="see-also"></a>См. также  
 [Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

