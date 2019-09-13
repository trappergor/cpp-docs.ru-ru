---
title: /UTF-8 (установка UTF-8 в качестве исходных и исполняемых наборов символов)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 1ff0f23ad0758642c73b1b35d6d4dd1be20899cb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498177"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (установка UTF-8 в качестве исходных и исполняемых наборов символов)

Задает кодировку исходного кода и кодировку выполнения в виде UTF-8.

## <a name="syntax"></a>Синтаксис

```
/utf-8
```

## <a name="remarks"></a>Примечания

С помощью параметра **/UTF-8** можно указать кодировку исходного кода и кодировки выполнения как закодированные при помощи UTF-8. Он эквивалентен указанию **указаны кодировки/Source-Charset: UTF-8/Execution-Charset: UTF-8** в командной строке. Любой из этих параметров также включает параметр **/Validate-charset** по умолчанию. Список поддерживаемых идентификаторов кодовых страниц и имен наборов символов см. в разделе [идентификаторы кодовых страниц](/windows/win32/Intl/code-page-identifiers).

По умолчанию Visual Studio обнаруживает метку порядка следования байтов, чтобы определить, имеет ли исходный файл формат в кодировке Юникод, например UTF-16 или UTF-8. Если метка порядка следования байтов не найдена, предполагается, что исходный файл кодируется с помощью кодовой страницы текущего пользователя, если не указана кодовая страница с помощью **/UTF-8** или параметра **указаны кодировки/Source-charset** . Visual Studio позволяет сохранить C++ исходный код с помощью любой из нескольких кодировок символов. Сведения о кодировках исходного кода и выполнения см. в разделе [наборы символов](../../cpp/character-sets.md) в документации по языку.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните папку **Свойства конфигурации**, **C/C++** , **Командная строка** .

1. В окне **Дополнительные параметры**добавьте параметр **/UTF-8** , чтобы указать предпочтительную кодировку.

1. Выберите **ОК** для сохранения внесенных изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/Execution-charset (Задание кодировки выполнения)](execution-charset-set-execution-character-set.md)<br/>
[/source/charset (задание исходной кодировки)](source-charset-set-source-character-set.md)<br/>
[/validate/charset (проверка совместимости символов)](validate-charset-validate-for-compatible-characters.md)
