---
title: "/Zf (создания быстрее PDB-файла) | Документы Microsoft"
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e8817b72e5e6eb7ba808455113104e8fb5000505
ms.sourcegitcommit: d24de38f9da844f824acb9d200a3f263077145fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="zf-faster-pdb-generation"></a>/Zf (создания быстрее PDB-файла)

Включите быстрее создания PDB-файла в параллельных сборок, сводя к минимуму вызовов RPC к mspdbsrv.exe.

## <a name="syntax"></a>Синтаксис

> **/Zf**

## <a name="remarks"></a>Примечания

**/Zf** параметр включает поддержку компилятора для более быстрое создание PDB-файлы при использовании [/MP (построить с несколькими процессами)](mp-build-with-multiple-processes.md) параметр, или когда система сборки (например, [MSBuild ](/visualstudio/msbuild/msbuild-reference) или [CMake](../../ide/cmake-tools-for-visual-cpp.md)) может выполняться несколько cl.exe компилятора процессы одновременно. Этот параметр вызывает интерфейс компилятора отложить создание типов индексов для каждой записи типа в PDB-файл до конца компиляции, а затем запрашивает их все за один вызов RPC для mspdbsrv.exe вместо внесения запрос RPC для каждой записи. Это может существенно повысить пропускную способность сборки путем снижения нагрузки на процесс mspdbsrv.exe в среде, где одновременно запускать несколько процессов Компилятор cl.exe RPC.

Поскольку **/Zf** применяется только для создания PDF, требует [/ZI](z7-zi-zi-debug-information-format.md) или [/ZI](z7-zi-zi-debug-information-format.md) параметр.

**/Zf** параметр доступен начиная с версии 15.1 2017 г. Visual Studio и по умолчанию отключена.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** включив **/Zf** и выберите **ОК**.

## <a name="see-also"></a>См. также

[Параметры компилятора в алфавитном порядке](compiler-options-listed-alphabetically.md)  
[/MP (сборка с несколькими процессами)](mp-build-with-multiple-processes.md)  
