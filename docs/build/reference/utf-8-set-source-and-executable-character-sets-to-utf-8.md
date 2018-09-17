---
title: -utf 8 (задать источник и исполняемый файл кодировки UTF-8) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1193af2891a2cd3150fdb1cee9dd6957a1fe271
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704071"
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

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.

1. В **Дополнительно**, добавьте **/UTF-8** и задайте предпочтительной кодировки.

1. Выберите **ОК** для сохранения изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/ Execution-CharSet (задать выполнение кодировки)](../../build/reference/execution-charset-set-execution-character-set.md)
[кодировки/Source (задание исходной кодировки)](../../build/reference/source-charset-set-source-character-set.md)
 [ /Validate/CharSet (Проверка совместимости символов)](../../build/reference/validate-charset-validate-for-compatible-characters.md)