---
title: Сочетания клавиш (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: bb407538f254df5f187ff91b85a8eaa753a52287
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362391"
---
# <a name="accelerator-keys-c"></a>Сочетания клавиш (C++)

## <a name="predefined-accelerator-keys"></a>Стандартные сочетания клавиш

Существуют стандартные сочетания клавиш, которые могут быть использованы в проектах приложений Windows. Некоторые из этих виртуальных клавиш предназначены для среды Windows. Другие поддерживают браузера или приложения на базе Юникода. Вы можете использовать любую из этих клавиш в любом сочетании.

|Ключ|Описание|
|---------|-----------------|
|VK_ACCEPT|(IME) примите|
|VK_BROWSER_BACK|(Windows) Браузер, **обратно** ключ|
|VK_BROWSER_FAVORITES|(Windows) Браузер, **"Избранное"** ключ|
|VK_BROWSER_FORWARD|(Windows) Браузер, **вперед** ключ|
|VK_BROWSER_HOME|(Windows) Браузер, **запустить** и **Главная** ключ|
|VK_BROWSER_REFRESH|(Windows) Браузер, **обновить** ключ|
|VK_BROWSER_SEARCH|(Windows) Браузер, **поиска** ключ|
|VK_BROWSER_STOP|(Windows) Браузер, **остановить** ключ|
|VK_CONVERT|Convert (IME)|
|VK_FINAL|Последний режим (IME)|
|VK_HANGUEL|(IME) Режим "хангул" (поддерживается для обеспечения совместимости, используйте клавишу VK_HANGUL.)|
|VK_HANGUL|(IME) Режим "хангыль"|
|VK_HANJA|(IME) Режим "ханджа"|
|VK_JUNJA|(IME) Режим "Джунджа"|
|VK_KANA|(IME) Режим "кана"|
|VK_KANJI|(IME) Режим "Кандзи"|
|VK_LAUNCH_APP1|(Windows) **Запуска приложения 1** ключ|
|VK_LAUNCH_APP2|(Windows) **Запуска приложения 2** ключ|
|VK_LAUNCH_MAIL|(Windows) **Запуска почты** ключ|
|VK_LAUNCH_MEDIA_SELECT|(Windows) **Выбора носителя** ключ|
|VK_LCONTROL|**Ctrl слева** ключ|
|VK_LMENU|**Меню с левой стороны** ключ|
|VK_LSHIFT|**Shift слева** ключ|
|VK_MEDIA_NEXT_TRACK|(Windows) **Следующая запись** ключ|
|VK_MEDIA_PLAY_PAUSE|(Windows) **Мультимедиа воспроизведение/пауза** ключ|
|VK_MEDIA_PREV_TRACK|(Windows) **Предыдущая запись** ключ|
|VK_MEDIA_STOP|(Windows) **Остановить мультимедиа** ключ|
|VK_MODECHANGE|Запрос на изменение режима (IME)|
|VK_NONCONVERT|Без преобразования (IME)|
|VK_OEM_1|(Windows) На стандартной клавиатуре США **;:** ключ|
|VK_OEM_102|(Windows) Ключ угловой скобкой или обратной косой чертой на 102-клавишной клавиатуре RT|
|VK_OEM_2|(Windows) На стандартной клавиатуре США **/?** клавиша|
|VK_OEM_3|(Windows) На стандартной клавиатуре США **`~** ключ|
|VK_OEM_4|(Windows) На стандартной клавиатуре США **[{** ключ|
|VK_OEM_5|(Windows) На стандартной клавиатуре США **\\ &#124;** ключ|
|VK_OEM_6|(Windows) На стандартной клавиатуре США **]}** ключ|
|VK_OEM_7|(Windows) На стандартной клавиатуре США, раздел «один кавычка/двойная кавычка»|
|VK_OEM_COMMA|(Windows) Для любой страны или региона **,** ключ|
|VK_OEM_MINUS|(Windows) Для любой страны или региона **-** ключ|
|VK_OEM_PERIOD|(Windows) Для любой страны или региона **.** клавиша|
|VK_OEM_PLUS|(Windows) Для любой страны или региона **+** ключ|
|VK_PACKET|(Windows) Используется для передачи символов Юникода, как будто они являются нажатий клавиш.|
|VK_RCONTROL|**Справа Ctrl** ключ|
|VK_RMENU|**Меню справа** ключ|
|VK_RSHIFT|**Левая клавиша Shift** ключ|
|VK_SLEEP|**Компьютер в спящем режиме** ключ|
|VK_VOLUME_DOWN|(Windows) **Уменьшения громкости** ключ|
|VK_VOLUME_MUTE|(Windows) **Звука** ключ|
|VK_VOLUME_UP|(Windows) **Увеличения громкости** ключ|
|VK_XBUTTON1|(Windows) **X1** кнопки мыши|
|VK_XBUTTON2|(Windows) **X2** кнопки мыши|

## <a name="accelerator-key-association"></a>Сопоставление ключа сочетаний клавиш

Во многих случаях требуется, чтобы пункт меню и сочетание клавиш выдавали одну и ту же команду. Это можно сделать, назначив один и тот же идентификатор ресурса (ID) пункту меню и записи в таблице сочетаний клавиш приложения. Затем можно изменить заголовок пункта меню, чтобы показать имя сочетания клавиш. Дополнительные сведения о пунктах меню и сочетаний клавиш см. в разделе [команды меню](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сочетаний клавиш](../windows/accelerator-editor.md)<br/>