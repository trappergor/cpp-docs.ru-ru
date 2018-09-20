---
title: Стандартная команда и идентификаторы окон | Документация Майкрософт
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
ms.openlocfilehash: 2106312bd83edc4a37c904e2ee87ce78acb82904
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379135"
---
# <a name="standard-command-and-window-ids"></a>Стандартная команда и идентификаторы окон

Библиотеки Microsoft Foundation Class определяет ряд стандартная команда и идентификаторы окна в файле Afxres.h. Чаще всего эти идентификаторы используются в редакторы ресурсов и окне «Свойства» для сопоставления сообщений к функции обработчика. Все стандартные команды имеют **ID_** префикс. Например при использовании редактора меню, обычно привязке пункта меню открытия файла к стандартной ID_FILE_OPEN идентификатор команды.

Большинство стандартных команд, код приложения не требуется ссылаться на идентификатор команды, так как платформа сама обрабатывает команды через схемы сообщений в его основной framework классы (`CWinThread`, `CWinApp`, `CView`, `CDocument`, и т. д).

В дополнение к стандартные идентификаторы команд, ряд других стандартных идентификаторов определяются которого имеют префикс из **AFX_ID**. Эти идентификаторы указаны ИД стандартное окно (префикс **AFX_IDW_**), строка идентификаторы (префикс **AFX_IDS_**) и несколько других типов.

Идентификаторы, начинающиеся с **AFX_ID** префикс редко используются разработчиками, но может потребоваться для ссылки на эти идентификаторы при переопределении функции framework, которые также ссылаются на **AFX_ID**s.

Идентификаторы не документированы в этом справочнике по отдельности. Дополнительные сведения о них можно найти в Технические примечания [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), и [22](../../mfc/tn022-standard-commands-implementation.md).

> [!NOTE]
>  Файл заголовка Afxres.h косвенно включается в Afxwin.h. Явным образом, необходимо включить следующую инструкцию в файле RC-ресурса приложения:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
