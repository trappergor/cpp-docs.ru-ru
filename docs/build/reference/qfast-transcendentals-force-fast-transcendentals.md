---
title: -Qfast_transcendentals (принудительное использование быстрых трансцендентных функций) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qfast_transcendentals
dev_langs:
- C++
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4bb296c8a1fdfde46969ef601fde33c901c9306
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)
Создает встроенный код для трансцендентной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Qfast_transcendentals  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр компилятора принудительно преобразует трансцендентные функции должно быть преобразовано в встроенный код, чтобы повысить скорость выполнения. Этот параметр действует только в том случае, когда в паре с **/fp: except** или **/fp: точный**. Создание встроенного кода для трансцендентной функции уже поведение по умолчанию в разделе **/fp:fast**.  
  
 Этот параметр несовместим с **/fp: strict**. В разделе [/FP (указать поведение с плавающей запятой)](../../build/reference/fp-specify-floating-point-behavior.md) Дополнительные сведения о плавающей точки параметры компилятора.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)