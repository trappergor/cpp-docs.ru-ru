---
title: / Qsafe_fp_loads | Документы Microsoft
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1462303f9e178c70a845066bc7a0a3ce78a99e15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378289"
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

Требуется целочисленные инструкции перемещения значений с плавающей запятой и отключает определенные оптимизации загрузки с плавающей запятой.

## <a name="syntax"></a>Синтаксис

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Примечания

**/ Qsafe_fp_loads** доступен только в компиляторах, предназначенных для x86; он недоступен в компиляторах, предназначенных для x64 или ARM.

**/ Qsafe_fp_loads** регистрирует компилятору использовать целочисленные инструкции перемещения вместо инструкций с плавающей запятой перемещения для перемещения данных между памяти и MMX силы. Этот параметр также отключает оптимизацию нагрузки регистра для значений с плавающей запятой, которые могут загружаться в нескольких путей элемента управления, если значение может вызвать исключение при загрузке — например, значение NaN.

Этот параметр может переопределяться [/fp: except](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** определяет подмножество поведение компилятора, который задается параметром **/fp: except**.

**/ Qsafe_fp_loads** несовместим с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) и [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md). Дополнительные сведения о параметрах компилятора с плавающей точкой см. в разделе [/FP (указать поведение с плавающей запятой)](../../build/reference/fp-specify-floating-point-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите параметр компилятора в **Дополнительные параметры** поле. Выберите **ОК** для применения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)  
[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)  
