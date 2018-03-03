---
title: "-J (по умолчанию является тип unsigned char) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5195822908c13217244a344357a6140d67a9e7df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="j-default-char-type-is-unsigned"></a>/J (тип знака по умолчанию не подписан)
Изменяет значение по умолчанию `char` из тип `signed char` для `unsigned char`и `char` тип является нулем при расширяется для `int` типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/J  
```  
  
## <a name="remarks"></a>Примечания  
 Если `char` значение явно объявляется как `signed`, **/j.** параметр не влияет на его, а значение является расширением знака, когда он преобразуется в `int` типа.  
  
 **/J.** определяет параметр `_CHAR_UNSIGNED`, который используется с `#ifndef` в файле LIMITS.h, чтобы определить диапазон по умолчанию `char` типа.  
  
 ANSI C и C++ не требуют реализации `char` типа. Этот параметр полезен при работе с символьными данными, которые будут в дальнейшем переведены на язык, отличный от английского.  
  
> [!NOTE]
>  При использовании данного параметра компилятора с ATL и MFC, может быть сформирована ошибка. Несмотря на то, что их можно отключить эту ошибку путем определения `_ATL_ALLOW_CHAR_UNSIGNED`, этот обходной путь не поддерживается и может работать не всегда.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В проекте **страницы свойств** в левой области в разделе диалогового **свойства конфигурации**, разверните **C/C++** , а затем выберите **командной строки**.  
  
3.  В **Дополнительные параметры** области, укажите **/j.** параметр компилятора.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)