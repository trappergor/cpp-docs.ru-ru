---
title: -выполнение-charset (задание набора символов исполнения) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution-charset
- /execution-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cd7acf018930c013f477cf4c3a8b3260a8d53ec
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714627"
---
# <a name="execution-charset-set-execution-character-set"></a>/ Execution-CharSet (задать выполнение кодировки)

Позволяет указать кодировку выполнения для исполняемого файла.

## <a name="syntax"></a>Синтаксис

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Аргументы

**IANA_name**<br/>
Имя набора символов определен IANA.

**CPID**<br/>
Идентификатор кодовой страницы.

## <a name="remarks"></a>Примечания

Можно использовать **/Execution-CharSet** параметр, чтобы указать набор символов исполнения. Кодировка выполнения имеет кодировку, используемую для текста программы, которая является входными данными для на этапе компиляции, в конце концов предварительной обработки действия. Этот набор символов используется для внутреннего представления любой строковых или символьных литералов в скомпилированный код. Задайте этот параметр для указания расширенной кодировки выполнения для использования при исходные файлы включают символы, не входящие в набор символов для выполнения. Можно использовать либо IANA или имя кодировки ISO или точку (.) и идентификатором страницы 3 – 5 цифр десятичного кода для задания кодировки для использования. Для получения списка поддерживаемых идентификаторы кодовой страницы и кодировка имен, см. в разделе [идентификаторы кодовой страницы](/windows/desktop/Intl/code-page-identifiers).

По умолчанию Visual Studio определяет метку порядка байтов, чтобы определить, если исходный файл в кодировке Юникод, например, UTF-16 или UTF-8. При обнаружении нет метка порядка байтов предполагается исходный файл закодирован при помощи текущей кодовой странице пользователя, пока не задана кодировка имени или кодовой страницы с помощью **кодировки/Source** параметр или   **/UTF-8** параметр. Visual Studio позволяет сохранить исходный код C++ с помощью любого из несколькими кодировками символов. Сведения об источнике и кодировка выполнения, см. в разделе [кодировки](../../cpp/character-sets.md) в документации по языкам.

Если вы хотите задать исходная кодировка и кодировка выполнения в UTF-8, можно использовать **/UTF-8** параметр компилятора ярлыком. Это свойство эквивалентно указанию **/source-charset:utf-8 /execution-charset:utf-8** в командной строке. Любой из этих параметров также включает **/Validate/CharSet** параметр по умолчанию.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.

1. В **Дополнительно**, добавьте **/Execution-CharSet** и задайте предпочтительной кодировки.

1. Выберите **ОК** для сохранения изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[кодировки/Source (задание исходной кодировки)](../../build/reference/source-charset-set-source-character-set.md)
[/UTF-8 (задать источник и исполняемый файл кодировки UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
 [ /Validate/CharSet (Проверка совместимости символов)](../../build/reference/validate-charset-validate-for-compatible-characters.md)