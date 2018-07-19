---
title: -ERRORREPORT (отчет внутренних ошибках компоновщика) | Документы Microsoft
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
ms.openlocfilehash: 72e620e5347d422a8de66cba3ea9cfd601bb3f29
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374340"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (создание отчетов о внутренних ошибках компоновщика)

> **/ errorReport:**[ **нет** | **строки** | **очереди** | **отправки** ]

## <a name="arguments"></a>Аргументы

**none**  
Не будет выполняться сбор отчетов о внутренних ошибках компилятора и их отправка в корпорацию Майкрософт.

**prompt**  
Запрашивает отправку отчета при получении внутренней ошибки компилятора. **строки** значение по умолчанию, когда приложение компилируется в среде разработки.

**queue**  
Отчет об ошибке помещается в очередь. При входе в систему с правами администратора, будет открыто диалоговое окно, чтобы можно обо всех сбоях с момента последнего входа (не будет предлагаться отправлять отчеты об ошибках в более чем один раз каждые три дня). **очередь** значение по умолчанию при компиляции приложения в командной строке.

**send**  
Автоматически отправляет отчеты о внутренних ошибках компилятора в корпорацию Майкрософт, если включены отчеты по параметрам службы отчетов об ошибках Windows.

## <a name="remarks"></a>Примечания

**/ErrorReport** позволяет передавать данные о внутренних ошибках (ICE) непосредственно в корпорацию Майкрософт.

Параметр **/errorReport: send** автоматически отправляет сведения об ошибках в корпорацию Майкрософт, если параметр включен, параметры службы отчетов об ошибках Windows.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте **свойства конфигурации** > **компоновщика** > **Дополнительно** страницу свойств.

1. Изменить **отчеты об ошибках** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>См. также

[/errorReport (отчет о внутренних ошибках компилятора)](../../build/reference/errorreport-report-internal-compiler-errors.md)  
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)  
