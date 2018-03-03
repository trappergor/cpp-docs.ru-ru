---
title: "Буфер обмена: Использование буфера обмена Windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6063a27495d46e4b54f3133b92689e4b0faaa631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-using-the-windows-clipboard"></a>Буфер обмена. Использование буфера обмена Windows
В этом разделе описывается использование стандартных API буфера обмена Windows в приложении MFC.  
  
 Большинство приложений для Windows поддерживает вырезания или копирования данных в буфер обмена Windows и вставки данных из буфера обмена. Форматы данных буфера обмена отличаются для различных приложений. Платформа поддерживает ограниченное число форматы буфера обмена для ограниченного количества классов. Обычно реализуется команды буфера обмена, Вырезать, копировать и вставить — в меню "Правка" для представления. Библиотека классов определяет идентификаторы команд для этих команд: **ID_EDIT_CUT**, **ID_EDIT_COPY**, и **ID_EDIT_PASTE**. Также определяются их приглашения строки сообщения.  
  
 [Сообщения и команды в Framework](../mfc/messages-and-commands-in-the-framework.md) способы обработки команды меню в приложении, сопоставив команду меню на функцию-обработчик. До тех пор, пока приложение не определяет функции обработчика для команды буфера обмена в меню Правка, они остаются отключенными. Чтобы создать функции обработчика команд вырезания и копирования, реализуйте выделения в приложении. Чтобы написать функцию обработчика событий для команд Вставить, запрос в буфер обмена, чтобы узнать, содержит ли данные в формате, который может принимать приложения. Например чтобы включить команду копирования, можно написать обработчик примерно следующим образом:  
  
 [!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 Команды вырезания, копирования и вставки важны только в определенных контекстах. Команды вырезания и копирования должен быть включен только в том случае, если что-либо, и команда Вставить только тогда, когда что-нибудь в буфер обмена. Чтобы обеспечить это поведение, определив функции обработчика обновления, которые включают или отключают эти команды в зависимости от контекста. Дополнительные сведения см. в разделе [обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md).  
  
 Библиотеки классов Microsoft Foundation поддерживает буфер обмена текста при правке с `CEdit` и `CEditView` классы. Классы OLE упрощают реализацию операции с буфером обмена, включающих OLE-элементы. Дополнительные сведения о классах OLE см. в разделе [буфер обмена: использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).  
  
 Реализации других редактировать команды меню, например отмены (**ID_EDIT_UNDO**) и повтора (**ID_EDIT_REDO**), также остается для вас. Если приложение не поддерживает эти команды, их можно легко удалить из файла ресурсов с помощью редакторов ресурсов Visual C++.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Копирование и вставка данных](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## <a name="see-also"></a>См. также  
 [Буфер обмена](../mfc/clipboard.md)

