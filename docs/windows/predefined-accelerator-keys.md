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
ms.openlocfilehash: 6ef8f84564d6fd1957452971cb1e88dc99aa27e9
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320514"
---
# <a name="accelerator-keys-c"></a>Сочетания клавиш (C++)

## <a name="predefined-accelerator-keys"></a>Стандартные сочетания клавиш

Существуют стандартные сочетания клавиш, которые могут быть использованы в проектах приложений Windows. Некоторые из этих виртуальных клавиш предназначены для среды Windows. Другие поддерживают браузеры или приложения на базе Юникода. Вы можете использовать любую из этих клавиш в любом сочетании.

|Ключ|Описание:|
|---------|-----------------|
|VK_ACCEPT|Принять IME|
|VK_BROWSER_BACK|Windows: Клавиша назад в браузере|
|VK_BROWSER_FAVORITES|Windows: Клавиша браузера "Избранное"|
|VK_BROWSER_FORWARD|Windows: Клавиша вперед в браузере|
|VK_BROWSER_HOME|Windows: Запуск обозревателя и Клавиша домашней страницы|
|VK_BROWSER_REFRESH|Windows: Клавиша обновления в браузере|
|VK_BROWSER_SEARCH|Windows: Клавиша поиска в браузере|
|VK_BROWSER_STOP|Windows: Клавиша остановки в браузере|
|VK_CONVERT|Преобразование в редакторе метода ввода|
|VK_FINAL|Последний режим редактора метода ввода|
|VK_HANGUEL|Режим "Хангул" редактора метода ввода (Поддерживается для обеспечения совместимости. Используйте клавишу VK_HANGUL.)|
|VK_HANGUL|Режим "Хангыль" редактора метода ввода|
|VK_HANJA|Режим "Ханджа" редактора метода ввода|
|VK_JUNJA|Режим "Джунджа" редактора метода ввода|
|VK_KANA|Режим "Кана" редактора метода ввода|
|VK_KANJI|Режим "Кандзи" редактора метода ввода|
|VK_LAUNCH_APP1|Windows: Клавиша запуска приложения 1|
|VK_LAUNCH_APP2|Windows: Клавиша запуска приложения 2|
|VK_LAUNCH_MAIL|Windows: Клавиша запуска почты|
|VK_LAUNCH_MEDIA_SELECT|Windows: Клавиша выбора мультимедиа|
|VK_LCONTROL|Левая клавиша CONTROL|
|VK_LMENU|Левая клавиша МЕНЮ|
|VK_LSHIFT|Левая клавиша SHIFT|
|VK_MEDIA_NEXT_TRACK|Windows: Далее клавиша "запись"|
|VK_MEDIA_PLAY_PAUSE|Windows: Клавиша воспроизведения, паузы мультимедиа|
|VK_MEDIA_PREV_TRACK|Windows: Предыдущий клавиша "запись"|
|VK_MEDIA_STOP|Windows: Остановить ключ носителя|
|VK_MODECHANGE|Запрос на изменение режима редактора метода ввода|
|VK_NONCONVERT|Нет преобразования в редакторе метода ввода|
|VK_OEM_1|Windows: На стандартной клавиатуре США ";:" ключ|
|VK_OEM_102|Windows: Ключ угловой скобкой или обратной косой чертой на 102-клавишной клавиатуре RT|
|VK_OEM_2|Windows: На стандартной клавиатуре США «/?» клавиша|
|VK_OEM_3|Windows: На стандартной клавиатуре США "~" ключа|
|VK_OEM_4|Windows: На стандартной клавиатуре США "[{" key|
|VK_OEM_5|Windows: На стандартной клавиатуре США "\\&#124;" ключа|
|VK_OEM_6|Windows: На стандартной клавиатуре США "]}" ключа|
|VK_OEM_7|Windows: На стандартной клавиатуре США, раздел «один кавычка/двойная кавычка»|
|VK_OEM_COMMA|Windows: Для любой страны или региона, клавиша «»|
|VK_OEM_MINUS|Windows: Для любой страны или региона "-" ключа|
|VK_OEM_PERIOD|Windows: Для любой страны или региона "." ключа|
|VK_OEM_PLUS|Windows: Для любой страны или региона, клавиша «+»|
|VK_PACKET|Windows: Используется для передачи символов Юникода, как если бы они нажатий клавиш.|
|VK_RCONTROL|Правая клавиша CONTROL|
|VK_RMENU|Правая клавиша МЕНЮ|
|VK_RSHIFT|Правая клавиша SHIFT|
|VK_SLEEP|Клавиша перевода компьютера в спящий режим|
|VK_VOLUME_DOWN|Windows: Клавиша уменьшения громкости|
|VK_VOLUME_MUTE|Windows: Клавиша выключения звука|
|VK_VOLUME_UP|Windows: Клавиша увеличения громкости|
|VK_XBUTTON1|Windows: Кнопка мыши X1|
|VK_XBUTTON2|Windows: Кнопка мыши X2|

## <a name="accelerator-key-association"></a>Сопоставление ключа сочетаний клавиш

Во многих случаях требуется, чтобы пункт меню и сочетание клавиш выдавали одну и ту же команду. Это делается путем назначения одного и того же идентификатора ресурса (ID) пункту меню и записи в таблице сочетаний клавиш приложения. Затем можно изменить заголовок пункта меню, чтобы показать имя сочетания клавиш. Дополнительные сведения о пунктах меню и сочетаний клавиш см. в разделе [связывание пункта меню с сочетанием клавиш](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сочетаний клавиш](../windows/accelerator-editor.md)<br/>