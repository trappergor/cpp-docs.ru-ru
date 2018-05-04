---
title: -V (номер версии) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /v
dev_langs:
- C++
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3daf62c818b454a5477de04a27c4b4f308c271d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="v-version-number"></a>/V (номер версии)
Не рекомендуется. Внедряет строку текста в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Vstring  
```  
  
## <a name="arguments"></a>Аргументы  
 `string`  
 Строка, указывающая номер версии или уведомление об авторском праве для внедрения в OBJ-файле.  
  
## <a name="remarks"></a>Примечания  
 Метка stringcan OBJ-файл с номером версии и авторских правах. Любой пробел или символ табуляции символы должны заключаться в двойные кавычки (""), если они являются частью строки. Обратная косая черта (\\) должны предшествовать двойные кавычки, если они являются частью строки. Пробел между **/V** и `string` является необязательным.  
  
 Можно также использовать [комментарий (C/C++)](../../preprocessor/comment-c-cpp.md) с аргументом типа комментария компилятора для размещения в OBJ-файле имя и номер версии компилятора.  
  
 **/V** параметр является устаревшим, начиная с Visual Studio 2005; **/V** была в основном используются для поддержки процесса создания драйверов виртуальных устройств (VxD), а сборка драйверов VxD больше не поддерживается с помощью набора инструментов Visual C++. Список параметров компилятора см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
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