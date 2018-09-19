---
title: -IMPLIB (именование библиотеки импорта) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25d997bf7df96d3f6ee518a8b7ca0568a44efa93
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707646"
---
# <a name="implib-name-import-library"></a>/IMPLIB (именование библиотеки импорта)

> / IMPLIB:*имя файла*

## <a name="parameters"></a>Параметры

*filename*<br/>
Определяемое пользователем имя библиотеки импорта. Он заменяет имя по умолчанию.

## <a name="remarks"></a>Примечания

Параметр/IMPLIB переопределяет имя по умолчанию для библиотеки импорта, LINK при построении программы, содержащую экспорты. По умолчанию имя формируется из базовое имя основного выходного файла и расширение. lib. Программа содержит экспорты, если заданы одно или несколько из следующих:

- [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) ключевое слово в исходном коде

- [ЭКСПОРТЫ](../../build/reference/exports.md) инструкции в DEF-файла

- [/EXPORT](../../build/reference/export-exports-a-function.md) спецификации в команде LINK

LINK игнорирует/IMPLIB, когда не была создана библиотека импорта. Если указаны экспортируемые элементы, ссылка не создает библиотеку импорта. Если файл экспорта используется в сборке, ССЫЛКУ предполагается, что библиотека импорта уже существует и не создает его. Сведения о библиотеками импорта и экспорта файлов, см. в разделе [Справочник по LIB](../../build/reference/lib-reference.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **библиотека импорта** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)