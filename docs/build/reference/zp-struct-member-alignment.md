---
title: "-Zp (выравнивание члена структуры) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d387e0ab020e96afb3e2975b5c8686b668cbc10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zp-struct-member-alignment"></a>/Zp (Выравнивание члена структуры)
Определяет, как члены структуры упакованы в памяти и определяет тот же способ упаковки для всех структур в модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## <a name="remarks"></a>Примечания  
 При указании этого параметра, каждый элемент структуры после первого хранится на размер типа члена или `n`-байтовым границам (где `n` является 1, 2, 4, 8 или 16), какое значение меньше.  
  
 В следующей таблице описаны доступные значения.  
  
 1  
 Упаковывает структуры в 1 байт. То же, что **/Zp**.  
  
 2  
 Упаковывает структуры в 2 байта.  
  
 4  
 Упаковывает структуры в 4-байтовым границам.  
  
 8  
 Упаковывает структуры в 8-байтовым границам (по умолчанию).  
  
 16  
 Упаковывает структуры в 16-байтовым границам.  
  
 Не следует использовать этот параметр, если у вас нет специальных требований к выравниванию.  
  
 Можно также использовать [пакет](../../preprocessor/pack.md) упаковки структуры элемента управления. Дополнительные сведения о выравнивании см. в разделах:  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [Оператор __alignof](../../cpp/alignof-operator.md)  
  
-   [__unaligned](../../cpp/unaligned.md)  
  
-   [Примеры выравнивания структуры](../../build/examples-of-structure-alignment.md) (x64 64)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **создания кода** страницу свойств.  
  
4.  Изменить **выравнивание члена структуры** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)