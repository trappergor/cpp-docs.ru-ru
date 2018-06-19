---
title: Стандартная команда и идентификаторы окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72b50108a9b880961f0dd8bcded1126a635fb9e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371654"
---
# <a name="standard-command-and-window-ids"></a>Стандартная команда и идентификаторы окон
Библиотеки классов Microsoft Foundation определяет количество стандартная команда и идентификаторы окон в файле Afxres.h. Эти идентификаторы наиболее часто используются в редакторы ресурсов и окне «Свойства» для сопоставления сообщения с функций-обработчиков. Все стандартные команды имеют **ID_** префикс. Например, при использовании редактора меню обычно привязке элемента меню открытия файла стандарта `ID_FILE_OPEN` команды идентификатор.  
  
 Большинство стандартных команд кода приложения не требуется для ссылки на идентификатор команды, так как сама инфраструктура обрабатывает команды через схемы сообщений в его основной framework классов ( `CWinThread`, `CWinApp`, < c4 Настроек `CView` , **CDocument**и так далее).  
  
 Помимо стандартных идентификаторов команд, определенных ряд других стандартных кодов которого имеют префикс из **AFX_ID**. Эти идентификаторы включают стандартное окно идентификаторы (префикс **AFX_IDW_**), строка, идентификаторы (префикс **AFX_IDS_**) и несколько других типов.  
  
 Идентификаторы, начинающиеся с **AFX_ID** префикс редко используются разработчиками, однако может потребоваться для ссылки на эти идентификаторы при переопределении функции framework, которые также ссылаются на **AFX_ID**s.  
  
 Идентификаторы не документированы в этом справочнике по отдельности. Дополнительные сведения о них можно найти в Технические примечания [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), и [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Файл заголовка Afxres.h неявно включается в Afxwin.h. Явным образом, необходимо включить следующую инструкцию в RC-файл приложения ресурсов:  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
