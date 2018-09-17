---
title: -diagnostics (диагностические параметры компилятора) | Документация Майкрософт
ms.custom: ''
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
dev_langs:
- C++
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97b5e3ef2e5c14ae93d4fcc3b016f4dbc955edbd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709167"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/ Diagnostics (диагностические параметры компилятора)

Используйте **/Diagnostics** параметра компилятора определяют отображение данных об ошибках и предупреждения о географическом положении.

## <a name="syntax"></a>Синтаксис

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>Примечания

Этот параметр поддерживается в Visual Studio 2017 и более поздних версий.

**/Diagnostics** параметр компилятора управляет отображением ошибки и предупреждения.

**/Diagnostics:classic** параметр используется по умолчанию, который сообщает номер строки, где была обнаружена проблема.

**/Diagnostics:column** параметр также включает в себя столбец, где была обнаружена проблема. Это может помочь выявить конструкция конкретного языка или символ, который является причиной проблемы.

**/Diagnostics:caret** параметр включает в себя столбец, где был найден проблему и помещает вставки (^) в расположении в строке кода, в которых была обнаружена проблема.

Обратите внимание на то, что в некоторых случаях компилятор не обнаруживает ошибку, где оно произошло. Например отсутствие точки с запятой может быть незамечен до возникла непредвиденная, другие символы. Столбец передается и курсор помещается, где компилятор обнаружил, что что-то было не так, что не всегда должны убедитесь, что изменения внесены.

**/Diagnostics** параметр доступен, начиная с Visual Studio 2017.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте свой проект **страницы свойств** диалоговое окно.

2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **Общие** страницу свойств.

3. Используйте элемент управления dropdown в **формат диагностики** поле, чтобы выбрать диагностический режим отображения. Выберите **ОК** или **применить** для сохранения изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)