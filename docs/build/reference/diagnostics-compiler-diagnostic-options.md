---
title: -диагностики (параметры компилятора диагностики) | Документы Microsoft
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
ms.openlocfilehash: 2d874e26a922a7f9cce7223b574d525d37733598
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/Diagnostics (параметры компилятора диагностики)  
  
Используйте **/diagnostics** параметр компилятора, чтобы указать расположение сведений об ошибках и предупреждениях.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/diagnostics:{caret|classic|column}
```  

## <a name="remarks"></a>Примечания  
**/Diagnostics** параметр компилятора управляет отображением ошибках и предупреждениях.  
  
**/Diagnostics:classic** параметр выбирается по умолчанию, который сообщает номер строки, где была обнаружена проблема.  
  
**/Diagnostics:column** вариант также включает столбец, где была обнаружена проблема. Это может помочь выявить конструкцию для конкретного языка или символ, который является причиной проблемы.  
  
**/Diagnostics:caret** параметр включает столбец которой проблема был найден и помещает знак вставки (^) в расположении в строке кода, в которых была обнаружена проблема.  
  
Обратите внимание, что в некоторых случаях компилятор не находит место возникновения проблемы. Например отсутствие точки с запятой могут не обнаруживаться до произошла непредвиденная, другие символы. Столбец выводится и курсор помещается, где компилятор обнаружил, что что-то не так, что не всегда, когда нужно сделать ваш исправления.  
  
**/Diagnostics** параметр доступен, начиная с Visual Studio 2017 г.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте свой проект **страницы свойств** диалоговое окно.   
  
2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **Общие** страницу свойств.  
  
3. Используйте элемент управления dropdown в **формат диагностики** параметр отображения поле, чтобы выбрать диагностики. Выберите **ОК** или **применить** для сохранения изменений.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)