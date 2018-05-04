---
title: -Wp64 (выявление проблем переносимости на 64-разрядной платформы) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
dev_langs:
- C++
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 295f2f690cb3c9db17a410cea1f23d04e54b0054
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (выявление проблем переносимости на 64-разрядные платформы)

Этот параметр компилятора не рекомендуется. В версиях до Visual Studio 2013 это позволяет выявить проблемы с 64-разрядной переносимостью для типов, помеченных также ключевым словом [__w64](../../cpp/w64.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Wp64  
```  
  
## <a name="remarks"></a>Примечания  

По умолчанию в версиях Visual Studio до Visual Studio 2013 **/Wp64** компилятора выключен в компиляторе Visual C++, который создает 32-разрядный x86 кода, и на в компиляторе Visual C++, которое создает 64-разрядная версия, x64 кода.  
  
> [!IMPORTANT]
>  Параметр компилятора [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) и ключевое слово [__w64](../../cpp/w64.md) являются устаревшими в Visual Studio 2010 и Visual Studio 2012. Они не поддерживаются в версиях начиная с Visual Studio 2013. Если вы преобразуете проект, использующий этот параметр, то во время преобразования он не будет перенесен. Для использования этого параметра в Visual Studio 2010 или Visual Studio 2012 следует ввести параметр компилятора в области **Дополнительные параметры** раздела **Командная строка** в свойствах проекта. Если в командной строке используется параметр компилятора **/Wp64** , компилятор выводит предупреждение командной строки D9002. Обнаруживать конфликты переносимости на 64-разрядные платформы рекомендуется не с помощью этого параметра и ключевого слова, а с помощью компилятора Visual C++, предназначенного для 64-разрядной платформы, и параметра [/W4](../../build/reference/compiler-option-warning-level.md) . Дополнительные сведения см. в разделе [настройки Visual C++ для 64-разрядных x64 цели](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
Следующие типы переменных проверяются в 32-разрядной операционной системе, как если бы они использовались в 64-разрядной операционной системе:  
  
-   int  
  
-   long  
  
-   указатель  
  
 Если приложение регулярно компилируется с помощью компилятора, который создает 64-разрядная версия, x64 код, можно просто отключить **/Wp64** в 32-разрядных компиляциях, так как 64-разрядный компилятор обнаружит все типы конфликтов. Дополнительные сведения о том, как целевой Windows 64-разрядной операционной системы см. в разделе [настройки Visual C++ для 64-разрядных x64 цели](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта.  
  
     Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Измените поле **Дополнительные параметры** , включив в него параметр **/Wp64**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.  
  
## <a name="see-also"></a>См. также  

[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
[Настройка Visual C++ для 64-разрядных целевых объектов с архитектурой x64](../../build/configuring-programs-for-64-bit-visual-cpp.md)