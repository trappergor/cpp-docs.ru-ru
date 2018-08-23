---
title: Предопределенные символы Win32 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], predefined symbols
- symbols, Win32 predefined
- Windows API [C++], predefined symbols
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8578692701d6f9037ed40ed9ece34c79ca7f2275
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592792"
---
# <a name="win32-predefined-symbols"></a>Предопределенные символы Win32

Эти символы определены в заголовочных файлах Win32, и они поддерживают стандартные функции приложения Windows и действия. Эти символы используются главным образом с помощью общих элементов пользовательского интерфейса. Если вы работаете с элементами управления ресурсами в редакторах, эти символы будут показаны в [окно "Свойства"](/visualstudio/ide/reference/properties-window) связанный с помощью стандартных элементов управления. Например, если на панель инструментов должны отображаться значок приложения, значок будет связан с символом IDI_SMALL в **окно свойств**.

|||
|-|-|
|IDABORT|Управления: Кнопка прерывания полю диалоговое окно|
|IDC_STATIC|Элемент управления: Статический текст в диалоговом окне|
|IDCANCEL|Элемент управления: Кнопки диалогового окна "Отмена"|
|IDD_ABOUTBOX|Диалогового окна: Продукт диалоговое окно «о продукте»|
|IDI_PROJECTNAME|Значок: Значок текущего проекта|
|IDI_SMALL|Значок: Маленький значок текущего проекта|
|IDIGNORE|Элемент управления: Используется с кнопкой "Ignore," о диалоговых окнах|
|IDM_ABOUT|Пункт меню: Используется с помощью... О...|
|IDM_EXIT|Пункт меню: Используется с файлом... Выход...|
|IDNO|Элемент управления: Диалоговое окно кнопка "Нет"|
|IDOK|Управления: Кнопки ОК поле диалогового окна|
|IDRETRY|Элемента управления: Кнопка повтора поле диалогового окна|
|IDS_APP_TITLE|Строка: Имя текущего приложения|
|IDYES|Управления: Диалоговое окно Да кнопку|

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)  
[Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)