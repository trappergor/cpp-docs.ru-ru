---
title: Сочетания клавиш (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 4f838caa8ca9e4a996fa4cb8018d663c6c7aecea
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504296"
---
# <a name="accelerator-keys-c"></a>Сочетания клавиш (C++)

## <a name="predefined-accelerator-keys"></a>Стандартные сочетания клавиш

Существуют стандартные сочетания клавиш, которые могут быть использованы в проектах приложений Windows. Некоторые из этих виртуальных клавиш предназначены для среды Windows. Другие поддерживают браузер или приложения для Юникода. Вы можете использовать любую из этих клавиш в любом сочетании.

|Клавиши|Описание|
|---------|-----------------|
|VK_ACCEPT|(IME) Accept|
|VK_BROWSER_BACK|Windows Браузер, клавиша **возврата**|
|VK_BROWSER_FAVORITES|Windows Браузер, ключ **"Избранное"**|
|VK_BROWSER_FORWARD|Windows Браузер, клавиша " **вперед** "|
|VK_BROWSER_HOME|Windows Обозреватель, **начальный** и **домашний** ключи|
|VK_BROWSER_REFRESH|Windows Браузер, ключ **обновления**|
|VK_BROWSER_SEARCH|Windows Браузер, ключ **поиска**|
|VK_BROWSER_STOP|Windows Браузер, клавиша **завершения**|
|VK_CONVERT|(IME) Convert|
|VK_FINAL|(IME) окончательный режим|
|VK_HANGUEL|ВВОДА Режим хангуел (поддерживается для обеспечения совместимости, используйте VK_HANGUL)|
|VK_HANGUL|ВВОДА Режим хангыль|
|VK_HANJA|ВВОДА Режим ханджа|
|VK_JUNJA|ВВОДА Режим жунжа|
|VK_KANA|ВВОДА Режим Каны|
|VK_KANJI|ВВОДА Режим кандзи|
|VK_LAUNCH_APP1|Windows **Запустить ключ приложения 1**|
|VK_LAUNCH_APP2|Windows **Запустить ключ приложения 2**|
|VK_LAUNCH_MAIL|Windows **Запустить почтовый** ключ|
|VK_LAUNCH_MEDIA_SELECT|Windows **Выбор ключа носителя**|
|VK_LCONTROL|Клавиша **CTRL слева**|
|VK_LMENU|Клавиша **меню слева**|
|VK_LSHIFT|Клавиша **SHIFT слева**|
|VK_MEDIA_NEXT_TRACK|Windows Ключ **следующей записи**|
|VK_MEDIA_PLAY_PAUSE|Windows **Воспроизвести или приостановить ключ носителя**|
|VK_MEDIA_PREV_TRACK|Windows Ключ **предыдущей записи**|
|VK_MEDIA_STOP|Windows **Выключить ключ носителя**|
|VK_MODECHANGE|(IME) запрос на изменение режима|
|VK_NONCONVERT|(IME) не преобразовывать|
|VK_OEM_1|Windows Для стандартной клавиатуры США клавиша **;:**|
|VK_OEM_102|Windows Либо ключ угловой скобки, либо клавиша обратной косой черты на клавиатуре RT 102.|
|VK_OEM_2|Windows Для стандартной клавиатуры США в поле **/?** ключ|
|VK_OEM_3|Windows Для стандартной клавиатуры США **`~** ключ|
|VK_OEM_4|Windows Для стандартной клавиатуры США параметр **[{** Key|
|VK_OEM_5|Windows Для стандартной клавиатуры США ** \\&#124;** ключ|
|VK_OEM_6|Windows Для стандартной клавиатуры США клавиша **]}**|
|VK_OEM_7|Windows Для стандартной клавиатуры США — клавиша "одинарная кавычка/двойная кавычка"|
|VK_OEM_COMMA|Windows Для любой страны или региона **, ключ**|
|VK_OEM_MINUS|Windows Для любой страны или региона **-** ключ|
|VK_OEM_PERIOD|Windows Для любой страны или региона **.** ключ|
|VK_OEM_PLUS|Windows Для любой страны или региона **+** ключ|
|VK_PACKET|Windows Используется для передачи символов Юникода, как если бы они были нажатиями клавиш.|
|VK_RCONTROL|Клавиша **CTRL справа**|
|VK_RMENU|Клавиша контекстного **меню**|
|VK_RSHIFT|Клавиша **SHIFT справа**|
|VK_SLEEP|Ключ **спящего режима компьютера**|
|VK_VOLUME_DOWN|Windows Ключ **уменьшения громкости**|
|VK_VOLUME_MUTE|Windows Ключ **отключения тома**|
|VK_VOLUME_UP|Windows Ключ **уровня громкости**|
|VK_XBUTTON1|Windows Кнопка мыши **x1**|
|VK_XBUTTON2|Windows Кнопка мыши в **x2**|

## <a name="accelerator-key-association"></a>Связывание сочетаний клавиш

Во многих случаях требуется, чтобы пункт меню и сочетание клавиш выдавали одну и ту же команду. Это действие выполняется путем назначения одного идентификатора ресурса (ID) элементу меню и записи в таблице сочетаний клавиш приложения. Затем можно изменить заголовок пункта меню, чтобы показать имя сочетания клавиш. Дополнительные сведения об элементах меню и сочетаниях клавиш см. в разделе [команды меню](./menu-command-properties.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также раздел

[Редактор сочетаний клавиш](../windows/accelerator-editor.md)<br/>
