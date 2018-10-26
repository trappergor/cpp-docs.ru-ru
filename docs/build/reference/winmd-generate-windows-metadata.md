---
title: -WINMD (Создание метаданных Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 492be2c5510155ab0336070adc4b5ae96a9775c0
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162962"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (создавать метаданные Windows)

Включает создание файла метаданных среды выполнения Windows (.winmd).

> **/ WINMD**\[**:**{**НЕТ**\|**ТОЛЬКО**}]

## <a name="arguments"></a>Аргументы

**/WINMD**<br/>
Значение по умолчанию для приложений универсальной платформы Windows. Компоновщик создает двоичный исполняемый файл и winmd-файл метаданных.

**/WINMD:NO**<br/>
Компоновщик создает двоичный исполняемый файл, но не создает winmd-файл.

**/ WINMD: ТОЛЬКО**<br/>
Компоновщик создает winmd-файл, но не двоичный исполняемый файл.

## <a name="remarks"></a>Примечания

**/WINMD** параметр компоновщика используется для приложений универсальной платформы Windows и компонентов среды выполнения Windows для создания файла метаданных (с расширением winmd) среды выполнения Windows. Winmd-файл представляет собой библиотеку DLL, содержащую метаданные для типов среды выполнения Windows, а в случае компонентов среды выполнения, реализации этих типов. Порядок импорта метаданных [ECMA-335](http://www.ecma-international.org/publications/standards/Ecma-335.htm) standard.

По умолчанию имя выходного файла имеет форму *binaryname*.winmd. Чтобы указать другое имя файла, используйте [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) параметр.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **метаданных Windows** страницу свойств.

1. В **создавать метаданные Windows** раскрывающемся списке выберите нужный вариант.

## <a name="see-also"></a>См. также

[Пошаговое руководство: Создание компонента простой среды выполнения Windows и вызов его из JavaScript](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Введение в язык определения интерфейса Microsoft 3.0](/uwp/midl-3/intro)<br/>
[/WINMDFILE (указание файла WINMD)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (указание файла ключей WINMD)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (указание контейнера ключей)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (частичная подпись файла WINMD)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
