---
title: -ERRORREPORT (отчет о внутренних ошибках компоновщика) | Документация Майкрософт
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs:
- C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b4b19eed4b481ffa44688e15fb1567e73da1a8f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373469"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (создание отчетов о внутренних ошибках компоновщика)

> **/ errorReport:**[ **none** | **строке** | **очереди** | **отправки** ]

## <a name="arguments"></a>Аргументы

**none**<br/>
Не будет выполняться сбор отчетов о внутренних ошибках компилятора и их отправка в корпорацию Майкрософт.

**prompt**<br/>
Запрашивает отправку отчета при получении внутренней ошибки компилятора. **строки** используется по умолчанию при компиляции приложения в среде разработки.

**queue**<br/>
Отчет об ошибке помещается в очередь. При входе в систему с правами администратора, будет открыто диалоговое окно, чтобы вы можете сообщить о сбоях с момента последнего входа (вам будет не предложено отправить отчеты об ошибках более одного раза каждые три дня). **очередь** используется по умолчанию при компиляции приложения в командной строке.

**send**<br/>
Автоматически отправляет отчеты о внутренних ошибках компилятора в корпорацию Майкрософт, если включены отчеты с помощью параметров службы отчетов об ошибках Windows.

## <a name="remarks"></a>Примечания

**/ErrorReport** параметр позволяет передавать данные о внутренних ошибках (ICE) непосредственно в корпорацию Майкрософт.

Параметр **/errorReport: send** автоматически отправляет сведения об ошибках в корпорацию Майкрософт, если включен, параметры службы отчетов об ошибках Windows.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте **свойства конфигурации** > **компоновщика** > **Дополнительно** страницу свойств.

1. Изменить **отчеты об ошибках** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>См. также

[/errorReport (отчет о внутренних ошибках компилятора)](../../build/reference/errorreport-report-internal-compiler-errors.md)<br/>
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
