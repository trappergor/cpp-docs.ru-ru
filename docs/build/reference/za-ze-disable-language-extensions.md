---
title: -Za, - Ze (отключить расширения языка) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
dev_langs:
- C++
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2949a3d60af6d9058f02d12aac1fd86dead5affa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378149"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (отключить расширения языка)
**/Za** параметр компилятор выдает ошибку для языковых конструкций, которые не совместимы с ANSI C89 или ISO C ++ 11. **/Ze** параметр компилятора, который включен по умолчанию, включает расширения Microsoft.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Za  
/Ze  
```  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  **/Ze** параметр является устаревшим, так как его поведение включено по умолчанию. Рекомендуется использовать [/Zc (соответствие)](../../build/reference/zc-conformance.md) параметры компилятора для управления функциями расширения для конкретного языка. Список параметров компилятора см. в разделе **нерекомендуемые и удаленные параметры компилятора** статьи [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Компилятора предлагает несколько возможностей, не указанные в стандартам ANSI C89, ISO C99 или ISO C++. Эти компоненты называются расширениями Microsoft для языков C и C++. Эти расширения по умолчанию и не доступен при **/Za** параметра. Дополнительные сведения о конкретных расширениях см. в разделе [расширения Майкрософт для языков C и C++](../../build/reference/microsoft-extensions-to-c-and-cpp.md).  
  
 Рекомендуется отключить расширения языка, указав **/Za** вариант, если планируется переносить программы в другие среды. Когда **/Za** указан, компилятор обрабатывает расширенные ключевые слова как простые идентификаторы Майкрософт, отключает другие расширения Microsoft и автоматически определяет `__STDC__` предварительно определенный макрос для программ.  
  
 Другие параметры компилятора, используемые с **/Za** может повлиять на том, как компилятор гарантирует соответствие стандартам. Например **/Za** и [/FP (указать поведение с плавающей запятой)](../../build/reference/fp-specify-floating-point-behavior.md) может привести к поведению рекламной акции типа с плавающей запятой, которое не соответствует ISO C99 и C ++ 11 стандартам.  
  
 Способов для указания конкретных стандартам параметры поведения в разделе [/Zc](../../build/reference/zc-conformance.md) параметр компилятора.  
  
 Дополнительные сведения о вопросах соответствия с [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)], в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В области навигации выберите **свойства конфигурации**, **C/C++**, **языка**.  
  
3.  Изменить **отключить расширения языка** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)