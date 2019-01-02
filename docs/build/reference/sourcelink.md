---
title: / SOURCELINK (Sourcelink включить файл в PDB-ФАЙЛ)
ms.date: 08/20/2018
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: a5a01ca56a49791a608c5c836312c7728e9328c3
ms.sourcegitcommit: fe1e21df175cd004d21c6e4659082efceb649a8b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53978287"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/ SOURCELINK (включить ссылку на исходный файл в PDB-ФАЙЛ)

Указывает файл конфигурации, ссылки на источник для включения в PDB-файла компоновщиком.

## <a name="syntax"></a>Синтаксис

> **/ SOURCELINK:**_имя файла_

## <a name="arguments"></a>Аргументы

*filename*<br/>
Задает конфигурации в формате JSON файл, содержащий простое сопоставление локальных путей для URL-адреса приложения откуда можно извлечь исходный файл для отображения в отладчике. Дополнительные сведения о формате этого файла см. в разделе [исходной схемы JSON ссылку](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md#source-link-json-schema).

## <a name="remarks"></a>Примечания

Ссылка на источник — система зависит от языка - и системы управления версиями для предоставления отладки исходного кода для двоичных файлов. Ссылка на источник поддерживается для собственных двоичных файлов C++, начиная с Visual Studio 2017 версии 15.8. Обзор ссылки на источник, см. в разделе [ссылки на источник](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md). Сведения об использовании ссылки на источник в проектах и как для создания файла SourceLink как часть проекта, см. в разделе [с помощью ссылки на источник](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects).

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Установка параметра компоновщика /SOURCELINK в Visual Studio

1. Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры** , добавьте **/SOURCELINK:**_filename_ и выберите **ОК** или **применить**для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- Этот параметр не поддерживает программный эквивалент.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
