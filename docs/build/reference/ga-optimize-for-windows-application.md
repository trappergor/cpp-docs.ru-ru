---
title: -GA (оптимизация для приложений Windows) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
dev_langs:
- C++
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 387732c5bde04970e3a467ca4f43f911afa7a9a6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374262"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Оптимизация для приложений Windows)
Результаты более эффективного кода для файла .exe для доступа к переменным локальной памяти потока (TLS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GA  
```  
  
## <a name="remarks"></a>Примечания  
 **/GA** ускоряет доступ к данным объявлен с [__declspec(thread)](../../cpp/declspec.md) в Windows-приложение. Если этот параметр установлен, [__tls_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) макрос полагается равным 0.  
  
 С помощью **/GA** для библиотеки DLL может привести к недопустимой генерации кода.  
  
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