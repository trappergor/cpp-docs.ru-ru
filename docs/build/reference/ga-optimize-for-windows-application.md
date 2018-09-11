---
title: -GA (оптимизация для приложений Windows) | Документация Майкрософт
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
ms.openlocfilehash: 61bf8844a5471a97214ca6f3d3b5b473c9cd6217
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194667"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Оптимизация для приложений Windows)
Результаты в более эффективный код для файла .exe для доступа к переменным локальное хранилище потока (TLS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GA  
```  
  
## <a name="remarks"></a>Примечания  
 **/GA** ускоряет доступ к данным объявлен с [__declspec(thread)](../../cpp/declspec.md) в приложении на базе Windows. Если этот параметр имеет значение, [__tls_index](/windows/desktop/ProcThread/thread-local-storage) макрос полагается равным 0.  
  
 С помощью **/GA** для библиотеки DLL может привести к созданию неверного кода.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)