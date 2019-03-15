---
title: / UTF-8 (задать источник и кодировки исполняемого файла в кодировке UTF-8)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 5ac15c63041e76b8bb0d292868bb982c21866078
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812295"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/ UTF-8 (задать источник и кодировки исполняемого файла в кодировке UTF-8)

Указывает, как исходный набор символов и кодировка выполнения как UTF-8.

## <a name="syntax"></a>Синтаксис

```
/utf-8
```

## <a name="remarks"></a>Примечания

Можно использовать **/UTF-8** параметр, чтобы указать источник и выполнения кодировки в кодировке с помощью UTF-8. Это свойство эквивалентно указанию **/source-charset:utf-8 /execution-charset:utf-8** в командной строке. Любой из этих параметров также включает **/Validate/CharSet** параметр по умолчанию. Для получения списка поддерживаемых идентификаторы кодовой страницы и кодировка имен, см. в разделе [идентификаторы кодовой страницы](/windows/desktop/Intl/code-page-identifiers).

По умолчанию Visual Studio определяет метку порядка байтов, чтобы определить, если исходный файл в кодировке Юникод, например, UTF-16 или UTF-8. При обнаружении нет метка порядка байтов предполагается исходный файл закодирован при помощи текущей кодовой странице пользователя, пока не задана кодовая страница с помощью **/UTF-8** или **кодировки/Source** параметр. Visual Studio позволяет сохранить исходный код C++ с помощью любого из несколькими кодировками символов. Сведения об источнике и кодировка выполнения, см. в разделе [кодировки](../../cpp/character-sets.md) в документации по языкам.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.

1. В **Дополнительные параметры**, добавьте **/UTF-8** параметр, чтобы указать предпочтительной кодировки.

1. Выберите **ОК** для сохранения внесенных изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/ Execution-CharSet (задать выполнение кодировки)](execution-charset-set-execution-character-set.md)<br/>
[/source/charset (задание исходной кодировки)](source-charset-set-source-character-set.md)<br/>
[/validate/charset (проверка совместимости символов)](validate-charset-validate-for-compatible-characters.md)
