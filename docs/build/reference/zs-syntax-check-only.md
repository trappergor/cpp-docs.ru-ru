---
title: -Zs (только синтаксическая проверка) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zs
dev_langs:
- C++
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbefdf18ac5299addc4c0c251d801b39ab038e1e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="zs-syntax-check-only"></a>/Zs (Только синтаксическая проверка)
Предписывает компилятору проверять синтаксис исходных файлов в командной строке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zs  
```  
  
## <a name="remarks"></a>Примечания  
 При использовании этого параметра, не выходные файлы создаются и сообщения об ошибках записываются в стандартный вывод.  
  
 **/Zs** параметр предоставляет быстрый способ найти и исправить синтаксические ошибки перед компиляцией и компоновкой файла источника.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)