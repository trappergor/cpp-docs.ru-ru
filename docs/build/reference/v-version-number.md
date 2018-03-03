---
title: "-V (номер версии) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a940000b5330c4eccdcabcc5a31f0c3e3e74d65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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