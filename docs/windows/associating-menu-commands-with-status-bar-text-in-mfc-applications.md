---
title: Привязка команд меню к тексту строки состояния в приложениях MFC
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [C++], associating menu items
- menus [C++], status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
ms.openlocfilehash: fc39695358a9c1f2f62878487a5e4fedf5db2b82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468891"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>Привязка команд меню к тексту строки состояния в приложениях MFC

Приложение MFC может отображать описательный текст для каждой из команд меню, которые может выбрать пользователь. Добиться этого можно назначить строку текста для каждой команды меню, используя **Prompt** свойство в **свойства** окна. Если в [таблице строк](../windows/string-editor.md) имеется строка, идентификатор которой совпадает с идентификатором команды, приложение MFC автоматически отобразит этот строковый ресурс в строке состояния выполняющегося приложения в момент, когда пользователь наведет указатель мыши на пункт меню.

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>Чтобы связать команду меню со строкой текста в строке состояния, выполните следующие действия.

1. В редакторе **меню** выберите команду меню.

2. В [окне "Свойства"](/visualstudio/ide/reference/properties-window)в поле **Prompt** (Подсказка) введите нужный текст для строки состояния.

## <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Добавление команд в меню](../windows/adding-commands-to-a-menu.md)<br/>
[Редактор меню](../windows/menu-editor.md)